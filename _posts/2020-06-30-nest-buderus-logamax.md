---
layout: post
title: "Nest thermostat installation with a Buderus Logamax Plus boiler"
date: 2020-06-30 19:28:00 +0200
categories: home-automation
---

Last weekend I installed a [Nest learning thermostat 3rd generation](https://store.google.com/be/product/nest_learning_thermostat_3rd_gen) I had lying around, collecting dust. However, I would currently not buy this thermostat again, because when Google acquired the company behind this product, they also [disabled the API](https://blog.google/products/google-nest/updates-works-with-nest/), making integration with non-Google platforms challenging.

While the installation in itself it not really complicated, I'm writing this blog post because it can be a bit challenging finding out which configurations will work.

Essentially when connecting the Nest thermostat to a boiler, you have two options. You can ether, choose to utilize it as an on/off thermostat, or you can utilize the [OpenTherm](https://en.wikipedia.org/wiki/OpenTherm) protocol. While I believe most boilers offer support for on/off thermostats, support for OpenTherm is a bit more rare in my experience. Boiler manufacturers seem to prefer to develop their own protocols for talking with thermostats. While I am not an expert in the matter, when using OpenTherm the Nest thermostat is able to control the internal temperature of the boiler more gradually (modulating). I've been told that this is way more efficient. When utilizing an on/off thermostat, the boiler always utilizes the maximum temperature internally which makes it more difficult to keep room temperature constant.

So was the case with the boiler that was installed when we bought the house. It is a Buderus Logamax Plus model. The thermostat we replaced was a Buderus RC35 model. Buderus uses the EMS protocol in order to facilitate communication from the boiler to the thermostat. This protocol is explained in detail in [this blogpost](https://domoticproject.com/ems-bus-buderus-nefit-boiler/).

So in order to talk from the Nest thermostat to the boiler I needed a translator to translate the EMS protocol to the OpenTherm protocol. Luckily this device exists and looks like this: ![](/img/ems_ot_adapter.png)

There was however one problem, my boiler was not listed as a supported device. I however took a leap of fate, and ordered the adapter anyway. To make a long story short: it works without any issue (so far).

The installation of the adapter is also not too difficult. You connect the one end of the adapter (the orange plug) to the boiler in the connection labeled RC (remote control). This is also the spot where your old EMS thermostat would be connected:

![](/img/ems_adaptor_install.png)

The other end of the adapter should be connected with the Nest Heatlink using the OT1 and OT2 connections. The Nest thermostat itself should be connected using the T1 and T2 connections:

![](/img/nest_heatlink_install.png)

While it is unfortunately that I currently cannot integrate it into my home automation system easily, I am still extremely happy how it looks on my wall:

![](/img/nest.png)
