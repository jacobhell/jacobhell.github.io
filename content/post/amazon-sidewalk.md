+++

author = "Jacob Hell"
title = "The Privacy Nightmare of Amazon Sidewalk"
date = "2021-05-31"
tags = [
    "daily", "amazon", "privacy"
]

+++

<!--more-->

### What is Sidewalk

[Amazon Sidewalk](https://www.amazon.com/Amazon-Sidewalk/b?node=21328123011) is a network created by Amazon's devices. These devices include the Echo assistant and Ring doorbell. It will also work with the bluetooth tracking tag, [Tile](https://staceyoniot.com/with-tile-deal-amazons-sidewalk-network-just-became-more-interesting/). And [Level](https://level.co/), a Bluetooth smartlock.

Why create this network? Sidewalk shares your internet with your neighbors, providing a resilient network. So if your internet is having issues, the Sidewalk protcol uses your neighbors router.

Sidewalk is Amazon's competition to [Apple's AirTag](https://www.apple.com/airtag/). AirTag only works with Apple devices, while Amazon works with any opted in medium.

### Privacy Risks

The network isn't limited to your own devices. Sidewalk creates a mesh network with any Amazon device. So your device, your downstairs neighbor's Ring, and your nextdoor neighboor's Echo, will share a network. 

The Sidewalk protocol connects Bluetooth devices too. Initially, only some Amazon products will be connected. But considering the deals with Tile and Level, Amazon is looking for future partners.

[ArsTechnica](https://arstechnica.com/gadgets/2021/05/amazon-devices-will-soon-automatically-share-your-internet-with-neighbors/) pointed out there's no known vulnerabilities with Sidewalk. But historically safe protocols and networks have vulnerabilities:

> Wireless technologies like Wi-Fi and Bluetooth have a history of being insecure. Remember WEP, the encryption scheme that protected Wi-Fi traffic from being monitored by nearby parties? It was widely used for four years before researchers exposed flaws that made decrypting data relatively easy for attackers. WPA, the technology that replaced WEP, is much more robust, but it also has a checkered history.

> Bluetooth has had its share of similar vulnerabilities over the years, too, either in the Bluetooth standard or in the way it’s implemented in various products.

I ask the same question as ArsTechnica:

> If industry-standard wireless technologies have such a poor track record, why are we to believe a proprietary wireless scheme will have one that’s any better?

### Disabling Sidewalk

Perform the following to disable Sidewalk:

1. Opening the Alexa app
2. Opening More and selecting Settings
3. Selecting Account Settings
4. Selecting Amazon Sidewalk
5. Turning Amazon Sidewalk Off

Do this before Sidewalk goes live on June 8th.
