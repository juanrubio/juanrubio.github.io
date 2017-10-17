---
id: 593
title: Upgrading Ubuntu 12.04 Desktop to the latest LTS enablement stack
date: 2013-03-24T00:00:00+00:00
author: Juan Rubio
layout: post
guid: http://www.juanrubio.me/?p=593
permalink: /2013/03/upgrading-ubuntu-12-04-desktop-to-the-latest-lts-enablement-stack/
categories:
  - Linux
---
The ATI Radeon HD 5770 graphics card on my main desktop computer died recently after months and months of noisy overheated operation (not a gamer myself, the dust is the one to blame here). So I&#8217;ve recently upgraded the GPU and unfortunately, I also had to reinstall Ubuntu 12.04. After many failed attempts, I was unable to make the card work with the existing graphics stack (tried different versions of the AMD proprietary driver with no luck). Fortunately I have a separate `/home` partition, so reinstalling Ubuntu is not that much of a pain. 

So I decided to re-install the system and I downloaded a fresh 12.04 image from Ubuntu&#8217;s website. Soon after the installation completed, I noticed that the new Ubuntu image came with an updated Linux kernel, one from the 3.5 series instead of the normal 3.2 that I was used to see on my old Ubuntu 12.04 installation. I doubled check with my laptop&#8217;s 12.04 install, and effectively, there I can see a 3.2 kernel. 

It seems that Ubuntu is shipping its newer Ubuntu Desktop images with updated Linux kernel and X stacks, what they call the &#8220;[LTS Hardware Enablement Stack](https://wiki.ubuntu.com/PrecisePangolin/ReleaseNotes/UbuntuDesktop#LTS_Hardware_Enablement_Stack)&#8220;. This is happening since the 12.04.2 point release. Point releases 0 and 1 shipped with a 3.2 kernel. So if you have an old 12.04 LTS installation , any upgrades applied via the `update-manager` or `apt-get` will only ever install kernels from the 3.2 series. 

It turns out that this is a policy that they plan to continue with in future 12.04 point releases, where the kernel and X stack will be aligned to the latest Ubuntu available at the time. 

However, in order to get these newer kernels you either need to install a system from a 12.04.2+ image or alternatively, opt-in by manually running the following command that will upgrade your installation to the `quantal` enablement stack (the latest at the time of writing). 

<pre class="brush: plain; light: true; title: ; notranslate" title="">$ sudo apt-get install linux-generic-lts-quantal xserver-xorg-lts-quantal
</pre>

In case anyone wonder, the fresh Ubuntu 12.04 installation fixed [the problem](http://askubuntu.com/questions/264362/ubuntu-12-04-freeze-after-changing-graphic-card) I was experiencing with the graphics. But to be completely honest, I still don&#8217;t know exactly why it did.