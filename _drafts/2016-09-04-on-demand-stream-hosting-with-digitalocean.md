---
title: 'On-Demand Icecast Hosting with DigitalOcean'
date: 2016-09-04
author: Dan Fraser
layout: post
categories:
  - general
---
# Why?

I have an occasional desire to stream audio to my friends over the internet. I like to play music out of Spotify or Serato DJ and let my friends listen in. It's a fun, easy method to share "live" music. Doing it requires a lot of bandwidth, around 250kbit/sec per listener. With 40 people listening, that's 10Mbit, more than the average home connection can send reliably. To get around this, you send a single stream from your home to a server with a faster connection. The server distributes the single music stream to many listeners.

There are many services on the internet to do this, but the pricing is intended for people who stream music often. They charge a monthly fee, usually starting around $10, and increase the fee based on the number of listeners you would like to support, or the quality of the audio stream you'd like to transmit -- that is, your bandwidth commitment. As I write this, <a href="http://shoutcheap.com">ShoutCheap</a> charges USD$16 a month to support 50 listeners at 128kbit/sec, a barely acceptable bitrate.

I don't need to do it all the time, I'm a nerd, and I want it cheaper.  Let's try this new cloud thing!

# Getting Started

I decided to try this project on <a href="https://digitalocean.com">DigitalOcean</a> because it looked easy, seemed cost-effective, and was recommended by a few of my friends. I went to their site, signed up, entered my credit card info, and set up <a href="https://en.wikipedia.org/wiki/Multi-factor_authentication">two-factor authentication</a>.

I hit the "create droplet" button (DigitalOcean calls servers "droplets") and selected the simplest, cheapest choice, the 512MB Ubuntu server. At the current rates, it will cost me $0.007 per hour to run -- I can afford this for a couple hours a month.

DigitalOcean uses SSH to secure their servers, so I used PuTTYgen from the <a href="http://www.chiark.greenend.org.uk/~sgtatham/putty/">PuTTY</a> project to generate an SSH key, and added the public side to my droplet. They have a great <a href="https://www.digitalocean.com/community/tutorials/how-to-use-ssh-keys-with-putty-on-digitalocean-droplets-windows-users">tutorial</a> on how to do this, if you're not an old hat with SSH like me.

I clicked "Create" with all the rest as defaults, and seconds later I had my very own Ubuntu server. I logged in with PuTTY to get started.

# Icecast2

I knew I wanted to use Icecast2 for streaming, and it's available in the default Ubuntu packages, so installing it with apt took only seconds. The package script prompted me for a hostname (which I just left as localhost) and passwords for being a music source, a relay (which I set, but will never use) and for the admin panel.  Once it was done, I used `systemctl` to make it run on boot and started it up.  

I was able to connect easily from NiceCast on my Mac. I used the IP address DigitalOcean gave me for my droplet, made up a mountpoint name (`/music`) and used the default login (`source`) with the password I gave during setup.  Everything worked.

# DNS

I wanted people to access my music stream with a proper URL, and DigitalOcean changes IP addresses whenever you create or destroy a droplet, so it was time for some <a href="https://en.wikipedia.org/wiki/Dynamic_DNS">dynamic DNS</a>. I use <a href="https://easydns.com">EasyDNS</a> to host my domain name, so I used their service. There are other ones available out there, many for free, if your situation is different. EasyDNS recommended the Linux tool "ez-ipupdate" to configure their service. It was available in the Ubuntu packages and included a setup script as well.  I just selected EasyDNS, entered my username, my access token, and the hostname I wanted to use (`radio.capybara.org`) and the package did the rest. A bit more playing with `systemctl`, and I had my dynamic DNS working.

# Systems Stuff - The Snapshot

The next thing I did was to reboot my droplet -- I wanted to confirm that everything was going to start automatically. After testing everything out, I shut it down with the "`poweroff`" command.  Powering off your Droplet doesn't change the amount you're charged, since the computer and disk space and IP address are still all allocated in your name. But you need to power off to make a
"snapshot.""

On the DigitalOcean website, I created snapshot of my droplet. You can use the snapshot as a template to create new droplets in the future.  DigitalOcean charges you money to store them, but it's significantly less than the cost of having your server running. At the time of writing, $0.05 per gigabyte per month. My snapshot was exactly 1 gigabyte.

At this point I could destroy my droplet -- this releases all of its resources and takes you off the clock. When I'm ready to stream, I can create a new Droplet at any time from my snapshot, use it for as many hours as I want, and then destroy it.

# Conclusion

Setting this up took me about 3 hours, but I'm a Linux user, a system administrator, and a programmer. If you're none of those things, this setup might not be for you, and you might want to head over to ShoutCheap for their turn-key service. If you want to mess around with the cloud and potentially save some money, give this a try. I had a lot of fun playing with it, and I bet you will too!
