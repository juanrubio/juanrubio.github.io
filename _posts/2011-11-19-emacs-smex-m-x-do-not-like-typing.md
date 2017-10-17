---
id: 351
title: 'Emacs smex : M-x do-not-like-typing'
date: 2011-11-19T16:02:34+00:00
author: Juan Rubio
layout: post
guid: http://www.juanrubio.me/?p=351
permalink: /2011/11/emacs-smex-m-x-do-not-like-typing/
categories:
  - Emacs
tags:
  - Emacs
---
<div id="yass_top_edge_dummy" style="width: 1px; height: 1px; padding: 0px; margin: -11px 0px 0px; border-width: 0px; display: block;">
</div>

<div id="yass_top_edge" style="background-image: url('chrome://yass/content/edgebgtop.png'); background-attachment: scroll; background-position: center bottom; padding: 0px; margin: 0px 0px 10px -386px; border-width: 0px; height: 0px; display: block; width: 1px;">
</div>

<p style="margin-top: 10px;">
  As an ordinary hardcore Emacs user, I only use the mouse when is absolutely necessary. In fact I removed the top menu and the tool bar from the stock interface many, many years ago:
</p>

<pre class="aligncenter"><span style="font-family: courier new,courier;">'(menu-bar-mode nil nil (menu-bar)) </span>
<span style="font-family: courier new,courier;">'(tool-bar-mode nil nil (tool-bar))</span></pre>

Not liking the mouse, there are the two basic things you have to do to keep using Emacs in a productive way: memorize tons of **_keyboard shortcuts_** and knowing your way with the **_M-x commands_**.

But the above two things lead to lots of typing. And I don&#8217;t like typing a lot either (&#8230;no one does&#8230;). But the good thing is that Emacs has plenty of interesting packages to help reduce the amount of typing that one has to do to complete the usual editing tasks.

One of those packages is <a title="Ido @ EmacsWiki" href="http://www.emacswiki.org/emacs/InteractivelyDoThings" target="_blank">Ido</a> which I&#8217;ve been using for quite a few years now.

<pre class="aligncenter"><span style="font-family: courier new,courier;"> ;;Ido</span>
<span style="font-family: courier new,courier;"> (require 'ido) </span>
<span style="font-family: courier new,courier;"> (ido-mode t) </span>
<span style="font-family: courier new,courier;"> (setq ido-enable-flex-matching t) ;; enable fuzzy matching </span>
<span style="font-family: courier new,courier;"> ;; idomenu </span>
<span style="font-family: courier new,courier;"> (autoload 'idomenu "idomenu" nil t)</span></pre>

The typical things you can achieve with _**Ido**_ are:

  * easily switch between buffers with “<span style="font-family: courier new,courier;">C-x b</span>” (<span style="font-family: courier new,courier;">M-x ido-switch-buffer</span>), by just typing a few characters that from the buffer name. _**Ido**_ will interactively show in the <a title="Echo area @ The Emacs manual" href="http://www.gnu.org/software/emacs/manual/html_node/emacs/Echo-Area.html#Echo-Area" target="_blank">echo area</a> the buffer names matching the characters just typed.
  * similarly, you can easily find a file using “<span style="font-family: courier new,courier;">C-x C-f</span>” (<span style="font-family: courier new,courier;">M-x ido-find-file</span>)and then typing some characters appearing in the file name. _**Ido**_ will interactively list in the echo area the file names from the current directory that match the characters that you just typed.
  * in the same way, you can easily kill a buffer using <span style="font-family: courier new,courier;">&#8220;C-x k&#8221;</span> (<span style="font-family: courier new,courier;">M-x ido-kill-buffer</span>) and then typing some characters appearing in the buffer&#8217;s name.
  * I also use <a title="idomenu @ EmacsWiki" href="http://www.emacswiki.org/emacs/idomenu.el" target="_blank">idomenu.el</a>, which does the same trick to easily jump to any function or heading in the source code or text file in the buffer that you are currently editing.

But it is until recently that I noticed <a title="smex @ EmacsWiki" href="http://www.emacswiki.org/emacs/Smex" target="_blank">smex</a>.

<pre><span class="aligncenter" style="font-family: courier new,courier;">;; Smex</span><span class="aligncenter" style="font-family: courier new,courier;">(require 'smex)</span><span class="aligncenter" style="font-family: courier new,courier;">(smex-initialize)</span><span class="aligncenter" style="font-family: courier new,courier;">(global-set-key (kbd "M-x") 'smex)</span><span class="aligncenter" style="font-family: courier new,courier;">(global-set-key (kbd "M-X") 'smex-major-mode-commands)</span><span class="aligncenter" style="font-family: courier new,courier;">;; This is your old M-x.</span><span class="aligncenter" style="font-family: courier new,courier;">(global-set-key (kbd "C-c C-c M-x") 'execute-extended-command)</span></pre>

<a title="smex @ GitHub" href="https://github.com/nonsequitur/smex/" target="_blank"><em><strong>Smex</strong></em></a> is another fine Emacs package built on top of _**Ido**_ which helps with the two little actions that you need to perform when you don&#8217;t know or don&#8217;t remember the keyboard shortcut, namely, finding and typing the corresponding <span style="font-family: courier new,courier;">M-x command</span>. _**Smex**_ will do the following for you:

  * list in the echo area the <span style="font-family: courier new,courier;">M-x commands</span> that match the characters that you type as you type them.
  * And additionally, it shows the most recently used commands first, in case you need to invoked them again.

Those two little things combined save valuable time that you learn to appreciate very quickly because you are able to minimize your brain&#8217;s <a title="Human_multitasking @ Wikipedia" href="http://en.wikipedia.org/wiki/Human_multitasking" target="_blank">context switching</a> time, which is the most successful way of destroying a programmer&#8217;s focus.

Finally, there are a number of other packages that offer similar functionality:

  * <a title="iswitchb @ EmacsWiki" href="http://www.emacswiki.org/emacs/IswitchBuffers" target="_blank">iswitchb</a>: Among other things, this package provides <span style="font-family: courier new,courier;">M-x iswitch-kill-buffer</span> which does the same job as <span style="font-family: courier new,courier;">M-x ido-kill-buffer</span>.
  * <a title="icicles @ EmacsWiki" href="http://www.emacswiki.org/emacs/Icicles" target="_blank">icicles</a>: This package is similar in essence to _**Ido**_, however it is much more generic and big and the interface is a little bit different. Normally, you use one or the other but not both at the same time. I&#8217;ve tried it in the past, but I found its interface and general feeling less intuitive than _**Ido**_. However, I&#8217;m know this is because I didn&#8217;t give it enough time to completely adjust to its philosophy.

<br>
