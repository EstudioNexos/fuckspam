What?
=====

fuckchina is a Python script that helps you significantly reduce Spam and
Hack attempts to your servers by using the GeoIP database from
MaxMind (see below) to block certain countries.

It provides one preset of spammer countries and is easy to use.

Why?
====

I am running an WordPress blog site which received several thousand spam
entries per day after only a few days of being live.

A test showed, that at least 99% of that spam entries came from IP addresses
from China. A very basic version of this script filtered out only chinese
addresses and by this i was able to reduce the spam level from several thousand
a day to only half a dozend.

The remaining half a dozend also came from only a few different countries.

How?
====

Download the software and uncompress somewhere. Make sure the script is
runnable by:

    chmod +x ./fuckspam
    
(alternatively you could run it using the python interpreter)

If you just want to add chinese IP addresses, all you have to do is:

    sudo ./fuckspam

Answer yes to actually add the IP addresses to the firewall.

To list supported countries, call:

    ./fuckspam --list

You can specify short or long codes (use double quote if long country
name has spaces), here we block china and taiwan:

    sudo ./fuckspam and tw

... the use of the 'and' keyword is optional for better readability

To check the help, call:

    ./fuckspam --help

Presets
=======

The script provides 1 preset that you can add instead of country names:

 * spammers - well known spamming countries


To list countries in a preset, use:

    ./fuckspam --list presetname

These presets are made on my personal experience and are neither a representative
list of spamming or hacking countires nor matter of discussion, so if you disagree
or don't like them, i have a very simple solution for you: <em>don't use them</em>.

Examples
========

Do not block chinese addresses, but taiwan

    sudo ./fuckspam not but tw

Block known spammers, but not libya

    sudo ./fuckspam and spammers but not libya

Be hardcore, block 'em all (hackers preset currently doesn't exist)

    sudo ./fuckspammers and spammers and hackers

Warning
=======

This script may add many thousand entries into your systems iptable list, it may
affect you systems performance if you add too many countries.

Before adding them, it tells you how many it will add, so you can decide if you
really want to do this.

It creates a custom chain named **fuckspam** so you can easily remove the rules
again.

Notes
=====

Main developer Heiko Irrgang, though he made a good job with this script, the usage of potentially offensive language and code naming made me feel unease when forking to add ipv6 support and update csv files format. That is why I renamed this project to **fuckspam**

This fork supports ip v4 and v6 addresses.

This fork support latest MaxMind GeoLite2 releases.

This fork has only one preset based on my experience with a dozen of servers, both web and mail servers.

Future development will add support for presets stored in yaml files that can be loaded when calling the script.


Copyright
=========

Copyright 2014 Heiko Irrgang

Copyright 2017 Nestor Diaz Valencia

This software is licensed under GPL v3 license, see LICENSE

This product includes GeoLite2 data created by MaxMind, available from
<a href="http://www.maxmind.com">http://www.maxmind.com</a>.
