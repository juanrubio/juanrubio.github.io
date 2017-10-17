---
id: 288
title: Khronos releases OpenMAX IL 1.2 as a provisional spec
date: 2012-02-17T22:30:13+00:00
author: Juan Rubio
layout: post
guid: http://www.juanrubio.me/?p=288
permalink: /2012/02/khronos-releases-openmax-il-1-2-as-a-provisional-spec/
categories:
  - Multimedia
  - OpenMAX IL
tags:
  - Khronos
  - Multimedia
  - OpenMAX IL
---
<div id="yass_top_edge_dummy" style="width: 1px; height: 1px; padding: 0px; margin: -11px 0px 0px; border-width: 0px; display: block;">
</div>

<div id="yass_top_edge" style="background-image: url('chrome://yass/content/edgebgtop.png'); background-attachment: scroll; background-position: center bottom; padding: 0px; margin: 0px 0px 10px -386px; border-width: 0px; height: 0px; display: block; width: 1px;">
</div>

<p style="margin-top: 10px;">
  The <a title="The Khronos Group" href="http://www.khronos.org/" target="_blank">Khronos Group</a> yesterday <a title="OpenMAX IL 1.2 provisional spec announcement" href="http://www.khronos.org/news/archives/khronos-group-releases-openmax-il-1.2-provisional-specification" target="_blank">announced</a> the public release of the new version of the OpenMAX IL specification (version 1.2.0), the open standard, cross-platform, C-language based API for multimedia hardware acceleration.
</p>

The OpenMAX Working Group was created by Khronos in 2004, with three sub-groups, OpenMAX AL (Application Layer), OpenMAX IL (Integration Layer), and OpenMAX DL (Development Layer). OpenMAX IL sits architecturally <a title="OpenMAX overview" href="http://www.khronos.org/openmax/" target="_blank">in the middle of the OpenMAX stack</a>. Although complementary, these three APIs have been arquitected to be independent of each other, so that they can live in a system without any of its siblings.

Until yesterday, the latest and greatest version of the OpenMAX IL specification was 1.1.2, which was released in September 2008.

The OpenMAX IL standard is well known amongst the Multimedia software community as a lengthy, cumbersome API. This new specification is an attempt by the Khronos OpenMAX IL Working Group to address some of the shortcomings and issues reported by implementers during the past few years.

From an architectural point of view, the new release does an attempt to break as little as possible with the past, to avoid giving OpenMAX IL developers additional headaches. However, this won&#8217;t necessarily be the case for every IL implementation out there, as there are still enough relevant changes in this new version of the spec to _keep **entertained** those developers with responsibilities in existing implementations**.**_ However, in my opinion, it is all for good.**
  
** 

Without going into the detail, I would highlight the following changes as the most relevant in my view:

  * Those changes related to the _**&#8220;buffer pre-announcement feature&#8221;**_ in IL.
  * This is something that has traditionally caused troubles to IL Client developers and integrators of OpenMAX IL components in multimedia frameworks. The issue here has typically been the difficulties of reusing framework-allocated buffers inside IL. The new version of the spec relaxes some of the limitations in this area while still maintaining the &#8220;old ways&#8221;, in case someone is concerned about backwards compatibility.

  * The various updates to the IL **_state machine._**
  * The IL state machine has been <a title="Discussion on OpenMAX IL integration challenges @ Linaro" href="https://wiki.linaro.org/Events/2011-06-MMWG/OpenMaxIntegration" target="_blank">criticized</a> in many occasions due its size and complexity. The IL state machine hosts a large number of states (6 in total) and the reality is that it is difficult to find many implementations that support all of them. But more importantly, problems in the state machine (or alternatively, in the language that described it) have been identified in the past, especially in scenarios with tunneled components. These problems have the potential to cause a number of issues that are collectively known as the &#8220;IL race conditions&#8221;.
  * In general, the IL state machine has been improved in this new spec by rewriting the sections that dealt with the state transitions and the conditions that triggered them, the removal of the &#8220;<span style="font-family: courier new,courier;">OMX_StateInvalid</span>&#8221;  state, and the addition of a number of conditions to achieve &#8220;_**command cancellation**_&#8220;, which is something that wasn&#8217;t possible in previous versions of the IL spec.

But what it is really important here in my opinion, is that Khronos has <a title="Khronos OpenMAX IL registry" href="http://www.khronos.org/registry/omxil/" target="_blank">published</a> this new spec as _**provisional**_, and has setup a <a title="Discussion forum - OpenMAX IL 1.2 provisional spec" href="http://www.khronos.org/message_boards/viewforum.php?f=58" target="_blank">public forum</a> for developers to discuss and/or provide feedback. To my knowledge, this is the first time that Khronos has done something similar with a specification. This is in my opinion a great initiative which has the potential to make the final spec a better one by <a title="OpenMAX: a rant, by Victor Jaquez" href="http://blogs.igalia.com/vjaquez/2011/11/29/openmax-a-rant/" target="_blank">opening the discussion</a> to a wider community of developers.

From a personal point of view, I&#8217;m very happy to see that this new spec is finally out, as I had the great honor of collaborating with the Khronos IL WG between 2008 and 2011, during the time I worked for Symbian and Nokia. All in all, I can only say big kudos to the IL WG!

You can read more about the new specification and its improved capabilities in the Khronos  <a title="OpenMAX IL 1.2 provisional spec press release" href="http://www.khronos.org/news/press/khronos-group-releases-openmax-il-1.2-provisional-specification" target="_blank">press release</a>.