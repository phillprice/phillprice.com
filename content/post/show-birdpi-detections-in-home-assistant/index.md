---
title: "Show Bird Pi detections in Home Assistant"
date: 2023-03-07T19:00:00Z
draft: false
categories: ["Home Assistant", "BirdPi"]
---
## Introduction

In the world of bird enthusiasts and nature lovers, BirdPi offers an exciting opportunity to connect with the avian wonders around us. Whether you're a seasoned birder or a curious beginner, setting up BirdPi can enhance your bird-watching experience. In this guide, I'll walk you through the steps to configure BirdPi for notifications and integration with Home Assistant.

## Apprise

{{< srcset src="notification.jpg" title="Full Node Red Flow">}}

Apprise, a versatile notification tool, will help you stay informed about the feathered visitors in your vicinity.

To set up Apprise for BirdPi, follow these instructions (replace the placeholders with your actual mqtt details):

mqtt://[username]:[password]@[ip-address]:1883/birdpi/apprise

Make sure to set the Apprise title as empty and the body as follows:


{{< gist phillprice 5a228f770bf14e29221c176600b77c6e "apprise-settings.json" >}}

This configuration ensures that I receive detailed and informative notifications whenever BirdPi detects a bird.

## Home Assistant Setup
To seamlessly integrate BirdPi into your smart home ecosystem, I recommend setting up Home Assistant with the following components:

### MQTT Sensor
Create an MQTT sensor by adding the following configuration to your `mqtt.yaml`:

{{< gist phillprice 5a228f770bf14e29221c176600b77c6e "mqtt.yaml" >}}

### Bird Image Display
Display images of the detected birds using the 'image' component. Add this configuration to your `image.yaml`:

{{< gist phillprice 5a228f770bf14e29221c176600b77c6e "image.yaml" >}}

### Lovelace Card
Create a Lovelace card with a mushroom theme. You'll need [mushroom](https://github.com/piitaya/lovelace-mushroom) and [stack-in](https://github.com/custom-cards/stack-in-card) cards to replicate this setup. Add the following configuration to your `lovelace.yaml`:

{{< gist phillprice 5a228f770bf14e29221c176600b77c6e "lovelace.yaml" >}}

With these configurations, you'll have a comprehensive BirdPi setup that not only detects birds but also provides a delightful experience through Home Assistant.

{{< srcset src="birdpi-card.jpg" title="BirdPi Image">}}
