+++

author = "Jacob Hell"
title = "Software that Kills. The Therac-25 Incident"
date = "2021-05-27"
tags = [
    "daily", "software", "bugs", "tech criticism"
]

+++

<!--more-->

I was reading [this thread](https://news.ycombinator.com/item?id=27292219) about people hurting themselves with code. The injuries in the thread were mostly humorous and nothing nearly fatal. However, overconfidence by programmers has caused accidental death in the past.

### Therac-25

The [Therac-25](https://en.wikipedia.org/wiki/Therac-25) is the most infamous example of accidental deadly software. Due to race conditions in the code, 6 patients were given far greater radiation than intended. Some of the incidents were fatal.

[An overview](https://en.wikipedia.org/wiki/Therac-25#Root_causes) of the causes claims that there was no single source of the bugs. In general, a bad company culture and lack of testing caused the deaths of patients.

Researchers on the postmortem of Therac-25 produced this insightful statement:

> "A naive assumption is often made that reusing software or using commercial off-the-shelf software will increase safety because the software will have been exercised extensively. Reusing software modules does not guarantee safety in the new system to which they are transferred..."