+++

author = "Jacob Hell"
title = "Adding Activities Section"
date = "2021-05-21"
tags = [
    "daily", "indieweb", "activities"
]

+++

<!--more-->

I mentioned in my [last blog post](../fascination-indie-web) I am obsessed with the [IndieWeb](https://indieweb.org/). The [principles](https://indieweb.org/principles) of the IndieWeb:

>1. ✊ Own your data. Your content, your metadata, your identity.
>2. 🔍 Use & publish visible data for humans first, machines second. See also DRY.
>3. 💪 Make what you need. Make tools, templates, etc. for yourself first, not for all of your friends or ”everyone“. If you design for some hypothetical user, they may not actually exist; if you make for yourself, you actually do exist. Make something that satisfies your needs (also known as scratch your own itch), and is compatible for others, e.g. by practicing POSSE, you benefit immediately, while staying connected to friends, without having to convince anyone. If and when others join the indieweb, you all benefit.
>4. 😋 Use what you make! Whatever you build you should actively use. If you aren't depending on it, why should anybody else? We also call this eat what you cook. Personal use helps you see both problems and areas for improvement more quickly, and thus focus your efforts on building the indieweb around actual needs and consistently solving immediate real world problems, instead of spending lots of time solving what may be theoretical problems.
>5. 📓 Document your stuff. You've made a place to speak your mind, use it to document your processes, ideas, designs and code. Help others benefit from your journey, including your future self!
>6. 💞 Open source your stuff! You don't have to, of course, but if you like the existence of the indie web, making your code open source means other people can get on the indie web quicker and easier.
>7. 📐 UX and design is more important than protocols, formats, data models, schema etc. We focus on UX first, and then as we figure that out we build/develop/subset the absolutely simplest, easiest, and most minimal protocols & formats sufficient to support that UX, and nothing more. AKA UX before plumbing.
>8. 🌐 Modularity. Build platform agnostic platforms. The more your code is modular and composed of pieces you can swap out, the less dependent you are on a particular device, UI, templating language, API, backend language, storage model, database, platform. Modularity increases the chance that at least some of it can and will be re-used, improved, which you can then reincorporate. AKA building-blocks. AKA "small pieces loosely joined".
>9. 🗿 Longevity. Build for the long web. If human society is able to preserve ancient papyrus, Victorian photographs and dinosaur bones, we should be able to build web technology that doesn't require us to destroy everything we've done every few years in the name of progress.
>10. ✨ Plurality. With IndieWebCamp we've specifically chosen to encourage and embrace a diversity of approaches & implementations. This background makes the IndieWeb stronger and more resilient than any one (often monoculture) approach.
>11. 🎉 Have fun. When the web took off in the 90's people began designing personal sites with tools such as GeoCities. These spaces had Java applets, garish green background and seventeen animated GIFs. It may have been ugly and badly coded but it was fun. Keep the web weird and interesting.

One [itch](https://indieweb.org/itches) I have is my activities from the Garmin Connect silo aren't displayed on my site. 

To own this activity data, I used principle 3 to pull my data from Garmin. I will create a post outlining the steps (principle 5) at a later point, but here is a summary:

1. Pull down the data using [garminexport](https://github.com/petergardfjall/garminexport).
2. Use [Garmimport](https://github.com/jacobhell/Garmimport) to migrate the data into Hugo.

The activities section of my site lives [here](../../activities/) 🎉