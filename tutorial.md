---
layout: page
title: Quick Start Guide
permalink: /tutorial
---

![RSI Integration](https://preview.redd.it/ukybnhsl24ta1.png?width=1080&format=png&auto=webp&v=enabled&s=394278d14210b9eec520e7948c41f9b61cfca1e7)

This tutorial is meant to showcase the bot's main features and how to use them. It is not meant to be a complete guide on how to use the bot, for that, you can check the [**documentation**](https://devtracker-bot.github.io/documentation)

In this tutorial we'll learn how to follow only [**Patch Notes**](https://robertsspaceindustries.com/spectrum/community/SC/forum/190048/thread/star-citizen-alpha-3-18-0-live-8389318-patch-notes) on Spectrum & **the RSI comm link.**

### 1. Add the bot to your server

This is quite simple, the bot is fully integrated with [Discord Slash Commands](https://support.discord.com/hc/en-us/articles/1500000368501-Slash-Commands-FAQ) and therefore doesn't need any special permissions, you just need to [invite it](https://discord.com/api/oauth2/authorize?client_id=982257201211138050&permissions=274877925376&scope=bot%20applications.commands) .

### 2. Create a channel where the Bot can send messages

Assuming you know your way around Discord, this shouldn't too difficult, just make sure the Bot **has the permissions** to **See your channel** and **Send Messages in it.**

### 3. Make the bot follow Star Citizen, and post its messages in the channel you just created

Let's say your channel is called "#sc-devtracker", you need to run the "/dt-set-channel game" command. All of the bot's command have auto-completers to help you, but your prompt should look like to something like this

>/dt-set-channel game channel: **#sc-devtracker** game\_name: Star Citizen

As soon as you do this, the bot will send the latest post it can find from all the sources available to it, otherwise, you should probably check the channel's permissions

### 4. Keep only the RSI Comm-Link and the Spectrum as sources of posts

This is where we make use of [allowlists](https://github.com/s0me-1/devtracker-bot#allowlist--ignorelist) . Setting up an allowlist will make the bot ignore any post that does not come from a source that is in the allowlists. The source can be either a S**ervice** ( CommLink, Spectrum, Twitter, etc...) or an **Account** (Wakapedia-CIG, Silvan-CIG, etc ...)Let's first add the Comm-Link service as an allowed source first

>/dt-allowlist add service game\_name:Star Citizen service\_id:CommLink

Now we add the Spectrum service

>/dt-allowlist add service game\_name:Star Citizen service\_id:rsi

Now you'll only receive posts if they come from Spectrum or the RSI Comm-Link

### S5. Keep only posts from the Patch Notes category on Spectrum

This is where [
    URL Filters](https://github.com/s0me-1/devtracker-bot#url-filters) become useful.

A **URL Filter** is a keyword that must always be included in the source URL of a post in order to be sent.

In this exemple, we only want to keep the **Spectrum  Patch Notes category,** which URL is: [**https://robertsspaceindustries.com/spectrum/community/SC/forum/190048**](https://robertsspaceindustries.com/spectrum/community/SC/forum/190048)

So we can set **"forum/190048"** as the **URL Filter** for the **Spectrum service** ("rsi'),

>/dt-urlfilters global game\_name: Star Citizen service\_id: rsi

This command will open a Discord modal like this

![Discord URL Filters Modal](https://camo.githubusercontent.com/5e81fc2d7720ef70f8d0479d98a61031aaa78d7fd71e9904d682ad3a8cd5e247/68747470733a2f2f692e696d6775722e636f6d2f37444d356849522e706e67)

There, you can enter "**forum/190048**" as yhe URL Filter and click the **Submit** button.

### 6. Ckeck your current configuration

You can check your configuration at any time with

>/dt-config

If everything went well and you followed this Tutorial carefully, you should have something like this

### That's all ?

Yes, you're now  all set !

- You can check the [Github Page](https://github.com/s0me-1/devtracker-bot) for more advanced configuration.
- You can also find the official **Devtracker Discord Server** [**here**](https://discord.com/invite/QN9uveFYXX)
