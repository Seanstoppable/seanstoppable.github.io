---
layout: post
title: O'Reilly Security Conference
author: Sean
category: conference-writeup
date: '2016-11-08'
tags:
 - conferences
 - security
---

As previously mentioned, the first [O’Reilly Security
Conference](http://conferences.oreilly.com/security/network-data-security-ny)
just wrapped up in NYC. I opted to attend last minute and was glad I chose to, 
due to a number of really good conversations with other attendees.

Some of the highlights:

O'Reilly provided 'office hours' with most of the speakers, giving attendees
the opportunity to pick the brains on speakers. I took advantage of this to
sit down at a table with [Cory Doctorow](http://craphound.com/bio/), who was 
one of the keynote speakers. This ended up being people going around, 
introducing themselves and describing what they are up to. I described my 
current job at SecurityScorecard, to which  Cory expressed interest and thought 
it was pretty cool.

Had a great conversation with one of the guys from
[SourceClear](https://www.sourceclear.com/) about their work. They claim to
have a vulnerability that is 50% greater than the NIST Vulnerability
Database, accomplished by scanning Github for PRs related to security, as
well as using that data to find similar patterns. They have some interesting
scaling challenges, as they manually verify all the vulnerabilities. They
then use this data to let people scan their dependencies and get a list of
dependencies with vulnerabilities. We chatted about vulnerability databases
in general, as well as Mitre's occasional slowness in providing details.

Went to a great talk from [HackerOne](https://hackerone.com/) on [Hacker
Quantified
Security](http://conferences.oreilly.com/security/network-data-security-ny/public/schedule/detail/53296),
which went over some of the data they have collected from their bug bounties,
showing security trends from making this a bit more public. I talked to their
CTO about possibly working on an API where they can expose what companies are
running bug bounty programs, and perhaps some of the metrics that are already
available on their site.

Had a hallway conversation with one of the founders of
[Cobalt.io](https://cobalt.io/), a crowdsourcing pentest company, where they
match up pentesters to specific engagements, and wrap that in some management
and a good web platform. We talked about how security is becoming more and more
transparent, and how it might be interesting if companies were able to share a
subset of pentest results in a verifiable way.

Sat in on Jay Jacob's talk on [Security Data Beyond
Operations](http://conferences.oreilly.com/security/network-data-security-ny/public/schedule/detail/57312).
He went over some interesting things, like clustering security breaches by
industry, and not seeing any cross industry patterns, so much as patterns within
industries. He also went over Bitsight's recent research on [malware/torrent
correlation](https://www.bitsighttech.com/blog/torrents-good-bad-ugly).

Kelly Harrington from the Google Safe Browsing team gave a talk on their efforts
entitled
["Are we out of the woods? The current state of web malware"](http://conferences.oreilly.com/security/network-data-security-ny/public/schedule/detail/53427).
They have covered a number of these things in their blog, but it was nice to see
a talk that expands on the topics and pulls it all together.

There were two talks in particular where I was exposed to a lot of new
information.

The first was [Deriving actionable intelligence from spoofed domain
registrations](http://conferences.oreilly.com/security/network-data-security-ny/public/schedule/detail/53101)
where Kyle Ehmke from ThreatConnect went over some research where they observed
spikes in typosquat registration for domains that were later attacked. He went
over various ways in which they try to correlate some of the data to find out
more about attackers and related potentially malicious domains.

The second  was Dan Kaminsky's ['A technical dive into defensive
trickery'](http://conferences.oreilly.com/security/network-data-security-ny/public/schedule/detail/56203).
Prefaced with the comment 'I am tired of doing keynotes, let me tell you the
cool projects I am working on', and then went into a LOT of experiments in:
 * DDoS attacks, and how to better communicate around these events. He is
   experimenting with shipping a subset of netflow data to destination networks.
   You can check out some of this in his
   [overflowd](https://github.com/dakami/overflowd) project.
 * Crypto/TLS Deployment. Let's Encrypt makes this easier, but he suggests the
   easiest thing would probably be to [jump to full
   encryption](https://github.com/dakami/jfe), which is a wrapper that will
   act as a TLS wrapper on any port, and provision TLS certificates on the fly.
 * Data Loss Prevention. Experimentation in rate limiting data access through a
   proxy. Example was for querying password data at a rate of 7 requests/second.
   At that rate, querying for 500M users would take 2.26 years to exfiltrate the
   data.
 * Code Safety. How to protect end users from executing bad code. Experimenting
   with making it easy to sandbox every application, via VMs/docker and syscall
   firewalling.


