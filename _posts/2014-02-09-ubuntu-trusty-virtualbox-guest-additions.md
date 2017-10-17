---
id: 627
title: Install VirtualBox Guest Additions in Ubuntu 14.04 Alpha via package system
date: 2014-02-09T00:00:00+00:00
author: Juan Rubio
layout: post
guid: http://www.juanrubio.me/?p=627
permalink: /2014/02/ubuntu-trusty-virtualbox-guest-additions/
categories:
  - Linux
  - Ubuntu
---
I&#8217;ve been recently running Ubuntu 14.04 Daily Build using VirtualBox. Everything has been working great so far. However, after some large system upgrade involving a new kernel and a bunch of the xorg libraries, the customary re-installation of the VirtualBox Guest Additions modules stopped working for me. After several attempts, I was getting a message like this: 

> Warning: unknown version of the X Window System installed. Not installing X Window System drivers. 

I googled around and I found a very [useful thread](http://ubuntuforums.org/showthread.php?t=2057146&#038;page=2) in [ubuntuforums.org](http://ubuntuforums.org) that gave me the answer. So the steps that finally resolved this issue were: 

<ol class="org-ol">
  <li>
    Remove the existing <code>Guest Additions</code> using the script under <code>/opt</code>: <div class="org-src-container">
      <pre class="brush: plain; light: true; title: ; notranslate" title="">
$ /opt/VBoxGuestAdditions-4.3.6/uninstall.sh
</pre>
    </div>
  </li>
  
  <li>
    Install the <a href="http://packages.ubuntu.com/trusty/virtualbox-guest-additions-iso">Guest Additions Iso</a> using the package system <div class="org-src-container">
      <pre class="brush: plain; light: true; title: ; notranslate" title="">
$ sudo apt-get install virtualbox-guest-additions-iso
</pre>
    </div>
  </li>
  
  <li>
    Enable VirtualBox Guest Service driver, using the <code>software-properties-gtk</code> dialog. <p>
      You can type the following command in the terminal to bring up the dialog.
    </p>
    
    <div class="org-src-container">
      <pre class="brush: plain; light: true; title: ; notranslate" title="">
$ software-properties-gtk --open-tab=4
</pre>
    </div>
    
    <div class="figure">
      <p>
        <img src="http://www.juanrubio.me/wp-content/uploads/2014/02/wpid-software-properties-gtk-tab4.png" alt="wpid-software-properties-gtk-tab4.png" />
      </p></p>
    </div>
  </li>
  
  <li>
    Reboot <p>
      The guest display can now be auto-resized, made full screen, etc.
    </p>
  </li>
</ol>

<div id="outline-container-sec-1" class="outline-2">
  <h2 id="sec-1">
    Update 13/02/2014:
  </h2>
  
  <div class="outline-text-2" id="text-1">
    <ul class="org-ul">
      <li>
        From today, this solution appears to be broken. Presumably, the latest upgrades pushed to the 14.04 repos have somehow broken it, most likely temporarily. I&#8217;ll update again this post if I find it working again. But in the meantime, you&#8217;ve been warned! 🙂
      </li>
    </ul>
  </div>
</div>

<div id="outline-container-sec-2" class="outline-2">
  <h2 id="sec-2">
    Update 15/02/2014
  </h2>
  
  <div class="outline-text-2" id="text-2">
    <ul class="org-ul">
      <li>
        As it turns out, there is a test build of the Guest Additions iso (v4.3.7) that installs without problems and fixes the issues. Thanks to AnimeMuyou and Martin for pointing this out (look for the links in the Replies section).
      </li>
    </ul>
  </div>
</div>
