Title: Pelican Blog Workflow and Blogger Migration Tips
Date: 2014-04-11 18:59
Author: jamesleighton
Category: linux
Tags: blog
Slug: pelican-blog-workflow-and-blogger-migration-tips
Status: published

I migrated away from Blogger this month to using [Pelican Static Site Generator](http://docs.getpelican.com/en/3.3.0/). It's very different, and the change is quite a bit to get used to. Previously, I'd log into blogger and draft away, add some images and publish.

Now I store my raw markdown blog posts in a [Bittorrent sync](http://www.bittorrent.com/sync) folder that syncs between my desktop, mobile devices, and netbook. From here, I connect to my webserver using SSH and upload the post and all related media. I then run the pelican command which outputs the static site to the webservers htdocs/www folder.

Pros? Absolutely no server side scripting on the server. No PHP, no CGI, and of course there is no MySQL server anywhere in sight. It's brilliant. This also means I sidestep any problems such as the [xmlrpc.php issues](http://blog.spiderlabs.com/2014/03/wordpress-xml-rpc-pingback-vulnerability-analysis.html) that seem to be plauging Wordpress admins everywhere. Pages also load really damn quickly.

Cons? It's not as simple! That's pretty much the only draw back I can find! This is not a blogging engine for your mother. Someone has made a tutorial for posting and managing their Pelican install via [Dropbox](http://technivore.org/posts/2014/01/03/blogging-with-dropbox-and-pelican.html). I don't use Dropbox myself, but I imagine it would be easy to adapt to [Bittorrent Sync](http://www.bittorrent.com/sync) when I'm bored one day.

Being consistant with images is another potential snag. Due to my permalink structure (more on that in a minute!) I store my image media in a top level folder called 'images' therefore I can reference images using '/images/img\_name.png' from any post and have them work. If you didn't do it this way, I imagine it'd just be a nightmare keeping track of post media. If you have questions, feel free to leave a comment below.

Blogger Migration Tip
---------------------

When moving away from Blogger it's a good idea to keep your permalinks the same as they were to avoid losing out on search engine hits. To achieve this with Pelican, add the following to your pelicanconf.py file:

<div class="highlight">

    ARTICLE_URL = "{date:%Y}/{date:%m}/{slug}.html"
    ARTICLE_SAVE_AS = "{date:%Y}/{date:%m}/{slug}.html"

</div>

Also, add the following to make yearly and monthly archive pages work:

<div class="highlight">

    YEAR_ARCHIVE_SAVE_AS = '{date:%Y}/index.html'
    MONTH_ARCHIVE_SAVE_AS = '{date:%Y}/{date:%m}/index.html'

</div>

This will result in blog post URLs that match the Blogger's default URLs. Just make sure when you move everything over that you keep the 'slug' the same as what was stored with Blogger otherwise the resulting URLS won't match.

As for migrating, I did it all manually. I loaded each post up on blogger, used wget to download the images into the \[pelican folder\]/content/images folder, and then converted each post into Markdown. There is an RSS feed importer but I couldn't find a way to get my older posts importer so I gave up using the importer and spend several weeks moving my posts over to markdown files for Pelican.
