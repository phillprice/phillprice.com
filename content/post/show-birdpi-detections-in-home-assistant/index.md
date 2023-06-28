---
title: "Show Bird Pi detections in Home Assistant"
date: 2023-03-07T19:00:00Z
draft: true
categories: ["Home Assistant", "BirdPi"]
---
## BirdPi Setup
### Apprise
setup apprise like this (not my real details) for every detection

{{< srcset src="notification.jpg" title="Full Node Red Flow">}}
```
mqtt://[birdpi]:[password]@[ip-address]:1883/birdpi/apprise
```

Set the apprise title as empty and the body as this 
```
{"Common_Name": "$comname", "Scientific_Name": "$sciname", "Confidence_Score": "$confidence", "link": "$listenurl", "Date": "$date", "Time": "$time", "Week": "$week", "Latitude": "$latitude", "Longitude": "$longitude", "Minimum_Confidence": "$cutoff", "Sigmoid_Sensitivity": "$sens", "Overlap": "$overlap", "Image": "$flickrimage"}
```
## Home Assistant Setup
### MQTT
setup an mqtt sensor:
{{< gist phillprice bdeacff9dd8ff8b18f6c4155afb559e1 "mqtt.yaml" >}}

### Camera
I also setup a 'camera' for the image:

{{< gist phillprice 5a228f770bf14e29221c176600b77c6e "camera.yaml" >}}

### Lovelace
I have a mushroom card setup like this (you'll need [mushroom](https://github.com/piitaya/lovelace-mushroom) and [stack-in](https://github.com/custom-cards/stack-in-card) cards to copy directly):
{{< gist phillprice 0500ea0ef980cfea0a45995fffafcdd6 "lovelace.yaml" >}}


{{< srcset src="birdpi-card.jpg" title="Full Node Red Flow">}}