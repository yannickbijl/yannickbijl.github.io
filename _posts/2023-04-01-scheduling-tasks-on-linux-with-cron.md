---
layout: post
date: 2023-04-01 00:00:00 +0100
tags: Linux
categories: Software-Development Tools
title: 'Scheduling Tasks on Linux with CRON'
---

We have the ability to create processes to simplify our tasks immensely as programmers. Able to turn whole paragraphs of text (a script) into a few words (a command) gives great flexibility, efficiency, and productivity. However, some tasks need to be repeated quite often, say every day or even every hour. Coming to your terminal and typing the same command every time gets tedious real fast.

On unix devices (thus also servers) we can use `cron` to run tasks on a fixed schedule. `cron` is a commandline utility with which we can specify the moment a script or command should be executed. As long as the computer in question is on, it will execute the scheduled job. 

To set a job, we will need to at it to a specific file. This file can be opened using the command `crontab -e`. If the file does not exist, it will create one for you and open it in the editor of your choice. In this file you can add jobs with the format: `Minute Hour DayOfMonth Month DayOfWeek Command`. There are shorthands starting with an `@` symbol such as `@yearly`. The command can be a standard unix command such as `ls` or the start of script like `bash run_script.sh`. A few examples are given below.

```bash
15 * * * * command # Every 15 minutes
0 4 * * sun command # Every Sunday at 4 AM
0 9 8-14 * * command # Every 8th till 14th of the month at 9 AM
@yearly command # Every year
```

There are many ways to set the scheduling. A useful website for `cron` is [crontab.guru](https://crontab.guru/). This gives an interactive interface to play with the time settings. The great part is that [crontab.guru](https://crontab.guru/) gives an understandable explanation of the given time settings back as feedback. It also has a short list of the options for the time settings. There are many ways to extend the scheduling to your own custom uses. Both this post and [crontab.guru](https://crontab.guru/) are starting points to automate and schedule some processes to simplify your life. The best way to learn it is by trying different settings yourself.
