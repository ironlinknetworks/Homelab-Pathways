# *Work In Progress*
# 🏠 Homelab-Pathways
*Want to break into IT⁉️ Don't know where to start⁉️* With this quick guide, you can get started with your own home lab with **simple, easy to use hardware and software** that will help you get started on your journey. If you're and experienced IT pro and want some nice everyday locally hosted services, feel free to use this guide as well.

You can own your own data and services without paying a subscription and without sacrificing your privacy. Follow the projects below to improve your overall Privacy and security in this modern era ‼️

“Bene vixit, bene qui latuit." (To live well is to live concealed.) - OVID

“The only privacy that’s left is the inside of your head. Maybe that’s enough.” – George Orwell

This guide walks through a rough development of my own personal homelab and the steps I've taken to stop paying subscriptions and take back control of my data. I started my IT education in 2021 shortly before getting a job in data analytics and coding using SAS and SQL and simulataneously studying for the Comptia Security+ certification. I started building out homelab components to enhance my knowledge in the field and gain an understanding of how role based permissions work, how networking concepts work in practice, and discover what is needed for all of the services we use everyday. Another big reason I like hosting my own services is the customization and increased security, data ownership, and the ability to cut free services which harvest my data and subscription services that harvest my hard earned money. I will also like to many of the tools, programs, and creators I trust and respect in the industry along with free and open resources you can use today to build out your own systems.

# 📑 Table of Contents
1. [Getting Started](#getting-started)
2. [Pihole](#pihole) - Block trackers and protect your privacy with this simple DNS project
3. [VPN Recommendations](#vpn-recommendations) - Protect all your devices on your network and your phone on your phone on your daily travels
4. [Home Networking Equipment](#home-networking-equipment) - Customized devices to improve connectivity, security, and privacy across your home
5. [Mini PC](#mini-pc) - Great place to start for home services
6. [Home NAS](#home-nas) - Tired of paying for cloud services and subscriptions? Take a look at a home NAS.
7. [Travel Routers](#travel-routers) - Frequent flyer? Use one of these to protect yourself and your business when traveling.
8. [Getting Started with different Services](#home-services) - What would I even want to run on a home server?
9.  [Camera Security](#camera-security) - Secure your camera feeds and host it locally, avoid the subscription fees
10. [General Hardware and Privacy Recommendations](#general-recommendations) - Who makes the best, easy to use, and privacy focues hardware and software?
11. [Closeout](#closeout) - Current state and future planned projects

## Getting Started

Generally Users should know the basics about the difference betweeen LAN and WAN, internet speeds, DNS, wifi, and basic home networking information. Helpful links are included below to give you the basics and get you started. You should understand who your internet provider is. What type of connection do your devices use (wired ethernet, MoCa, WiFi etc). How many devices are you connecting? Do you use IOT devices? Are your IOT devices separated from other devices? What does my threat model include: Nation state actors, script kiddies, family members, members of the press/media, criminal organizations? How comfortable are you with coding/maintaining devices? Am I overworked and want simple plug and play/Graphical User Interface (GUI) based Management? Do you know how to login and manage your router?

Link 1: [Jimmy Tries World Overview](https://www.youtube.com/watch?v=DT2ARc1NOpM)

Link 2: [Network Chuck Subnetting for Home Network](https://youtu.be/mJ_5qeqGOaI?si=Nmnr6YyWV-VZSAaO)

Link 3: [WhiteboardDoodles Networking Protocols Explained](https://youtu.be/1zVZ9cWFnCc?si=M-PAW6gMwMoxRp1M)

Link 4: [TechHut What's on my Home Server](https://youtu.be/yUyxJr2xboI?si=aBudJaIxr0DqPBHT)


#### **Project costs and time commitment:**
The below table lists general guidelines for all of the projects I have completed. You could take much less time and spend less money on certain projects. Sometimes hardware can be found on sale or maybe a workplace is giving away lifecycled gear. VPN providers also offer steep discounts for first time buyers. The time commitments are generalized based on the time I took to develop and implement solutions and can vary greatly based on your skill and the equipment you purchase.

| Project | Cost | Time Commitment |
|:--------|:---------------|:--------------|
| 🥧[Pihole](#pihole)        | 💵💵                                                                   | 1-2 hours    |
| 🔒[VPNl](#vpn-recommendations)       | 💵💵                                                          | 1-2 hours    |
| 🏠[Home Network Upgrade](#home-networking-equipment)                | 💵💵💵💵                                                           | 3 hours (depends on home size)           |
| 💻[Mini PC](#mini-pc)     | 💵💵              | 4-5 hours |
| 🖥️[Home NAS](#home-nas) | 💵💵💵💵💵    |                                12 hours (building raid array) |
| ✈️[Travel Routers](#travel-routers) | 💵💵  | 1-2 hours |
| 🔒[Home Servicesl](#home-services)       | 🆓 (requires mini pc or nas                                                        | 1-24 hours    |
| 📹[Camera Security](#camera-security)       | 💵💵💵💵                                                        | 3-6 hours hours    |



[Back to top](#readme)

## Pihole
## Send the trackers into a black home and take back your data

| Project | Cost | Time Commitment |
|:--------|:---------------|:--------------|
| 🥧[Pihole](#pihole)        | 💵💵                                                                   | 1-2 hours    |

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

## VPN Recommendations

| Project | Cost | Time Commitment |
|:--------|:---------------|:--------------|
| 🔒[VPNl](#vpn-recommendations)       | 💵💵                                                          | 1-2 hours    |

What is a VPN? It is a virtual private network. A VPN hides your network traffic from tracking sources and websites that seek to make money and understand your behavior for marketing and other behavioral analysis. Most VPNs have an application that is available to use on your devices such as PCs, MACs, Streaming devices, and more. Another cool feature most folks don't know about is the wireguard and OpenVPN files these services offer. You can install this file on most routers and tunnel all your traffic through the VPN so any device connected to your home network is protected. This eases device setup and ensures you don't have to go through tedious steps to install additional applications on all of your devices and especially helps with IOT devices which may not have much or any security built into the systems. You might as which VPNs I would recommend? Check out the list below for my picks and why I like each of these services.

[Proton VPN](https://protonvpn.com/) 

Proton is an excellent choice and has been in the VPN space for a long time, is Switzerland Based and a non-profit organization. Proton's suite of tools includes email, a password manager, an AI tool, and many other features available from a single provider. Their application works on Linux, windows, MacOS, Android, Iphone, and they offer wireguard or OpenVPN configurations you can install on a home or travel router to protect your privacy at home and when you're traveling. They offer VPN servers across the globe with high availability and no logs. I have been a ProtonVPN user for quite a long time and have enjoyed using their services. Their platform is generally offered at a steep discount for first time customers. Proton also offers a free tier so you can try it out before making a purchase, just understand that you will have reduced server selections and likely lower speeds because of the limitations of the free tier.

[Mullvad VPN](https://mullvad.net/en)

Mullvad is another great choice for data privacy based in Sweden. They also have a no logs policy for user. The mullvad VPN application is available on multiple operating systems as well. Mullvad offers wireguard configurations as well which can be used on a home or travel router making it an excellent option. I have used Mullvad's VPN service and recommend it highly to anyone wanting to try out a new option. Mullvad operates as a for-profit company.

You might have heard advertisements on podcasts or on the web for services like Nord VPN, Express VPN or other services which are all valid options. As the author I have my own specific criteria for selecting my VPN services and you may want to take a deep dive before selecting a specific provider. I tend to prioritize a no logs policy, GDPR data protection, high availability and server selection, and a wider variety of additional features. Please feel free to take a look at the resources below to to compare differnet services and determine which is the best for your personal situation before committing to a purchase.

[Who really owns your VPN Provider](https://vpnpro.com/blog/hidden-vpn-owners-unveiled-97-vpns-23-companies/)

[VPN Privacy Comparison](https://vpn.techlore.tech)

[PC Magazine Top Rankings](https://www.pcmag.com/picks/the-best-vpn-services)

[Back to top](#readme)


## Home Network Upgrade

| Project | Cost | Time Commitment |
|:--------|:---------------|:--------------|
| 🏠[Home Network Upgrade](#home-networking-equipment)                | 💵💵💵💵                                                           | 3 hours (depends on home size)           |

Are you using your Internet Service provider's router? Maybe you already have your own separate router or device between your ISP's modem and your network. Purchasing your own equipment can give you a higher confidence measure that your network traffic is separated while also giving you greater control of its management and a greater feature set over your default provider router. I will go over a few options below that may fit your use case and will layout options based on the size and scale of your home network. Remember that when you build your network, you should always plan for growth, the usual recommendation is about 50% of your current size. With the amount of connected devices emerging today this is more necessary than ever. Hopefully you've also enjoyed the previous projects and you have a passion for your home lab now so you will likely want to keep adding devices to your home enviroment to challenge and test yourself.

## Small home or Apartment
For small homes or apartment users and even potentially larger spaces you can get by with a decent small router/wifi access point combination device. Most of the devices on the market will fit this use case but you want to make sure it has the lastes WiFi protocols available and has the ability to accept a wireguard configuration so you can install the VPN and route all your traffic through that VPN tunnel and protect your data and privacy. I'll go through a list of my picks, but feel free to select any device you like so long as it meets your use case. Don't fall victim to marketing gimmicks like devices designed for gaming because often you're paying a premium for features that are available on a similar device at a much lower cost.

1. [Ubiqiti Dream Machine](https://store.ui.com/us/en/category/cloud-gateways-wifi-integrated/products/udr7)
Ubiquiti has one of the most user friendly interfaces available. It is all managed through an easy to use web interface and there are many guides on the internet for setup and deployment. Ubiquiti also makes many other, larger systems and can integrate with ecosystem switches, cameras, and other devices easing expansion later down the road if you want to upgrade without having to learn a new interface. This device will serve all of your needs as you get started and has many features available like web filtering and its own ad blocker built into the system.

3. [Firewalla](https://firewalla.com/products/firewalla-orange)
Firewalla products are very simple as well with many advanced feature sets that can be enabled. Firewalla devices do require an additional access point purchase for additional feature sets which can bring up the cost significantly but you will have a highly available system with many of the advanced feature sets you would like to have as your home network grows.

5. [Netgear Nighthawk](https://www.netgear.com/home/wifi/routers/raxe300/)
The netgear nighthawk label is a line of Netgear products with typically higher speeds and more features than their base models. These are also managed from a web portal an can utilize a VPN configuration as well.

All of these routers/access points will fit your needs but selecting the correct model for your use case depends highly on your budget, home lab size, home size, and other factors. Please make sure to do your research and buy up to date devices and look for sales. Ubiquiti usually has great deals on black friday as an example.

[Back to top](#readme)

## Mini PC

| Project | Cost | Time Commitment |
|:--------|:---------------|:--------------|
| 💻[Mini PC](#mini-pc)     | 💵💵              | 4-5 hours |

[Back to top](#readme)

## Home Nas

| Project | Cost | Time Commitment |
|:--------|:---------------|:--------------|
| 🖥️[Home NAS](#home-nas) | 💵💵💵💵💵    |                                12 hours (building raid array) |


[Back to top](#readme)

## Travel Routers

| Project | Cost | Time Commitment |
|:--------|:---------------|:--------------|
| ✈️[Travel Routers](#travel-routers) | 💵💵  | 1-2 hours |

[Back to top](#readme)

## Home Services

| Project | Cost | Time Commitment |
|:--------|:---------------|:--------------|
| 🔒[Home Servicesl](#home-services)       | 🆓 (requires mini pc or nas                                                        | 1-24 hours    |


[Back to top](#readme)

## Camera Security

| Project | Cost | Time Commitment |
|:--------|:---------------|:--------------|
| 📹[Camera Security](#camera-security)       | 💵💵💵💵                                                        | 3-6 hours hours    |

[Back to top](#readme)

## General Recommendations

[Back to top](#readme)

## Closeout

[Back to top](#readme)


