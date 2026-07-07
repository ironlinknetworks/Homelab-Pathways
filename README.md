# Homelab-Pathways
*Want to break into IT⁉️ Don't know where to start⁉️* With this quick guide, you can get started with your own home lab with **simple, easy to use hardware and software** that will help you get started on your journey. If you're and experienced IT pro and want some nice everyday locally hosted services, feel free to use this guide as well.

You can own your own data and services without paying a subscription and without sacrificing your privacy. Follow the projects below to improve your overall Privacy and security in this modern era ‼️

“Bene vixit, bene qui latuit." (To live well is to live concealed.) - OVID

“The only privacy that’s left is the inside of your head. Maybe that’s enough.” – George Orwell

This guide walks through a rough development of my own personal homelab and the steps I've taken to stop paying subscriptions and take back control of my data. I started my IT education in 2021 shortly before getting a job in data analytics and coding using SAS and SQL and simulataneously studying for the Comptia Security+ certification. I started building out homelab components to enhance my knowledge in the field and gain an understanding of how role based permissions work, how networking concepts work in practice, and discover what is needed for all of the services we use everyday. Another big reason I like hosting my own services is the customization and increased security, data ownership, and the ability to cut free services which harvest my data and subscription services that harvest my hard earned money. I will also like to many of the tools, programs, and creators I trust and respect in the industry along with free and open resources you can use today to build out your own systems.

## Table of Contents
1. [Getting Started](getting-started)
2. [Pihole](pihole) - Block trackers and protect your privacy with this simple DNS project
3. [VPN Recommendations](vpn-recommendations) - Protect all your devices on your network and your phone on your phone on your daily travels
4. [Home Networking Equipment](home-networking-equipment) - Customized devices to improve connectivity, security, and privacy across your home
5. [Mini PC](mini-pc) - Great place to start for home services
6. [Home NAS](home-nas) - Tired of paying for cloud services and subscriptions? Take a look at a home NAS.
7. [Travel Routers](travel-routers) - Frequent flyer? Use one of these to protect yourself and your business when traveling.
8. [Getting Started with different Services](getting-started-with-different-services) - What would I even want to run on a home server?
9. [General Hardware and Privacy Recommendations](general-hardware-and-privacy-recommendations) - Who makes the best, easy to use, and privacy focues hardware and software?
10. [Closeout](closeout) - Current state and future planned projects

## Where should I start, and what do I need to know?

Generally Users should know the basics about the difference betweeen LAN and WAN, internet speeds, DNS, wifi, and basic home networking information. Helpful links are included below to give you the basics and get you started. You should understand who your internet provider is. What type of connection do your devices use (wired ethernet, MoCa, WiFi etc). How many devices are you connecting? Do you use IOT devices? Are your IOT devices separated from other devices? What does my threat model include: Nation state actors, script kiddies, family members, members of the press/media, criminal organizations? How comfortable are you with coding/maintaining devices? Am I overworked and want simple plug and play/Graphical User Interface (GUI) based Management? Do you know how to login and manage your router?

Link 1: [Jimmy Tries World Overview](https://www.youtube.com/watch?v=DT2ARc1NOpM)

Link 2: [Network Chuck Subnetting for Home Network](https://youtu.be/mJ_5qeqGOaI?si=Nmnr6YyWV-VZSAaO)

Link 3: [WhiteboardDoodles Networking Protocols Explained](https://youtu.be/1zVZ9cWFnCc?si=M-PAW6gMwMoxRp1M)

Link 4: [TechHut What's on my Home Server](https://youtu.be/yUyxJr2xboI?si=aBudJaIxr0DqPBHT)

[Back to top](#readme)

## Pihole - Send the trackers into a black home and take back your data

If you watched the videos in the previous post, you should have and idea of what DNS does on your network. For the older crowd, DNS works like a phone book for the internet. For the younger crowd, DNS translates IP addresses into the common names and websited you use every day. DNS is one of the backbones of the Modern Internet. If you have a baseline configured system from your internet service provider or cellular provider, you are likely using their DNS server. This allows your ISP/cellular provider to gain information on the websites you visit and gather metrics on their customer base. There are also many free options out there you can set as a default other than your ISP's DNS. Some good examples are 8.8.8.8 (Google), 9.9.9.9 (QuadNine), 1.1.1.1 (Cloudflare), and many more. Some offer unparalleled availability and access to new websites while other focus on privacy, security, and content filtering. Pihole allows you to choose the best options for your own personal use case while also importing blocklists from other sources like [Hagezi's dns-blocklist](https://github.com/hagezi/dns-blocklists?tab=readme-ov-file#overview) which will improve your security and data privacy✔️ 

###What you need:
1. Raspberry Pi (various models will suffice, for utilizing the larger blocklists, a model with 6gb of ram or more will be a better option)
2. micro sd card 16gb or 32gb (for the operating system and data storage)
3. Laptop or PC to flash the micro sd card with raspbian OS
4. Micro sd card reader or slot on PC/laptop to flash the SD Card
5. [Balena Etcher Software](https://etcher.balena.io/) - software for flashing the OS to the sd card
6. Portable/second monitor for the raspberry pi
7. Keyboard for the raspberry pi
8. Username and password for your home router to set the DNS entry in your router once you have the pihole setup

Follow the guide below to flash the sd card, setup the raspberry pi, and connect it to your network to serve as your DNS Server. Once complete you can see how many DNS entries the Pihole blocks every day. Each block is an example of the device protecting your privacy and security.

[Raspberry Pi Pihole Setup Guide](https://www.raspberrypi.com/tutorials/running-pi-hole-on-a-raspberry-pi/)

[Back to top](#readme)

###VPN Recommendations


