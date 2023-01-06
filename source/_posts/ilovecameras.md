---
title: How i pwned thousands of cameras around the internet
date: 2023-01-06 10:40:14
excerpt: I made a tool to automatically find and exploit cheap chinese cameras
tags: IOT
---

One day i was browsing around [shodan.io](https://shodan.io) and randomly stumbled upon the **faucet** search feature.

This is a feature that allows you to view the count of devices that match a search query and a selected attribute, sorted by number.

For example with the query `country:gr` and facet `port` i can see the most common ports in Greece.

![](/img/ilovecameras/faucet1.png)

With this, i decided to see what kind of devices are most popular in Greece using the `product` faucet.

![](/img/ilovecameras/faucet2.png)

Whoa, Hikvision IP cameras?

I expected something like Apache which actually comes 3rd but apparently there are over 25.000 Hikvision scanned by [shodan.io](https://shodan.io) in Greece.

If you know a thing or two about this manufacturer you can guess that this can't be a good situation, Hikvision is infamous for their vulnerability ridden firmware and are known to place intentional backdoors in their programs.

[https://ipvm.com/reports/hik-exploit](https://ipvm.com/reports/hik-exploit)

I wanted to see how many of these devices are online and actually vulnerable.

I started by searching for public exploits affecting Hikvision devices, i came across this one [https://watchfulip.github.io/2021/09/18/Hikvision-IP-Camera-Unauthenticated-RCE.html](https://watchfulip.github.io/2021/09/18/Hikvision-IP-Camera-Unauthenticated-RCE.html) and decided to start from here.

Since i made the tool there has been even more exploits disclosed which i plan to add when i get the chance.

I \*borrowed\* some code written for CVE-2021-36260 by bashis (legendary IOT hacker) and automated the process of getting hosts from [shodan.io](https://shodan.io) and checking each one for exploitability.

![](/img/ilovecameras/tool.png)

I implemented SOCKS5 proxies for anonymity and multi-threading for each session to decrease the time taken to check for exploits, all results get saved into an SQLite3 database for ease of access.

You can find more info on how to use this tool [here](https://github.com/TasosY2K/camera-exploit-tool)

After i completed some scans of certain countries and cities i was surprised to see the number of vulnerable devices still up.

The number was in the thousands.

I decided to throw in some more exploits in the mix since i was at it (TVT, Avtech) and as expected i got even more hits.

Funnily enough i came across alot of systems what were already exploited too!

My plan for this tool is to be made into a fully-featured IOT vulnerability scanner, anybody is welcome to contribute!