---
layout: post
title: Exim - By The Numbers
author: Seanstoppable
category: <<CATEGORY>>
date: '<<DATE>>'
tags:
- cves
---

Recently, [CVE-2018-6789](https://www.cvedetails.com/cve/CVE-2018-6789/), a
remote code execution vulnerability for Exim made the rounds, and this was of
big concern due to the almost 5 million Exim servers exposed to the internet.
And since Exim is a mail server, it actually has to be publically available on
the internet.

A month later, where are we? Sadly, only ~178K of those detected Exim servers
are on 4.90.1, only ~3.6%%! That is, if we go by the raw version number. We
know that some distributions backport security fixes and so we have fixes on
[Debian Jessie and Stretch](https://www.debian.org/security/2018/dsa-4110) at
versions 4.84.2 and 4.89 respectively, and [Debian
Weezy](https://lists.debian.org/debian-lts-announce/2018/02/msg00009.html)
at version 4.80. Additionally, Ubuntu has [announced
fixes](https://usn.ubuntu.com/3565-1/) at versions 4.89, 4.86.2, and 4.82.

Those are the only references on CVEDetails though, so what about other distributions? Some have backports as well, such as [OpenSUSE](https://www.suse.com/security/cve/CVE-2018-6789/), which has a patch for 4.86.2. Others, such as
[Arch](https://security.archlinux.org/CVE-2018-6789), 
[Gentoo](http://www.linuxsecurity.com/content/view/211109/104/) and
[Fedora](https://bugzilla.redhat.com/show_bug.cgi?id=1543270) recommended
users upgrade to the latest version.

So, with those patches in mind, where are we at? This adds the potential of
another ~110K, bringing us to ~288K (5.76%). This does assume a few things,
namely that all those versions ARE patched. Which is a 38% error rate.
