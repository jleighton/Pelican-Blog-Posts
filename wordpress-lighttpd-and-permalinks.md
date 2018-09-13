Title: Wordpress, Lighttpd and Permalinks
Date: 2012-11-15 21:44
Author: jamesleighton
Tags: howto, lighttpd, wordpress
Slug: wordpress-lighttpd-and-permalinks
Status: published

For a few months I've been putting up with no pretty permalinks on my blog. It looked a bit crap, but now I've migrated Tupcast and this blog to a [wordpress network](http://codex.wordpress.org/Create_A_Network) I thought it was time to sort it out.

Turns out getting permalinks functioning with Lighttpd wasn’t actually that bad. I ended up with effectively the code found on this [blog](http://server.vijge.net/archive/running-wordpress-with-lighttpd/). He mentions a really good point however, running a php script for every upload isn’t exactly the most efficient especially since I am running on a pretty low spec VPS… I was mainly getting stuck on guides that said to redirect to ‘/wp-content/blogs.php’. This is old and has been replaced in newer versions of Wordpress.

‘/wp-content/blogs.php’ in these examples should be replaced with ‘wp-includes/ms-files.php’ if you are following these guides.

The better way is to manually code the ID as shown on the same blog linked. Better for your server, and it probably means pages get loaded faster too. I have had to adjust it slightly to allow for my podcast files to still be accessed directly despite permalinks being setup. If you have any folders that you need, just substitute them in!

My final code is as follows for tupcast.co.uk (which has a network ID of 2)

<div class="highlight">

    $HTTP["host"] =~ "tupcast.co.uk" {
    url.rewrite-once = (<
     "^/(.*)?/?files/(.*)" => "/wp-content/blogs.dir/2/files/$2",
     "^/(wp-.*)$" => "$1",
     "^/favicon.ico$" => "$1",
     "^/xmlrpc.ico$" => "$1",
     "^/robots.txt$" => "$1",
     "^/([_0-9a-zA-Z-]+/)?(.*.php)$" => "$2",
     "(?.*)$" => "index.php$1",
     "." => "index.php"
    )}

</div>
