---
layout: article
title: "Servicehandler: one library to bring them all..."
lang: en
ref: servicehandler-introduction
date: 2020-06-28
---

I would like to talk about another side project that kept me busy lately (apart from [ITAQA]({{site.url | append: '/blog/2020/05/29/ITAQA_introduction_en'}}), on which I'm still working!): the development of a small Python library to handle and orchestrate services (or *daemons*) in Linux.

## Fantastic bots and where to find them

Lately I developed four **Telegram bots** using the really nice library [python-telegram-bot](https://github.com/python-telegram-bot/python-telegram-bot).  
For the ones that don't know what a bot is, refer to [this page ontelegram.org](https://core.telegram.org/bots). Briefly, in this context a bot is an application able to interact with users/groups directly on Telegram, answering to messages and accepting commands.

I will probably write about some of these bots in the future, for now I just want to talk about their hosting and management.

### Hardware

A bot is a standard application (in this specific case, a Python script). To interact with it at any  time, it needs to be constantly running. Two are the possible solutions:

* **Hosting on external services**
  Services like [Microsoft Azure](https://azure.microsoft.com/en-us/), [Heroku](https://www.heroku.com/), [OpenShift](https://www.openshift.com/), [Amazon AWS](https://aws.amazon.com/) provide virtual machines (VMs) for different usages, on which is possible to run applications continuously. This alternative is the simplest (the machine is accessible everywhere, always active, with almost no maintenance needed), but it's also limited by reduced performances, a cap on the amount of runnable applications and nerfed responsiveness.
  Although almost all the listed services offer free plans for non-commercial projects, to obtain a machine with better performances a monthly subscription is needed (around ~10€<sub>/month</sub>).
* **Self hosting on personal hardware**
  The "domestic" solution is to dedicate personal hardware for the hosting. This is possible keeping a PC constantly running (may be inconvenient) or using a small low-cost hardware platform, like a single-board computer.

For different reasons[^1] I choose the second solution: hosting using a [**Raspberry PI Zero W**](https://www.raspberrypi.org/products/raspberry-pi-zero-w/). With 512MB of RAM and a 1GHz single-core CPU, it's not exactly a [TOP500](https://it.wikipedia.org/wiki/TOP500) PC, but considering the low amount of resources that my bots need, it's enough. The key points of the Zero are the small size, the built-in WiFi and the possibility to powering it directly through Micro-USB (using a simple phone charger).

{: style="text-align: center;"}
<img src="{{site.url | append: '/media/20200628/raspberrypizero.jpg'}}" title="Raspberry PI Zero W, pasta for scale" class="responsive" onclick="window.open(this.src)">

### Software

Chosen the hardware and installed a Linux distro like Raspberry Pi OS (historically known as *Raspbian*), the bots need to be configured so they start automatically on system startup.

The easiest way to automatically start applications is to create ad-hoc services. In order to do this **systemd**, an administrative/configuration suite native in Linux systems, can be used. For every new service a **unit file** is written and put in `/usr/lib/systemd/user/`:

{: .codeblock}

```ini
[Unit]
Description=My bot

[Service]
ExecStart=/usr/bin/python3 /home/user/bot/main.py
Environment=PATH=/bin:/usr/bin:/usr/local/bin
WorkingDirectory=/home/user/bot/

[Install]
WantedBy=multi-user.target
```

It's now sufficient to mark which services need to be started automatically using the command `systemctl --user enable MyBot.service`.

All done. It suffices to turn the Raspberry on, forget it, to have everything working fine forever.

Great.

{: style="text-align: center; padding: 0 15%;"}
<img src="{{site.url | append: '/media/20200628/jobdone.jpg'}}" title="Everything done, let's go home" class="responsive" onclick="window.open(this.src)">

There is just a small detail: often[^2] things don't go as planned, therefore it would be nice to be able to restart the bots, to check theirs logs, to kill them if needed, and so on. All things easy to do when connected to the same network of the Raspberry, more complex from somewhere else.[^3]

It would be great if these operations were easy to perform from any place, maybe... creating a new bot...

It will be a humble "bot-manager", with a modest name and a low-key profile picture. I don't want to create an evil bot overlord.

{: style="text-align: center; padding: 0 20%;"}
<img src="{{site.url | append: '/media/20200628/lordofthebots.jpg'}}" title="An humble bot, absolutely not bossy" class="responsive" onclick="window.open(this.src)">

_Mh._

## One library to bring them all and in the darkness bind them

A ~~evil bot driven by power~~ bot-manager[^4] cannot do anything if it's not able to interact and control `systemd` services. What it needs is a library to wrap `systemctl`.

The ones that have already used Python know that there is a library for every need.[^5] I looked around for something that would suits me. I didn't find anything useful, I decided to create one.

## systemd-servicehandler

The library is called systemd-servicehandler, or just  **servicehandler**.[^6]

{: style="text-align: center;"}
<img src="{{site.url | append: '/media/20200628/servicehandler_banner.png'}}" title="Lo stupendo banner di servicehandler" class="responsive" onclick="window.open(this.src)">

(I'm very proud of the banner)

**Current state**

*servicehandler* is still in an experimental phase, it's nothing exceptional but it currently works. There are still some features to implement, together with tests and fixes.

Since there was no such library yet, I also decided to pack and distribute it on **PyPI** ([servicehandler on PyPI](https://pypi.org/project/servicehandler/)), so that it can be used by other developers via pip  (`pip install servicehandler`).

Currently the base functionalities (service abstraction and utilities control methods[^7]) are implemented, making it possible to control a bot (or any service) in the following way:

{: .codeblock}
```python
import servicehandler as sh

# Create a ServiceHandler object that represents the bot service
my_bot = sh.ServiceHandler('Bot','MyBot.service')

# Check bot status
my_bot.state()
<ServiceState.STOPPED: 2>

# Start the bot
my_bot.start()
Bot changed state to ServiceState.STOPPED
<Response.OK: 1>
    
# Stop the bot
my_bot.stop()
Bot changed state to ServiceState.RUNNING
<Response.OK: 1>
```

### Coming soon

Some things to implement:

* Log/file monitoring, to access relevant files linked to a specific service
* Creation of a "watchdog class" able to monitor multiple ServiceHandler objects and to react automatically, following user-defined rules
* Exploring system services monitoring (root permissions needed)

Like the other projects in this blog, also *servicehandler* is completely open-source and available on GitHub: **[servicehandler](https://github.com/albertosantagostino/systemd-servicehandler)**.

See you soon, thanks for reading!

<br>


[^1]: I know that any virtual machine of the free-tier would be enough. But, I try to maximize the "DIY" approach in my projects. Also, I decided to resurrect the poor RPi Zero that was sleeping in a drawer for years. I assume he is bored
[^2]: Always
[^3]: It's of course possible to configure port-forwarding or use VNC, they are both valid solutions
[^4]: Who watches the watchers? Of course LordOfTheBots must be controlled manually (through SSH, for example). It must have a robust design, as it should be very stable
[^5]: <a href="https://xkcd.com/353/">xkcd: Python</a>
[^6]: I know I missed my chance to call the library `systemd-onering` or something similar, but I still have a glimmer of seriousness (_laugh track_)
[^7]: There are methods to start, stop, enable, disable, kill, get state