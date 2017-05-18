---
layout: post
title: Hang Down Your Head And (Wanna)Cry
author: Seanstoppable
category: security-roundup
date: '2017-05-17'
tags:
- ransomware
---

WannaCry took the world by storm starting on Friday, and everyone blogged about
it. A ransomware that spread not by phishing, but via an internet worm compared
to worms of old including [Sasser, Slammer and
Conficker](https://nakedsecurity.sophos.com/2017/05/15/the-windows-worm-is-back-and-this-time-its-serious/).
Specifically, leveraging the 'DoublePulsar/ETERNALBLUE' exploit from the NSA
stash that ShadowBrokers released several weeks ago, to install a backdoor and
then execute the ransomware automatically.

You can read a full technical breakdown on the [Talos
Blog](http://blog.talosintelligence.com/2017/05/wannacry.html), as well as
[MalwareBytes](https://blog.malwarebytes.com/threat-analysis/2017/05/the-worm-that-spreads-wanacrypt0r/)
(who has also been [tracking the
infection](https://intel.malwaretech.com/botnet/wcrypt), 
and [Endgame Security](https://www.endgame.com/blog/wcrywanacry-ransomware-technical-analysis).

Interestingly, it looks like this was exploited earlier by a botnet to infect
[users with cryptocurrency
miners](https://arstechnica.com/security/2017/05/massive-cryptocurrency-botnet-used-leaked-nsa-exploits-weeks-before-wcry/), 
which may have actually limited some of the damage since this malware [closed
the vulnerable
port](https://www.proofpoint.com/us/threat-insight/post/adylkuzz-cryptocurrency-mining-malware-spreading-for-weeks-via-eternalblue-doublepulsar)
to prevent additional infections.

Microsoft is [pissed off at the
NSA](https://www.techdirt.com/articles/20170515/17581837372/microsoft-is-pissed-off-nsa-over-wannacry-attack.shtml)
for stockpiling exploits. While Microsoft quickly patched against this problem 2 
months ago, the fact that there are still so many  victims is unfortunate. 
It certainly doesn't help that certain users are 
[disabling Windows
Auto-update](https://www.troyhunt.com/dont-tell-people-to-turn-off-windows-update-just-dont/),
making it that much more likely for someone to be a victim of an exploit like
this, or the fact that [pirated versions of Windows are
prevalent](https://www.engadget.com/2017/05/15/pirated-windows-china-russia-wannacry/)
and don't necessarily receive software updates.

The EFF talks up this [patching
problem](https://www.eff.org/deeplinks/2017/05/why-patching-problem-makes-us-wannacry), 
pointing out that Microsoft eventually felt the need to upgrade EOL versions of
Windows (XP and Windows Server 2003 received emergency patches) as a large
number of organizations [still rely on these
versions](https://www.wired.com/2017/05/still-use-windows-xp-prepare-worst/),
including [medical systems with specialized
software](https://krebsonsecurity.com/2017/05/u-k-hospitals-hit-in-widespread-ransomware-attack/).
They then furthered it by pointing out all the un-upgradable software present in 
IoT devices, as well as mobile phones as older versions of Android are still in 
use with manufacturers not updating for older devices.

WannaCry wasn't without its bugs. One bug [failed to create unique bitcoin
wallets](https://arstechnica.com/security/2017/05/wcry-ransomware-worms-bitcoin-take-tops-70k-as-its-spread-continues/)
for each victim, allowing payments to be tracked easily. And then, of course,
was the kill switch, which was accidentally [activated when a malware researcher
tried to sinkhole
communications](https://www.malwaretech.com/2017/05/how-to-accidentally-stop-a-global-cyber-attacks.html).
However, this is not the end, with a number of copycats [emerging from the
woodwork](https://www.bleepingcomputer.com/news/security/with-the-success-of-wannacry-imitations-are-quickly-in-development/).

The ShadowBrokers have left commentary in the wake of WannaCry, suggesting that 
they are going to start [providing zero day dumps as a
service](https://threatpost.com/shadowbrokers-planning-monthly-exploit-data-dump-service/125710/) 
for exploits that were not part of April's massive leak, including additional 
Windows 10 vulnerabilities.

