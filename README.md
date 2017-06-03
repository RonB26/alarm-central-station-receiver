# alarm-central-station-receiver
                                                         
**This is currently a work in progress** -- More information, and details to come soon.

## Overview
So what is this?  This is a python based project for receiving Contact-ID messages from a home alarm system.  It listens for incoming phone calls via a USB FXO with DTMF decoding (currently only magicJack is supported), and relays the messages via e-mail to the user.

*Note:* Use this at your own risk! There are no warranties or guarantees on the relability of this software when it comes to monitoring your home alarm system.  It's simply intended to be a fun software project!

### How does this work exactly?

The alarm-central-station-receiver daemon relies on the USB FXO (magicJack), to signal to it when the home alarm system is dialing out.  When this occurs, the daemon answers the phone, and responds to the alarm with the contact-id handshake.  Credit to li0r for explaining the protocol: https://li0r.wordpress.com/contact-id-protocol/  

Once the alarm receives the handshake, it begins transmitting it's message(s) to the daemon via DTMF codes.  These codes are decoded by the USB FXO, and read by the daemon.  Once the alarm completes transmitting it's message(s), it hangs up, and the daemon then relays them to the configured e-mail address.  If you use your phone provider's email to text bridge, for example for T-Mobile it's number@tmomail.net, you can receive the notification via text.

### Reasons for Building This

There were two reasons why this software was built.  First of all I wanted a way to monitor my home alarm system when I was away from home without having to pay a monthly fee to a central alarm company.  Second, my alarm the DSC PC9155 does not support serial communication like DSC Powerseries alarms do.  This forced me to connect to it via the phoneline and contact-id protocol. 

## Required Hardware & Software

1) Debian OS -- only software this has been run on though it should run on any Linux OS distro easily
2) magicJack -- original version which is silver with the clear window on it.  You can find these really cheap on eBay.
3) Alarm System -- See details on alarms below
4) (Optional) Raspberry Pi -- This is great to use as you can mount it in a small box right next to your alarm system

### Alarm Systems
So far this has been tested with the DSC PC9155 alarm only.  Though it should work with any alarm system that supports the Contact-ID protocol via phoneline.  Contact-ID is the standard used for communciations over the phone, so every alarm system you run into will support it.

## Setup

*TBD*