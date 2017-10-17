---
id: 568
title: Source code browsing using GNU ID and Emacs
date: 2013-03-10T00:00:00+00:00
author: Juan Rubio
layout: post
guid: http://www.juanrubio.me/?p=568
permalink: /2013/03/howto-source-code-browsing-using-gnu-id-and-emacs/
categories:
  - Emacs
---
Source code comprehension programs are amongst the most important tools that every software developer needs to master. Using these tools in an integrated way from the comfort of you favourite editor is important to minimise the context switches that kill the developer&#8217;s productivity (you know, &#8220;[the zone](http://lifehacker.com/5920484/what-is-the-zone-anyway)&hellip;&#8221;). 

Here it is a short HowTo on how I use [GNU ID Utils](http://www.gnu.org/software/idutils/) from Emacs. This assumes some Linux/Debian derivative (in my case Ubuntu 12.04) and a C/C++ project, but other languages like Perl or Java are also supported by GNU ID. 

<div id="outline-container-1" class="outline-2">
  <h2 id="sec-1">
    Verify that the <code>id-utils</code> Debian package is installed
  </h2>
  
  <div class="outline-text-2" id="text-1">
    <pre class="brush: plain; light: true; title: ; notranslate" title="">
$ dpkg -l | grep id-utils
ii  id-utils  4.5-3  Fast, high-capacity, identifier database tool
</pre>
  </div>
  
  <div id="outline-container-1-1" class="outline-3">
    <h3 id="sec-1-1">
      Alternatively, install it
    </h3>
    
    <div class="outline-text-3" id="text-1-1">
      <pre class="brush: plain; light: true; title: ; notranslate" title="">
$ sudo apt-get install id-utils
</pre></p>
    </div>
  </div>
</div>

<div id="outline-container-2" class="outline-2">
  <h2 id="sec-2">
    Download <code>idutils.el</code> and put it somewhere in your Emacs search path
  </h2>
  
  <div class="outline-text-2" id="text-2">
    <p>
      The <code>idutils</code> source distribution comes with <code>idutils.el</code>, an Emacs interface to <code>gid</code>, the utility that comes with <code>idutils</code> and that let&#8217;s you query the ID database from the command line. At the time of writing, 4.6 is the latest version of the <code>idutils</code> package. However, it probably is safer to use the <code>idutils.el</code> from the same release as the <code>idutils</code> package installed on your system (in my case that is 4.5).
    </p>
    
    <pre class="brush: plain; light: true; title: ; notranslate" title="">
$ cd ~/temp
$ wget http://ftp.gnu.org/gnu/idutils/idutils-4.5.tar.xz
$ xz -d idutils-4.5.tar.xz
$ tar xvf idutils-4.5.tar
$ cp idutils-4.5/lisp/idutils.el "somewhere where emacs can find it"
</pre>
  </div>
</div>

<div id="outline-container-3" class="outline-2">
  <h2 id="sec-3">
    Update your Emacs config
  </h2>
  
  <div class="outline-text-2" id="text-3">
    <p>
      Add the following to your dotemacs file:
    </p>
    
    <pre class="brush: plain; light: true; title: ; notranslate" title="">
;; Emacs GNU ID utils interface
;; M-x gid to run the command
;; more info at http://www.gnu.org/software/idutils/manual/idutils.html
(autoload 'gid "idutils" nil t)
</pre>
  </div>
</div>

<div id="outline-container-4" class="outline-2">
  <h2 id="sec-4">
    Build the ID database
  </h2>
  
  <div class="outline-text-2" id="text-4">
    <p>
      The next step is to run <code>mkid</code> to build the identifier database. The following commands will produce an <code>ID</code> file in you project&#8217;s root directory. This will index your system headers as well as your project&#8217;s source code. E.g.:
    </p>
    
    <pre class="brush: plain; light: true; title: ; notranslate" title="">
$ cd "your favorite project"
$ mkid -s /usr/include/ .
</pre>
  </div>
</div>

<div id="outline-container-5" class="outline-2">
  <h2 id="sec-5">
    Run <code>gid</code> from within Emacs
  </h2>
  
  <div class="outline-text-2" id="text-5">
    <p>
      Open up any source file from your project, point your cursor at some identifier and run <code>M-x gid</code>. Emacs will ask you something like this:
    </p>
    
    <pre class="brush: plain; light: true; title: ; notranslate" title="">
Run gid (with args): thread_mutex_create
</pre>
    
    <p>
      Just hit enter and Emacs will bring up a <code>*compilation*</code> buffer with the results:
    </p>
    
    <pre class="brush: plain; light: true; title: ; notranslate" title="">
-*- mode: gid; default-directory: "/home/juanrubio/3rdparty/icecast/src/" -*-
Gid started at Wed Apr 10 12:57:01

gid thread_mutex_create
thread/thread.h:104:#define thread_spin_create(x)  thread_mutex_create(x)
thread/thread.h:111:#define thread_mutex_create(x) thread_mutex_create_c(x,__LINE__,__FILE__)
thread/thread.h:136:# define thread_mutex_create_c _mangle(thread_mutex_create)
auth.c:683:        thread_mutex_create (&amp;auth-&gt;lock);
cfgfile.c:94:    thread_mutex_create(&amp;_locks.relay_lock);
connection.c:147:    thread_mutex_create(&amp;move_clients_mutex);
format_mp3.c:122:    thread_mutex_create (&amp;state-&gt;url_lock);
global.c:45:    thread_mutex_create(&amp;_global_mutex);
slave.c:139:    thread_mutex_create (&amp;_slave_mutex);
source.c:106:        thread_mutex_create(&amp;src-&gt;lock);
stats.c:134:    thread_mutex_create(&amp;_stats_mutex);
stats.c:138:    thread_mutex_create(&amp;_global_event_mutex);
stats.c:864:    thread_mutex_create (&amp;(listener.mutex));
util.c:719:         thread_mutex_create (&amp;localtime_lock);
xslt.c:101:    thread_mutex_create(&amp;xsltlock);
yp.c:282:    thread_mutex_create (&amp;yp_pending_lock);
net/resolver.c:41:#define thread_mutex_create(x) do{}while(0)
net/resolver.c:206:        thread_mutex_create (&amp;_resolver_mutex);
thread/thread.c:164:    thread_mutex_create(&amp;_threadtree_mutex);
thread/thread.c:165:    thread_mutex_create(&amp;_library_mutex);    

Gid finished at Wed Apr 10 12:57:01
</pre>
    
    <p>
      The results can be navigated with the usual Emacs commands <code>M-x next-error</code> and <code>M-x previous-error</code>, (usually assigned to <code>M-g n</code> and <code>M-g p</code>)
    </p>
  </div>
</div>

<div id="outline-container-6" class="outline-2">
  <h2 id="sec-6">
    Similar tools
  </h2>
  
  <div class="outline-text-2" id="text-6">
    <p>
      There are a number of other source browsing/navigation tools that are specific for Emacs or that also integrate well with Emacs, some of them are:
    </p>
    
    <ul>
      <li>
        <a href="http://www.gnu.org/software/emacs/manual/html_node/emacs/Tags.html">Tags tables</a>
      </li>
      <li>
        <a href="http://cscope.sourceforge.net/">cscope/xcsope</a>
      </li>
      <li>
        <a href="http://www.gnu.org/software/emacs/manual/html_node/ebrowse/">ebwrose</a>
      </li>
      <li>
        <a href="http://cedet.sourceforge.net/">CEDET</a> and <a href="http://ecb.sourceforge.net/">ECB</a>
      </li>
    </ul>
  </div>
</div>

<div id="outline-container-7" class="outline-2">
  <h2 id="sec-7">
    References
  </h2>
  
  <div class="outline-text-2" id="text-7">
    <ul>
      <li>
        <a href="http://www.gnu.org/software/idutils/manual/idutils.html">http://www.gnu.org/software/idutils/manual/idutils.html</a>
      </li>
      <li>
        <a href="http://emacswiki.org/emacs/IdUtils">http://emacswiki.org/emacs/IdUtils</a>
      </li>
      <li>
        <a href="http://directory.fsf.org/wiki/Idutils">http://directory.fsf.org/wiki/Idutils</a>
      </li>
    </ul>
  </div>
</div>

<br>
