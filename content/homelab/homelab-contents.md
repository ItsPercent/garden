---
publish: true
title: What's in my Homelab?
created: 2026-07-21T15:00:55.102-04:00
modified: 2026-07-21T17:26:11.570-04:00
---

Short answer: a whole lot of crap; long answer: an absolute ton of crap.
...okay on a more serious note my homelab is broken down into a few distinct sections, [[#Infrastructure]], [[#Utilities]], File Sync, Gaming, and Home.

### Infrastructure

Proper infrastructure is the foundation of any semi-competent homelab, and there is a lot to go through. to start with, my entire homelab is built off of [Portainer](https://www.portainer.io/) which gives you a helpful little website to create, manage, and supervise your docker containers. (For those who aren't in the know docker just allows you to keep programs seperated from each other.) This is perfect for me because whenever I'm out on a family vacation, I need to be prepared for something to go terribly wrong, and be able to fix it without being plugged into my home internet.

Next up are the services that I run from within Portainer. First is [Nginx Proxy Manager](https://nginxproxymanager.com/), which I have definitely developed a love/hate relationship with. It's idiot-proof enough that I can get by without worrying about nuking everything, but is lacking features in some areas like a way to control OIDC in a GUI or logging in with a passkey. Overall though being able to quickly deploy services with Portainer and expose them securely to the internet with NPM without waiting for DNS propagation is a killer combination, speaking of DNS...

[Cloudflare](https://www.cloudflare.com/)! Cloudflare has always been a bit of a controversial company online, (Not even mentioning the outage late last year) but as far as a free way to keep your DNS records updated and create fast tunnels to hide your IP, they're hard to beat. On my setup, I have a tunnel move http and https traffic from my domain to my lab, which is then directed to NPM for routing to my services. It's definitely a set-and-forget thing for me which lets me focus on other aspects of my lab.

Last thing for this section is [Pocket ID](https://pocket-id.org/) and [Tinyauth](https://tinyauth.app/), This dream team is responsible for keeping my homelab easy to access and secure. Pocket ID let's me sign into most of my services with one passkey that I keep tucked away in my password manager, however there are some services that don't support single sign on, which is where Tinyauth comes in to implement it. Some services like Pi-hole let me disable the passwords for them, which while at first sounds like a terrible idea, lets me then put them behind Tinyauth. If I'm signed in with my passkey it'll let me through no problem, but anyone else is kept out. By far my favorite part of an OIDC system like Pocket ID is that I can control who has access to what. While I can access everything, I may only give my friend access to RomM and then give them access to other utilities later on.

### Utilities

Utilities is definitely where my homelab is strongest, as it has many containers that I consistently use on a daily basis. First up is my dashboard, [Homarr](https://homarr.dev/), which lets me monitor everything in my homelab at a glance. I set it as my homepage in my web browser so I can keep an eye on everything an access any services as needed. Homarr is pretty resource intensive, though, so if you are comfortable with yaml I'd highly recommend [homepage](https://gethomepage.dev/) instead.

[Ladder](https://github.com/everywall/ladder) is actually one of few services that does not require any sort of password to access, although I may change that in the future. It's main feature is removing paywalls from websites, such as The Verge which recently started to charge people to read it. Combined with an Apple Shortcut I can quickly access my RSS feeds and view them for completely free.

[Shlink](https://shlink.io/) is up next, and it acts as my own little personal bitly. I have long used services such as bitly and yellkey, but bitly is paid and yellkey has issues if you don't use the www subdomain. What else is nice about Shlink is it lets me see link usage, which neither of the big alternatives offer for free.

Last one of the list is [Linkstack](https://linkstack.org/), which is likely how you got here in the first place. I just think of it at Linktree but with my own domain, and it's a nice thing to include in my bio so that people can quickly find everything they need.

# TBC :D
