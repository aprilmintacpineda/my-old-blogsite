---
layout: post
post_title: Upload your site to 000webhost using FileZilla
description: Managing your files with the built-in file manager offered by 000webhost is very limited with free accounts. In this post we will discuss how you can manage your files with FileZilla.
date_posted: 2017-08-16
last_updated: 2017-08-16
cover_image: 2017-08-16-upload-your-site-to-000webhost-using-filezilla/cover_image.png
category: how-tos
tags:
  - web app deployment
  - web app development
  - programming
  - 000webhost
  - free web hosting
  - web hosting
---

# Uploading an entire project to 000webhost

Unfortunately, free accounts does not have the ability to upload an entire directory by compressing it into a `.rar` or `.zip` file. Only the paid ones has that functionality.

So to achieve this effect, you will need to use something called **filezilla**. Firstly, download and install the [FileZilla Client](https://filezilla-project.org/download.php?type=client){:target="_blank"}.

# Setting things up

After you have installed that. Open the settings and we will set up some things first.

![open-settings](/blog/public/post-resources/2017-08-16-upload-your-site-to-000webhost-using-filezilla/open-settings.png)

### Disable timeout

On the **connection panel**, make sure the **Timeout in seconds** is set to 0, this is to prevent the **connection timeout after seconds of inactivity**.

![disable timeout](/blog/public/post-resources/2017-08-16-upload-your-site-to-000webhost-using-filezilla/timeout.png)

### Enable password saving

###### Notice

Do this if you don't want to type your password everytime you connect, otherwise skip this part.

On the **interface panel**, make sure to click on the **Save passwords**.

![save passwords](/blog/public/post-resources/2017-08-16-upload-your-site-to-000webhost-using-filezilla/save-passwords.png)

Save settings by clicking on the **OK button** on the lower left corner.

![save settings](/blog/public/post-resources/2017-08-16-upload-your-site-to-000webhost-using-filezilla/save-settings.png)

# Website manager

Click on **File > Site Manager** as shown in the image below.

![Open site manager](/blog/public/post-resources/2017-08-16-upload-your-site-to-000webhost-using-filezilla/open-site-manager.png)

Click on **new site button** then name your site whatever you like, I named mine as the domain name of my site so that it will not be confusing. You can edit that by clicking on the site name, then press **f2**.

![New site](/blog/public/post-resources/2017-08-16-upload-your-site-to-000webhost-using-filezilla/new-site.png)

Now you need to get the FTP information of your account, [login to your cpanel](https://www.000webhost.com/996779.html), then go to the general settings as shown in the image below. Scroll down a bit and you will see the FTP details, we need those to connect to the FTP server.

![General settings](/blog/public/post-resources/2017-08-16-upload-your-site-to-000webhost-using-filezilla/general-settings.png)

![FTP details](/blog/public/post-resources/2017-08-16-upload-your-site-to-000webhost-using-filezilla/ftp-details.png)

On your general tab, make sure to use your own setting as follows:

|------------+-------|
| Field name | value |
|------------+-------|
|Host|Copy value from your FTP details|
|Port|leave this empty|
|Protocol|FTP - File Transfer Protocol|
|Encryption|Only use plain FTP|
|Logon Type|Normal|
|User|Copy value from your FTP details|
|Password|Copy value from your FTP details|

![site manager general](/blog/public/post-resources/2017-08-16-upload-your-site-to-000webhost-using-filezilla/site-manager-general.png)

Then on the **Advanced tab**, click on the **browse** on the right side of the **Default local directory field**, then browse to where your website folder is located. Then click **Select folder**.

![local directory](/blog/public/post-resources/2017-08-16-upload-your-site-to-000webhost-using-filezilla/select-local-directory.png)

Then on the **Default remote directory**, put `/public_html` then simply click on the connect button.

![local directory](/blog/public/post-resources/2017-08-16-upload-your-site-to-000webhost-using-filezilla/remote-directory.png)

If your settings are correct and you followed along, you should not be connected to your **000webhost account** and you will see something that looks like this:

![local directory](/blog/public/post-resources/2017-08-16-upload-your-site-to-000webhost-using-filezilla/connected.png)

# Upload files and directories

You can see from the image above that the only file I have on my website is the `.htaccess` file. Now to upload your files, **highlight all the files and folders that you would like to upload > right click > Add files to queue** as shown below.

![add to queue](/blog/public/post-resources/2017-08-16-upload-your-site-to-000webhost-using-filezilla/add-to-queue.png)

Then **right click on an empty space on the queues > Process Queue** as shown below.

![process queue](/blog/public/post-resources/2017-08-16-upload-your-site-to-000webhost-using-filezilla/process-queue.png)

You could also just click on the **upload** when you right clicked the files you want to upload. Now you see the files on your website has been updated and the files and folders you uploaded are now visible.

![uploaded](/blog/public/post-resources/2017-08-16-upload-your-site-to-000webhost-using-filezilla/uploaded.png)

### Notice

If you uploaded a file and the file already exists, a dialogue box will appear asking you about what to do with the duplicate files.

![file exists](/blog/public/post-resources/2017-08-16-upload-your-site-to-000webhost-using-filezilla/file-exists.png)

# Download a file from your website to your computer

As you may or may not have noticed, I have a `.htaccess` file on my website but I don't have this file on my computer, so I'm going to download this to make sure all my files on my computer and my website are updated.

Simply **right click on the file you want to download > Download**. It will be downloaded and will be visible on my computer now.

![download](/blog/public/post-resources/2017-08-16-upload-your-site-to-000webhost-using-filezilla/download.png)

# Reconnecting

After closing FileZilla, and you want to connect again to your website, since we created our website in FileZilla's Website Manager, all we have to do is to **click on the dropdown next to Website Manager icon > click on your website**, FileZilla will automatically connect again using your previous settings. If ever you made changes to your settings, you need to change your settings on the **Website Manager** as well, it's just like how we set it all up.

![download](/blog/public/post-resources/2017-08-16-upload-your-site-to-000webhost-using-filezilla/recon.png)

Now you can visit your website and you will see all your changes.

* * *

**{} with <3 by April Mintac Pineda**