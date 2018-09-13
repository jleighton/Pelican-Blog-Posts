Title: Namecheap SSL Tutorial (Lighttpd)
Date: 2014-11-07 12:08
Author: jamesleighton
Tags: geek, lighttpd, ssl
Slug: namecheap-ssl-tutorial-lighttpd
Status: published

Namecheap's cheap SSL certificates work great on desktop, but are missing the root cert therefore gave me an untrusted error on Android (and I assume iOS).

I spend a while trying to figure out how to fix this, and I finally have!

From the zip file they send you, combine the files using cat like this. The order is important for the mobile devices.

<div class="highlight">

    cat COMODORSADomainValidationSecureServerCA.crt COMODORSAAddTrustCA.crt AddTrustExternalCARoot.crt > bundle

</div>

Add your private key and certificate from Namecheap (domain\_tld.crt file) to a single file, too.

<div class="highlight">

    cat privatekeyhere.key domain_tld.crt > certificate.pem

</div>

Use whatever names you want for the outputted files. Just make them consistent. You should probably make sure only your [web-server/root](http://blog.chrismeller.com/creating-and-managing-ssl-certificates-with-nginx) user can read them to keep them secure.

Finally in your lighttpd.conf add something like the following to enable SSL globally for your server.

<div class="highlight">

    $SERVER["socket"] == "ip.address:443" 
    {

    server.document-root = "/var/www/"
    ssl.engine = "enable"

    ssl.use-sslv2 = "disable"
    ssl.use-sslv3 = "disable"

    ssl.ca-file = "/path/to/bundle"
    ssl.pemfile = "/path/to/certificate.pem"

    }

</div>

To force SSL connections only, you'll want to add something like this:

<div class="highlight">

    $SERVER["socket"] == ":80" 
    {
            $HTTP["host"] =~ "(.*)" 
            {
                    url.redirect = ( "^/(.*)" => "https://%1/$1" )
            }
    }

</div>

Thanks to [Ben Green](http://bengreen.eu/fancyhtml/techiestuff/sslcertificateswithlighttpd.html), [SSL247](https://www.ssl247.co.uk/support/install/lighttpd), and [Bill Patrianakos](http://billpatrianakos.me/blog/2014/04/04/installing-comodo-positive-ssl-certs-on-apache-and-openssl/) for all pointing me in the right direction :)
