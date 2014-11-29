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

    ./fuckchina and tw

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

Examples
========

Do not block chinese addresses, but taiwan

    ./fuckchina not but tw

Block known hackers, but not libya

    ./fuckchina and hackers but not libya

Be hardcore, block 'em all

    ./fuckchina and spammers and hackers

Copyright
=========

fuckchina is copyrighted 2014 by Heiko Irrgang

It is available under GPL v3 license, see LICENSE

This product includes GeoLite2 data created by MaxMind, available from
<a href="http://www.maxmind.com">http://www.maxmind.com</a>.
