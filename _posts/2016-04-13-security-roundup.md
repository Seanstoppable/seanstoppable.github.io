---
layout: post
title: Security Roundup 2016-04-13
author: Sean
date: '2016-04-13'
tags:
- security
- roundup
---

Ever heard the story where an attacker can compromise a site just by leaving some USB keys around? Elie decided to put these to the test and found that 48% of users will plug in a drive and open a file. 20% of the drives were connected in the first hour, the first being connected and a file opened within 6 minutes of the experiment starting.

Who phishes the phishers? PhishMe posts about a CEO wire transfer fraud attack directed at them, and how they decided to deal with it. Phishing a phishing defense company? Probably not the greatest idea.

Google just published a paper on their 'trust nothing' policy, where trust nothing means also not trusting internal networks. This means that attackers that make it past the perimeter still have to deal with a hard, crunchy interior. The Registry has a nice summary.

An interesting article on how Bitcoin is not entirely anonymous. By monitoring the entire blockchain and grouping transactions together, you can actually figure out what services an individual is using, which could lead to services being able to refuse funds from users based on activity.

Talos Intel provides an informative write up of the 'Past, Present and Future of Ransomeware'. The future? Moving from phishing payloads to becoming worms targeting internal vulnerabilities and/or other malware to propagate through networks. Checkpoint has an interesting perspective where they view Ransomeware as increasing rapidly, with the previously lucrative banking trojans on a decline. Ransomeware is proving to be much simpler to develop vs banking trojans which have to be customized for specific banks, thus allowing them to reach a larger audience of victims.

Locky, unsurprisingly, continues to evolve. Newest changes include a more robust Domain Name Generation (DGA) algorithm to avoid detection of outbound communications, saving data in random registry keys to avoid detection, and additional code obfuscation.

Several high profile sites, such as the New York Times and the BBC have been impacted by Malvertising. A classic third party attack where bad actors use ad networks to inject hostile payloads into sites. Checkpoint has a brief history. 
