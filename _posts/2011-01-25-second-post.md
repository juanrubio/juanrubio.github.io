---
id: 104
title: Second post
date: 2011-01-25T00:36:44+00:00
author: Juan Rubio
layout: post
guid: http://joni-studio-xps-8100/?p=104
permalink: /2011/01/second-post/
categories:
  - Uncategorized
  - VPS
tags:
  - CMS
  - VPS
---
<div id="yass_top_edge_dummy" style="width: 1px; height: 1px; padding: 0px; margin: -11px 0px 0px; border-width: 0px; display: block;">
</div>

<div id="yass_top_edge" style="background-image: url('chrome://yass/content/edgebgtop.png'); background-attachment: scroll; background-position: center bottom; padding: 0px; margin: 0px 0px 10px -386px; border-width: 0px; height: 0px; display: block; width: 1px;">
</div>

I was discussing in my <a title="Up and running" href="http://www.juanrubio.me/2011/01/up-and-running/" target="_blank">previous post</a> some of the basic process I went through when I decided to setup my own Virtual Private Server. But there is more to it than just the hosting and the CMSs.

  * _**The choice of OS**_
  * I didn&#8217;t mention anything about the OS in the previous post, but this is possibly the most fundamental decision to be made. The cut the story short, my main goal was to build a stable system that I could trust to build a couple of websites, including my weblog and my company&#8217;s website and also to host some private, software development tools to be used to support a number of my company&#8217;s software projects. I&#8217;ve been a long time happy user of Ubuntu systems and this sort of was the obvious choice for me. So didn&#8217;t have to think a lot to deploy the most recent Ubuntu Server [Long-Term Support (LTS)](https://wiki.ubuntu.com/LTS "Ubuntu LTS") system available at <a title="Linode" href="http://www.linode.com/" target="_blank">Linode</a> at the time.

  * _**Web Server Infrastructure**_
  * Not much to decide on this department really: <a title="Lamp @ Wikipedia" href="http://en.wikipedia.org/wiki/Lamp" target="_blank">LAMP</a> (Linux, Apache, MySQL, and in my case, a combination of mostly PHP and Python-based tools).

  * _**Email system**_
  * There a number of great guides around that really helped when deciding on the email system tools combination. I personally liked the <a title="Slicehost's mail server guide" href="http://articles.slicehost.com/2008/9/2/mail-server-overview" target="_blank">Slicehost guides</a> as a friendly start on this subject. I&#8217;ll just say that my email system is based on a combination of <a title="Postfix" href="http://www.postfix.org/" target="_blank">Postfix</a> + <a title="The Courier IMAP server" href="http://www.courier-mta.org/imap/" target="_blank">Courier IMAP</a> + <a title="RoundCube webmail" href="http://roundcube.net/" target="_blank">RoundCube</a>. But the email system configuration is a complex and lengthy process and there are a number of additional software tools that sooner or later one need to install to have a properly configured system (e.g. solutions for security, anti-Spam and anti-virus functionality).

  * **_Security_**
  * It is essential to take good care of your server by following at least some of the best practices in Linux server security, like keeping your system up-to-date using your distribution&#8217;s package management system, disabling unused services, and disabling root logins and password authentication via SSH. For more comprehensive lists, the security guides at <a title="Security guides @ Linode" href="http://library.linode.com/security" target="_blank">Linode</a> and <a title="Security articles @ Slicehost" href="http://articles.slicehost.com/security" target="_blank">Slicehost</a> are good starting points.

  * **_Backups_**
  *  And finally, some backup strategy should be in place. I really value my data and the integrity of my websites, but more than anything else, I value my time. Fortunately, Linode has a great <a title="Linode's managed backup service" href="http://www.linode.com/backups/" target="_blank">managed backup service</a> which I consider pretty cheap and simple. This was a no-brainer for me.

&nbsp;