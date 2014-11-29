What?
=====

fuckchina is a Python script that helps you significantly recude spam and
hack attempts to your servers by using the GeoIP database from
MaxMind (see below) to block certain countries.

It provides useful presets of known hackers and spammers and is easy to use.

Why?
====

I am running an WordPress blog site which received several thousand spam
entries after only a few days of being live.

A test showed, that at least 99% of that spam entries came from IP addresses
from China. A very basic version of this script filtered out only chinese
addresses and by this i was able to reduce the spam level from several thousand
a day to only half a dozend.

The remaining half a dozend also came from only a few differnt countries.

How?
====

Download the software and uncompress somewhere. Make sure the script is
runnable by:

    chmod +x ./fuckchina

(alternatively you could run it using the python interpreter)

If you just want to add chinese IP addresses, all you have to do is:

    sudo ./fuckchina

Answer yes to actually add the IP addresses to the firewall.

To list supported countries, call:

    ./fuckchina --list

You can specify short or long codes (use double quote if long country
name has spaces), here we block china and taiwan:

    sudo ./fuckchina and tw

... the use of the 'and' keyword is optional for better readability

To check the help, call:

    ./fuckchina --help

Presets
=======

The script provides 3 presets that you can add instead of country names:

 * spammers - well known spamming countries

 * hackers - well known hacking countries

 * allspam - preset spammers + countries that are known to occassionally send spam

At the moment there is no way to list the presets (this will change), so you have
to display the script with an editor to see and/or modify which countries are in
these presets.

These presets are made on my personal experience and are neither a representative
list of spamming or hacking countires nor matter of discussion, so if you disagree
or don't like them, i have a very simple solution for you: <em>don't use them</em>.

Examples
========

Do not block chinese addresses, but taiwan

    sudo ./fuckchina not but tw

Block known hackers, but not libya

    sudo ./fuckchina and hackers but not libya

Be hardcore, block 'em all

    sudo ./fuckchina and spammers and hackers

Warning
=======

This script may add many thousand entries into your systems iptable list, it may
affect you systems performance if you add too many countries.

Before adding them, it tells you how many it will add, so you can decide if you
really want to do this.

It creates a custom chain named **fuckchina** so you can easily remove the rules
again.

Copyright
=========

Copyright 2014 Heiko Irrgang

This software is licensed under GPL v3 license, see LICENSE

This product includes GeoLite2 data created by MaxMind, available from
<a href="http://www.maxmind.com">http://www.maxmind.com</a>.
