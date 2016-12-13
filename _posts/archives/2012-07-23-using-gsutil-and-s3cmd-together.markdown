<div class="container">

<div class="left-col">

<div class="intrude-less">

<div class="profilepic">

</div>

[Jorge's Stompbox](/)
=====================

Plug in, crank it to Eleven.
----------------------------

-   [About Jorge](http://about.me/jorge.castro)
-   [Bio](http://www.jorgecastro.org/about.html)
-   [Blog](/)
-   [Archives](/blog/archives)
-   [Public Key](https://keybase.io/castrojo/key.asc)
-   [My Wife, Jill](http://drjillcastro.org/)
-   [My beagle, Oscar](http://packdog.com/oscar-castro)
-   -   [My bagel, Luna](http://packdog.com/luna-330)
-   

\
### Projects I work on

-   [Ubuntu Server](http://ubuntu.com/server)
-   [Juju](http://jujucharms.com)
-   [Juju Charms](http://jujucharms.com/store)
-   [Ask Ubuntu](http://askubuntu.com/users/235/jorge-castro)

\
### Projects that inspire me

-   [OpenStack](http://openstack.org)
-   [Discourse](http://discourse.org)
-   [FIRST Robotics Competition](http://usfirst.org)
-   [Little Kids Rock](http://www.littlekidsrock.org)

<div class="section aboutme">

I work on the Juju Ecosystem Team at Canonical Ltd. on Ubuntu Cloud and
Server, find me at jorge at ubuntu dot com.

</div>

<div class="social">

[Google+](https://plus.google.com/116015965439782966698 "Google+"){.google}
[Twitter](http://twitter.com/castrojo "Twitter"){.twitter}
[GitHub](https://github.com/castrojo "GitHub"){.github}
[](http://askubuntu.com/users/235/jorge-castro "Ask Ubuntu"){.stackoverflow}
[RSS](/atom.xml "RSS"){.rss}

</div>

</div>

</div>

<div class="mid-col">

<div id="banner" class="inner">

<div class="container">

</div>

[castrojo](http://twitter.com/castrojo) @ [Twitter](http://twitter.com)
<div class="loading">

Loading...

</div>

</div>

<div class="mid-col-container">

<div id="content" class="inner">

<div class="entry-content" itemprop="articleBody">

Small tips I’ve learned when using cloud storage:

[gsutil](https://developers.google.com/storage/docs/gsutil) is a great
little tool for managing Google Cloud Storage. In fact, if you look in
`~/.boto` it lets you also configure it’s usage with AWS. This is great
for me because I am often using both to test things (like performance)
and it’s nice to use one tool for “cloud storage stuff” instead of tools
specific to one storage provider.

I wanted to see how Google Storage works for hosting my blog so I copied
it over.

    gsutil -m cp -R s3://www.jorgecastro.org gs://www.jorgecastro.org

The `-m` is a nice little feature of gsutil. It turns on multithreaded
copies, very nice if you have a fast connection. I now have my blog on
two cloud providers, not bad for backups!

So does this mean I’ll never need s3cmd again? One bummer is that gsutil
does copies, it doesn’t do an equivalent of an rsync. So if I am
automating things I’m recopying a bunch of things over that don’t need
to be.

    s3cmd sync local_dir s3://www.jorgecastro.org

Ok so that means, if you’re doing a huge copy into S3 you can use
gsutil’s awesome multithreaded uploading to speed that up, then use
s3cmd in subsequent copies to save bandwidth. Not bad!

I suspect as more and more Cloud Storage providers pop up that both
gsutil and s3cmd will start to become more generalized tools, as a cloud
user I don’t really care where my bucket is, I do however want to have
one tool to manipulate it.

References and Stuff you should check out:

-   [Cloud storage solutions: s3cmd boto
    gsutil](http://housegeekatheart.blogspot.com/2011/04/cloud-storage-solutions-s3cmd-boto.html)

</div>

<div class="share">

<div class="addthis_toolbox addthis_default_style">

[](){.addthis_button_tweet} [](){.addthis_button_google_plusone}
[](){.addthis_counter .addthis_pill_style}

</div>

</div>

<div id="comment" class="section">

<div id="disqus_thread" aria-live="polite">

Please enable JavaScript to view the [comments powered by
Disqus.](http://disqus.com/?ref_noscript)

</div>

</div>

</div>

</div>

Copyright © 2016 - Jorge O. Castro - <span class="credit">Powered by
[Octopress](http://octopress.org)</span>

Design credit: [Shashank
Mehta](http://shashankmehta.in/archive/2012/greyshade.html)

</div>

</div>
