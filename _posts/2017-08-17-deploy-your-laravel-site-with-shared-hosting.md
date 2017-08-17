---
layout: post
post_title: Deploy your laravel site with shared hosting
description: Looking to deploy your laravel powered site on shared hosting? This guide will help you out with that.
date_posted: 2017-08-17
last_updated: 2017-08-17
cover_image: 2017-08-17-deploy-your-laravel-site-with-shared-hosting/cover_image.jpg
category: how-tos
tags:
  - web app deployment
  - web app development
  - programming
  - 000webhost
  - free web hosting
  - web hosting
  - shared hosting
  - laravel 5.4
---

Please take note of the date this was last updated vs the date you are reading this.

# Limitations

- This guide will not walk you through database migrations.
- This guide will not walk you through creating your website will laravel.
- This guide will not walk you through installing laravel on your site. Read the docs for that. [Install Laravel 5.4](https://laravel.com/docs/5.4/installation){:target="_blank"}.
- This guide will not walk you through deploying your site with GIT.

# Deploy your laravel website on shared hosting

In this post, I will use [000webhost](https://www.000webhost.com/996779.html){:target="_blank"}, it offers free hosting, using it, you can deploy and test your site or showcase your hobby sites.

Despite that I mentioned above that I will not guide you to deploying your site on servers that support GIT, 000webhost supports GIT but only for premium users. It also supports remote mysql connection (which is what you need for your database migrations), but again, only for premium users.

[Visit the laravel-test-site that I deployed on shared hosting](http://laravel-test-site.000webhostapp.com/){:target="_blank"}

### Step 1: Create an account

Create your account on [000webhost](https://www.000webhost.com/996779.html){:target="_blank"} and verify your email.

### Step 2: Upload your site

Upload your site to your site at 000webhost. Now, if you are using a free account, **GIT** is not available for you, using FileZilla to FTP your files wouldn't be wise, but there is always a work-around.

###### Work around

Highlight all your files and compress them to a **zip** file.

![Zip them!](/blog/public/post-resources/2017-08-17-deploy-your-laravel-site-with-shared-hosting/zip-them.png)

Upload the zip file.

![Upload the zip](/blog/public/post-resources/2017-08-17-deploy-your-laravel-site-with-shared-hosting/upload-the-zip.png)

Right click on the zip file > Extract

![Extract the zip](/blog/public/post-resources/2017-08-17-deploy-your-laravel-site-with-shared-hosting/extract-the-zip.png)

I simply called the destination folder **test-site**

![Extract the zip](/blog/public/post-resources/2017-08-17-deploy-your-laravel-site-with-shared-hosting/extract-the-zip-1.png)

Now all my files have been extracted to the folder **test-site**, all I have to do now is to **move them**. Open the folder where you extracted all your files. Highlight all your files:

- Click the first file.
- Click the last file while holding down the **shift** button.

Highlighting files on the file manager works exactly the same way with with windows. Now you have to move them:

- Right click on the one of the highlighted files.
- Click **Move**.
- Change the destination to `/public_html`.
- Click **Move**.

Now all the files have been moved and the **test-site folder** where we put the files during extraction is now empty. So I delete the **test-site folder** and the zip file because I no longer need those.

![Move the files](/blog/public/post-resources/2017-08-17-deploy-your-laravel-site-with-shared-hosting/move-the-files.png)

![Move the files](/blog/public/post-resources/2017-08-17-deploy-your-laravel-site-with-shared-hosting/move-the-files-1.png)

If you open the website's homepage, i.e. **the-site.000webhostapp.com/**, you will see a that looks somewhat like this:

![The site after upload](/blog/public/post-resources/2017-08-17-deploy-your-laravel-site-with-shared-hosting/the-site-after-upload.png)

There are two major bad things about this:

1. This page is displaying all our files and folder structure.
2. We don't want our visitors to see this page.

You will also notice that if you visit your site with **the-site.000webhostapp.com/public/** it will workout just fine.

### Step 3: Using .htaccess

If you are using [000webhost](https://www.000webhost.com/996779.html), you would already have a `.htaccess` file on your site since every site you create will be initialized with a `.htaccess` file that has the following codes:

{% highlight ruby %}
# HTID:2253271: DO NOT REMOVE OR MODIFY THIS LINE AND THE LINES BELOW
php_value display_errors 1
# DO NOT REMOVE OR MODIFY THIS LINE AND THE LINES ABOVE HTID:2253271:
{% endhighlight %}

For some others you may need to create your own. Please note that the codes above are not necessary for this to work but are necessary for **000webhost**.

You will need to add the following codes:

{% highlight ruby %}
# Prevent directory listing
Options -Indexes

# Turn on RewriteEngine
RewriteEngine on
# Redirect all requests to /publoc
RewriteRule ^(.*)$ /public/index.php [NC,L,QSA]
{% endhighlight %}

What this will do is redirect all requests to `/public/index.php`.

# Things to remember

{% highlight html %}
<link rel="stylesheet" type="text/css" href="/path/to/some/file.ext">
<!-- should be changed to -->
<link rel="stylesheet" type="text/css" href="/public/path/to/some/file.ext">
{% endhighlight %}

{% highlight html %}
<a href="/some-page">Some page</a>
<!-- should be changed to -->
<link rel="stylesheet" type="text/css" href="/public/some-page">
{% endhighlight %}

* * *

**{} with <3 by April Mintac Pineda**

Did I missed something? Are you experiencing an error? Have a better solution? Don't hesitate to contact me at **aprilmintacpineda@gmail.com**.