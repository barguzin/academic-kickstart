---
title: "Jupyter Arch Completions"
date: 2021-02-03
---

I recently had to make a clean OS install on my working laptop, so after beefing up the RAM on my Lenovo I finally decided on Manjaro distro. Manjaro comes in a few different flavors (desktop environments, such as KDE Plasma and GNOME), so making a switch from Fedora 31 with GNOME, chose to make the switch as seamless as  possible and opted to stick with the GNOME version. 

The installation process was a breeze and a set up did not take much time, compared to Arch Linux from which Manjaro is derived and which is notoriously laborious and time-consuming to install. I would devote another post to the differences between Fedora and Manjaro, suffice it to say these are very similar, but the switch did take some 'getting-used-to'. 

![illustration](/home/barguzin/github/academic-kickstart/static/img/jupy.jpeg)

Since I mostly utilize Python data analysis stack in my research, I almost exclusively prefer working in Jupyter Notebooks, especially for exploratory data analysis (EDA). One of the first things you learn in Jupyter is that it can speed up code writing using the so-called auto-completions, similar to other IDEs on the market. You start writing something like **print(__pd.ver)** and then you hit the **Tab** to auto-complete the command, but nothing was happening. Obviously, there was some package conflict related with Jupyter dependencies.  

Since much of the OS ecosystem, including package management comes from Arch it was only logical to search for an answer on the Arch Linux forums, which did not take much time. This [post](https://bugs.archlinux.org/task/67552) suggested the following workaround: 

> Completion depends on python-jedi which is at 0.17.0, dependency parso>=0.7.0, which allowed parso 0.8, but it is incompatible. jedi upstream is updated to 0.17.2 with its dependency parso<0.8>=0.7.0, which shows parso 0.8 is incompatible.

Turns out I needed to downgrade both *parso* and *jedi*, which is easily done via pip manager: 

```console 
user@manjaro pip3 install 'parso=0.7.1<0.8' --user
```

And that is it! Good luck on your next journey to Linux. 

@barguzin