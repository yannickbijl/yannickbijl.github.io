---
layout: post
date: 2022-10-29 00:00:00 +0100
tags: [Linux, BASH]
categories: 'Software-Development'
title: 'Screen: A Powerful Tool'
---

Screen is an amazing tool for linux that has saved me more than once, allowing me to run long-running processes in the background and disconnect from them. In turn allowing me to continue working without issue. Screen is already installed on most linux distributions, so it is easy to try out.

To start, simply type the command `screen`. This opens an interactive background process. Your standard commands work here and will continue as long as the computer (or server) stays on. To get out of the screen use `Ctrl` + `A` + `D`. To completely stop the screen and thus also stop all processes in it, use `Ctrl` + `D`. Use the same command again to create a new screen. 

To reconnect to your last screen (background process) use the command `screen -r`. Do note that this will always connect to your last connected screen. To reconnect to different screens you will need to know the id of the screen in question.

To get the ids of the different screens it is easiest to use the command `screen -ls`. This returns a list of your screens, including their ids as seen below. To reconnect to a screen use `screen -r <id>`. So in this case `screen -r 180.tty1.DESKTOP-7OCE5L2`.
```
There is a screen on:
        180.tty1.DESKTOP-7OCE5L2        (10/17/22 17:26:26)     (Detached)
1 Socket in /run/screen/S-root.
```

These are basic commands, but it allows for executing lond-during pipelines and software without having to keep your own computer on all the time. It is best to use this command on servers as you know they will stay on, even if you walk away. With this tool you can also easily start something at the end of the work-day and come back in the morning for your results. Screen really can make live easier.
