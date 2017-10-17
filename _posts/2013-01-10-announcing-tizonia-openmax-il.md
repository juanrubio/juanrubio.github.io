---
id: 393
title: Announcing Tizonia OpenMAX IL
date: 2013-01-10T15:26:42+00:00
author: Juan Rubio
layout: post
guid: http://www.juanrubio.me/?p=393
permalink: /2013/01/announcing-tizonia-openmax-il/
categories:
  - Multimedia
  - Open Source Software
  - OpenMAX IL
  - Tizonia
tags:
  - Khronos
  - Multimedia
  - Open Source
  - OpenMAX IL
  - Tizonia
---
Over the last year and a half, I&#8217;ve been working on the spare time between projects on my own <a title="OpenMAX IL - The Khronos Group" href="http://www.khronos.org/openmax/" target="_blank">OpenMAX IL</a> implementation for Linux. I started it because I really enjoyed implementing OpenMAX IL on Symbian OS during my days as a developer in the Multimedia Team of  Symbian and Nokia. Since I no longer was at Nokia and the Symbian platform was effectively defunct, I had no practical means of working with OpenMAX  (well, at least not in the way I was used to, which is, using with my own code base).

At the same time, I wanted to update my Linux system programming skills, after 4+ years working almost exclusively on Symbian. Having started in systems programming with <a title="Slackware Linux 3.4" href="http://www.elisoftware.org/index.php?title=Linux_Slackware_3.4_11/97_%28PC,_CD-ROM%29_Walnut_Creek_-_1997_USA,_Canada_Release" target="_blank">Slackware Linux 3.4</a> at university around 1997, after 4 years of exclusive Symbian OS work, I was already missing Linux.

Anyhow, at the time when I started this new OpenMAX IL implementation, there were already two fine Open Source implementations for Linux, <a title="Bellagio OpenMAX Integration Layer" href="http://omxil.sourceforge.net/" target="_blank">Bellagio OpenMAX IL</a> and <a title="LIM OpenMAX Implementation" href="http://limoa.sourceforge.net/" target="_blank">LIM</a>, so as usual, there really was no need for another one. However, I as I mentioned, I wanted to experiment with my own code base. So here it is. I&#8217;ve finally managed to put some time together over the Christmas period to tidy up the code and <a title="Tizonia OpenMAX IL project" href="http://tizonia.org" target="_blank">share it</a>.

Comparing this new code base with the implementation that I did for Symbian, this is a complete redesign, with a new threading model and internal architecture. And obviously, there is no Symbian C++ anymore, this is written in C. It shares though the object-orientation approach of the base component infrastructure, but with a completely different API.

Initially, **Tizonia OpenMAX IL** was based on IL  version 1.1.2, which was the latest version of the spec at the time. But once Khronos made public its 1.2 provisional specification, I decided to migrate the code base to it. Still this is not yet a complete implementation of the 1.2 provisional spec; I soon plan to document the status of the implementation either in this blog or in the project website.

The code is hosted on <a title="Tizonia Op0enMAX IL on GitHub" href="http://github.com/tizonia" target="_blank">GitHub</a> with repos mirrored on <a title="Tizonia Op0enMAX IL on Bitbucket" href="http://www.juanrubio.me/2011/11/emacs-smex-m-x-do-not-like-typing/" target="_blank">Bitbucket</a> and the project&#8217;s website is reachable from <a title="Tizonia OpenMAX IL website" href="http://tizonia.org" target="_blank">http://tizonia.org</a>

There is still a ton of quality work to be done plus a number of critical APIs that are missing in the base framework, so there is still no date for the first &#8220;official&#8221; release. However, functionality wise, with Base and tunnelled communication working decently, I believe there is enough already to make it worth sharing.

I hope people can find Tizonia a useful platform to experiment with and try the new OpenMAX IL 1.2 features that Khronos anticipated in the provisional specification. At least, I had some good fun myself while working on it.

<br>
