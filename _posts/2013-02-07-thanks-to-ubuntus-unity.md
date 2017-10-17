---
id: 459
title: 'Thanks to Ubuntu&#8217;s Unity'
date: 2013-02-07T00:00:00+00:00
author: Juan Rubio
excerpt: With the advent of the Unity shell in Ubuntu 11.04 and the Gnome 3 in 11.10, I and, I believe, many other Ubuntu users started to look around for a window manager replacement that we could use to continue doing development work properly and without feeling that our productivity was compromised. This is how I came to know the Awesome Window Manager. I really thank Ubuntu for shipping that painfully slow version of Unity in April 2011. The adoption of Awesome has been the most productive change in my developer workflow since I discovered Emacs org-mode back in 2007.
layout: post
guid: http://www.juanrubio.me/?p=459
permalink: /2013/02/thanks-to-ubuntus-unity/
categories:
  - Linux
  - Open Source Software
tags:
  - Awesome Window Manager
  - Gnome
  - Linux
  - Ubuntu
  - Unity
---
With the advent of the Unity shell in Ubuntu [11.04](https://wiki.ubuntu.com/NattyNarwhal/ReleaseNotes) (Natty) and the Gnome 3 shell in [11.10](https://wiki.ubuntu.com/OneiricOcelot/ReleaseNotes) (Oneiric), I and, I believe, [many other Ubuntu users](http://royal.pingdom.com/2011/11/23/ubuntu-linux-losing-popularity-fast-new-unity-interface-to-blame/), started to look around for a window manager replacement that we could use to continue doing development work properly and without feeling that our productivity was compromised.

This is how I came to know the [Awesome Window Manager](http://awesome.naquadah.org/). I really thank Ubuntu for shipping that painfully slow version of Unity in April 2011. The adoption of Awesome has been the most productive change in my developer work-flow since I discovered Emacs [org-mode](http://orgmode.org/) back in 2007.

![./awesome.png](http://www.juanrubio.me/wp-content/uploads/2013/03/wpid-awesome.png)

<div class="outline-2" id="outline-container-1">
  <h2 id="sec-1">
    What is Awesome WM
  </h2>
  
  <div class="outline-text-2" id="text-1">
    <p>
      Awesome falls into the category of <a href="http://en.wikipedia.org/wiki/Tiling_window_manager">tiling window managers</a>. The project was started in 2007 by <a href="http://julien.danjou.info/projects/">Julien Danjou</a>, who according to Wikipedia, started it as a fork of <a href="http://dwm.suckless.org/">dwm</a>, another tiling window manager. For hard-core Emacs users, Awesome is probably one of the best choices of window manager out there. Simply because the window manager keyboard shortcuts do not interfere with those from Emacs and actually seem like a natural fit for people like me that like to have complete control from the keyboard with a minimal use of the mouse.
    </p>
  </div>
</div>

<div class="outline-2" id="outline-container-2">
  <h2 id="sec-2">
    Pros/Cons
  </h2>
  
  <div class="outline-text-2" id="text-2">
    <p>
      This is a very personal summary of what things I like and dislike about Awesome WM.
    </p>
  </div>
  
  <div class="outline-3" id="outline-container-2-1">
    <h3 id="sec-2-1">
      Pros:
    </h3>
    
    <div class="outline-text-3" id="text-2-1">
      <ol>
        <li>
          Very minimal, no clutter, tiny top panel that stays our of your way and maximises screen real state.
        </li>
        <li>
          Large number of workspaces (a.k.a &#8216;tags&#8217; in Awesome WM speak). The default is 9.
        </li>
        <li>
          Very stable. Almost two years of daily use, and I don&#8217;t remember it crashing on me or having to restart it. One of the advantages or being minimalistic.
        </li>
        <li>
          High performance (this WM is really minimal), switching between workspaces/windows with 0 lag; the desktop loads immediately after the login screen (because there&#8217;s not a lot to load really). No silly 3D effects. It is perfect for running on virtual machines.
        </li>
        <li>
          Default keyboard shortcuts do not interfere with (my) Emacs key bindings thanks to Awesome using the Windows key as trigger.
        </li>
        <li>
          Everything can be done from the keyboard. Jumping between workspaces, selecting windows (a.k.a &#8216;clients&#8217; in Awesome WM speak), transferring windows to other workspaces (a.k.a. &#8216;tags&#8217; in Awesome WM speak), switching between tile layouts, changing window positions and sizes, starting terminals and programs, closing windows, putting windows on top, maximising, minimising, etc.
        </li>
        <li>
          No hassle installation in Debian derivatives with <code>sudo apt-get install awesome</code>.
        </li>
        <li>
          Minimal/no configuration out of the box that gets things working from minute 0. Multiple screens work out of the box at least in Ubuntu.
        </li>
      </ol>
    </div>
  </div>
  
  <div class="outline-3" id="outline-container-2-2">
    <h3 id="sec-2-2">
      Cons
    </h3>
    
    <div class="outline-text-3" id="text-2-2">
      <ol>
        <li>
          Additional configuration/personalisation requires tinkering with Lua scripts, which I don&#8217;t mind since I don&#8217;t care about the looks of the desktop.
        </li>
        <li>
          You need to memorise a basic subset of keyboard combinations from day 1. Not a problem if you are an avid Emacs user like me.
        </li>
        <li>
          No volume widget. Keyboard multimedia keys do not work out of the box (more on that later).
        </li>
      </ol>
    </div>
  </div>
</div>

<div class="outline-2" id="outline-container-3">
  <h2 id="sec-3">
    Keyboard shortcuts
  </h2>
  
  <div class="outline-text-2" id="text-3">
    <p>
      This is the subset of the window manager shortcuts that I use most frequently, and that I believe are minimal to be productive in this type of environment (NOTE: Mod4 is the Windows key on a normal PC keyboard).
    </p>
    
    <table border="2" frame="hsides" rules="groups" cellspacing="0" cellpadding="6">
      <caption> </caption> <colgroup> <col class="left" /> <col class="left" /> <col class="left" /> </colgroup> <tr>
        <th class="left" scope="col">
          Starting/closing things
        </th>
        
        <th class="left" scope="col">
          Function
        </th>
        
        <th class="left" scope="col">
          Comment
        </th>
      </tr>
      
      <tr>
        <td class="left">
          <code>Mod4 + Return</code>
        </td>
        
        <td class="left">
          Spawn terminal
        </td>
        
        <td class="left">
          This is so intuitive you will want to do it in other window managers
        </td>
      </tr>
      
      <tr>
        <td class="left">
          <code>Mod4 + r</code>
        </td>
        
        <td class="left">
          Run command
        </td>
        
        <td class="left">
          A tiny command prompt appears at the top panel near the left corner
        </td>
      </tr>
      
      <tr>
        <td class="left">
          <code>Mod4 + Shift + c</code>
        </td>
        
        <td class="left">
          Close focused window
        </td>
        
        <td class="left">
          Need to be careful as sometimes it is difficult to discern which one is the focused window
        </td>
      </tr>
    </table>
    
    <table border="2" frame="hsides" rules="groups" cellspacing="0" cellpadding="6">
      <caption> </caption> <colgroup> <col class="left" /> <col class="left" /> <col class="left" /> </colgroup> <tr>
        <th class="left" scope="col">
          Maximixing/Minimizing
        </th>
        
        <th class="left" scope="col">
          Function
        </th>
        
        <th class="left" scope="col">
          Comment
        </th>
      </tr>
      
      <tr>
        <td class="left">
          <code>Mod4 + m</code>
        </td>
        
        <td class="left">
          Maximize/restore windows
        </td>
        
        <td class="left">
          Ditto
        </td>
      </tr>
      
      <tr>
        <td class="left">
          <code>Mod4 + n</code>
        </td>
        
        <td class="left">
          Minimize windows
        </td>
        
        <td class="left">
          Ditto
        </td>
      </tr>
      
      <tr>
        <td class="left">
          <code>Mod4 + Ctrl + n</code>
        </td>
        
        <td class="left">
          Restore a minimized window
        </td>
        
        <td class="left">
          This one takes a bit of time to remember as it is not so intuitive
        </td>
      </tr>
      
      <tr>
        <td class="left">
          <code>Mod4 + f</code>
        </td>
        
        <td class="left">
          Set window full screen
        </td>
        
        <td class="left">
          The window is all over the screen, the top level panel disappears
        </td>
      </tr>
      
      <tr>
        <td class="left">
          <code>Mod4 + t</code>
        </td>
        
        <td class="left">
          Set window on top
        </td>
        
        <td class="left">
          Ditto
        </td>
      </tr>
    </table>
    
    <table border="2" frame="hsides" rules="groups" cellspacing="0" cellpadding="6">
      <caption> </caption> <colgroup> <col class="left" /> <col class="left" /> <col class="left" /> </colgroup> <tr>
        <th class="left" scope="col">
          Workspaces
        </th>
        
        <th class="left" scope="col">
          Function
        </th>
        
        <th class="left" scope="col">
          Comment
        </th>
      </tr>
      
      <tr>
        <td class="left">
          <code>Mod4 + j (k)</code>
        </td>
        
        <td class="left">
          Focus next (previous) window
        </td>
        
        <td class="left">
          Ditto
        </td>
      </tr>
      
      <tr>
        <td class="left">
          <code>Mod4 + Left (Right)</code>
        </td>
        
        <td class="left">
          Switch to left (right) workspace
        </td>
        
        <td class="left">
          Ditto
        </td>
      </tr>
      
      <tr>
        <td class="left">
          <code>Mod4 + 1-9</code>
        </td>
        
        <td class="left">
          Switch to workspace 1-9
        </td>
        
        <td class="left">
          Ditto
        </td>
      </tr>
      
      <tr>
        <td class="left">
          <code>Mod4 + Shift + 1-9</code>
        </td>
        
        <td class="left">
          Move focused window to workspace 1-9
        </td>
        
        <td class="left">
          Ditto
        </td>
      </tr>
    </table>
    
    <table border="2" frame="hsides" rules="groups" cellspacing="0" cellpadding="6">
      <caption> </caption> <colgroup> <col class="left" /> <col class="left" /> <col class="left" /> </colgroup> <tr>
        <th class="left" scope="col">
          Layouts
        </th>
        
        <th class="left" scope="col">
          Function
        </th>
        
        <th class="left" scope="col">
          Comment
        </th>
      </tr>
      
      <tr>
        <td class="left">
          <code>Mod4 + Space</code>
        </td>
        
        <td class="left">
          Switch to next layout
        </td>
        
        <td class="left">
          Ditto
        </td>
      </tr>
      
      <tr>
        <td class="left">
          <code>Mod4 + Shift + Space</code>
        </td>
        
        <td class="left">
          Switch to previous layout
        </td>
        
        <td class="left">
          Ditto
        </td>
      </tr>
    </table>
    
    <table border="2" frame="hsides" rules="groups" cellspacing="0" cellpadding="6">
      <caption> </caption> <colgroup> <col class="left" /> <col class="left" /> <col class="left" /> </colgroup> <tr>
        <th class="left" scope="col">
          Multiple screens
        </th>
        
        <th class="left" scope="col">
          Function
        </th>
        
        <th class="left" scope="col">
          Comment
        </th>
      </tr>
      
      <tr>
        <td class="left">
          <code>Mod4 + Ctrl + j (k)</code>
        </td>
        
        <td class="left">
          Focus next (previous) screen
        </td>
        
        <td class="left">
          Really handy in a multi-monitor setup
        </td>
      </tr>
      
      <tr>
        <td class="left">
          <code>Mod4 + o</code>
        </td>
        
        <td class="left">
          Send window to next screen
        </td>
        
        <td class="left">
          Ditto
        </td>
      </tr>
    </table>
  </div>
</div>

<div class="outline-2" id="outline-container-4">
  <h2 id="sec-4">
    Multiple screens
  </h2>
  
  <div class="outline-text-2" id="text-4">
    <p>
      In Awesome, by the default the second monitor acts as an independent screen with its own set of workspaces (tags). So with two monitors, you effectively get 18 independent workspaces. This is interesting because you can switch workspaces independently in each monitor, which is probably not the behaviour most people would expect. In my case, this feature is actually very desirable, but other people might find this a bit disconcerting.
    </p>
  </div>
</div>

<div class="outline-2" id="outline-container-5">
  <h2 id="sec-5">
    Customising
  </h2>
  
  <div class="outline-text-2" id="text-5">
    <p>
      I never cared very much about the looks of the Linux desktop, so I&#8217;m not really into <a href="http://awesome.naquadah.org/wiki/User_Configuration_Files">customizing</a> Awesome. But sometimes it is necessary to adjust a few things.
    </p>
    
    <p>
      Awesome WM can be customised by modifying a Lua script named <code>rc.lua</code> that is read at startup. The file is expected to be located at one of the following directories, in this order:
    </p>
    
    <ul>
      <li>
        <code>$XDG_CONFIG_HOME/awesome/rc.lua</code>
      </li>
      <li>
        <code>$HOME/.config/awesome/rc.lua</code>
      </li>
      <li>
        <code>XDG_CONFIG_DIRS/awesome/rc.lua</code>
      </li>
    </ul>
    
    <p>
      In my system, I could find an example <code>rc.lua</code> in this location:
    </p>
    
    <pre class="brush: bash; title: ; notranslate" title="">
/usr/share/awesome/lib/shifty/example.rc.lua
</pre>
  </div>
  
  <div class="outline-3" id="outline-container-5-1">
    <h3 id="sec-5-1">
      Getting the multimedia keys to work
    </h3>
    
    <div class="outline-text-3" id="text-5-1">
      <p>
        I&#8217;m used to changing volume using the multimedia keys of my keyboard. There is no default configuration in Awesome to do this so it is necessary to add a bit code in Awesome&#8217;s <code>rc.lua</code> script to make it work. The following is an example on how to bind the multimedia keys to do this type of things:
      </p>
      
      <pre class="brush: bash; title: ; notranslate" title="">
awful.key({}, "XF86AudioRaiseVolume", function () awful.util.spawn("pactl -- set-sink-volume 1 +10%") end),
awful.key({}, "XF86AudioLowerVolume", function () awful.util.spawn("pactl -- set-sink-volume 1 -10%") end),
awful.key({}, "XF86AudioMute", function () awful.util.spawn("/home/joni/work/tools/bin/pa-vol.sh mute") end),
awful.key({}, "XF86Mail", function () awful.util.spawn("thunderbird") end),
awful.key({}, "XF86HomePage", function () awful.util.spawn("nautilus /home/joni") end),
awful.key({}, "XF86Messenger", function () awful.util.spawn("skype") end),
awful.key({}, "XF86Document", function () awful.util.spawn("libreoffice") end),
awful.key({}, "XF86Favorites", function () awful.util.spawn("firefox") end),
</pre>
      
      <ul>
        <li>
          Increasing/decreasing the volume is done with <b>Pulseaudio&#8217;s</b> <code>pactl</code> command line utility, that allows the control of a running Pulseaudio server.
        </li>
        <li>
          Muting with Pulseaudio is a bit more complicated, but I found a <a href="http://blog.waan.name/pulseaudio-setting-volume-from-command-line/">handy script</a> that makes use of the same ~<a href="http://manpages.ubuntu.com/manpages/lucid/man1/pactl.1.html">pactl</a>~ utility in combination with <code>padump</code> to achieve the effect of muting and unmuting a specific Pulseaudio sink from the command line. Just needed to make sure that the script would use the right Pulseaduio sink for my system. <code>pacmd list-sinks</code> is one tool that can be used to list Pulseaudio sinks available in a system.
        </li>
        <li>
          I dont&#8217; use other keys like play, stop, next or previous, but other people <a href="http://wiki.gentoo.org/wiki/Awesome">bind</a> them to control <a href="http://mpd.wikia.com/wiki/Music_Player_Daemon_Wiki">MPD</a> as a backend player.
        </li>
      </ul>
    </div>
  </div>
  
  <div class="outline-3" id="outline-container-5-2">
    <h3 id="sec-5-2">
      Start up programs
    </h3>
    
    <div class="outline-text-3" id="text-5-2">
      <p>
        Finally, there are those programs that you need to start every time you log in your system. So I decided to add those to the Awesome&#8217;s config to <a href="#awesome.naquadah.org-wiki-Autostart">auto-start</a> them on every session.
      </p>
      
      <pre class="brush: bash; title: ; notranslate" title="">
awful.util.spawn_with_shell("/usr/bin/radiotray")
awful.util.spawn_with_shell("/usr/bin/hp-systray")
awful.util.spawn_with_shell("/usr/bin/quicksynergy")
awful.util.spawn_with_shell("/home/joni/bin/emacsorg")
awful.util.spawn_with_shell("/home/joni/bin/emacstiz")
awful.util.spawn(terminal)
awful.util.spawn(terminal)
awful.util.spawn("/usr/bin/nautilus")
awful.util.spawn("/usr/bin/firefox")
</pre>
    </div>
  </div>
</div>

<div class="outline-2" id="outline-container-6">
  <h2 id="sec-6">
    Other tiling window managers
  </h2>
  
  <div class="outline-text-2" id="text-6">
    <p>
      Currently Awesome is ticking all the boxes for me but I&#8217;ve also heard good things about <a href="http://xmonad.org/">xmonad</a>. Some people have blogged <a href="http://misspent.wordpress.com/2010/10/06/the-tiling-chronicles-from-xmonad-to-awesome-to-wmii/">comparisons</a> between these two, but so far my impression is that that there is no clear winner, so this might be an interesting test to do in the future.
    </p>
  </div>
</div>

<br>
