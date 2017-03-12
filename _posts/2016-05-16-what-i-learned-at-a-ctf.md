---
layout: post
title: What I Learned At My First CTF
author: Seanstoppable
category: security
date: '2016-05-16'
tags:
- ctf
- learning
---

The other day, my company ran a 'Capture The Flag' exercise, where developers 
attempted to complete a series of hacking challenges against a running server 
(set up by our Chief Research Officer).

The majority of the exercise revolved around application security, where the 
attacker would gain more and more information to gain further and further access.

To start, we were asked to identify what sofware the site was running. A quick 
look at the page source of the site showed the following:

```code
<meta name="generator" content="Drupal 7 (http://drupal.org)" />
```

making it easy to determine that the site was running Drupal. With that in hand, 
I was able to use [online scanning software](https://hackertarget.com/drupal-security-scan/) 
to identify the exact version was 7.31 (apparently contained in a changelog that 
is sitting accessible).

A quick search for ['Drupal 7.31 
cve'](https://search.yahoo.com/yhs/search?p=drupal+7.31+cve&ei=UTF-8&hspart=mozilla&hsimp=yhs-002) 
brought me to [Exploit DB](https://www.exploit-db.com/exploits/34992/) which 
handily contained a python script which allowed me to create an admin user in 
Drupal and log in to the server.

The next challenge was to try to identify users on the machine and passwords to 
things like databases. I spent a bunch of time poking around and trying to 
figure this out until I realized that Drupal, by default, allows content to be 
rendered as PHP. From the docs:

```
Body: where you put the text for the page. The "Input format" controls what 
code can go in the Body field. There are three default options: filtered HTML, 
PHP code, and full HTML.
```

With the ability to execute PHP, this made a few tasks pretty easy. I was able 
to leverage code execution to enumerate file paths on the server, and then 
open and render specific files. Of note was the settings.php file of Drupal to 
gather information on the database, as well as list the /home directory to learn 
more about some users.

The next step was to essentially obtain access to the machine itself, which 
I did not figure out in the time alloted, but I believe would build on the 
basis that I can potentially write files to the file system using PHP. Perhaps 
trying to add my own public key to a user's .ssh folder? Or perhaps trying to 
create a reverse shell? The next CTF will tell.
