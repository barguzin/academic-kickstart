---
title: "Setting Up Yandex Disk on Manjaro"
date: 2021-02-07T00:11:37-08:00
draft: false
---

{{< figure library="true" src="yadi.png" title="Jupyter" >}}

I have been using Yandex Disk since my heydays of working for big data in Moscow, Russia. Early adoption has born the fruit of ample free storage, which moved across OSes, as I was learning to work with both MacOS and Linux. Yandex Disk GUI for Mac and Windows make interacting with the cloud storage a breeze, but the Linux version of the program was lagging behind in terms of user experience and ease of use. While there are some unofficial GUIs for Yandex Disk, the primary interaction occurs via a command line utility. 

The set up is pretty straightforward and is outlined in the [documentation](https://yandex.com/support/disk-desktop-linux/). One thing to keep in mind, especially if you are storing 10s and 100s GB of data: make sure to uncomment and change the *exclude-dirs* flag in the **config.cfg**, located at **~/.config/yandex-disk**. Keep in mind that you have to follow the formatting style outlined in the doc. Please note, that if you already downloaded a directory onto computer and only then excluded the directory from syncing, it will still be stored on your computer, until you manually delete if from the Yandex Disk directory. 