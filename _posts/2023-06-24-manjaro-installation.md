---
layout: post
title: First things to do after a fresh Manjaro Install
date: 2023-06-24 15:28:16 +0900
description: Manjaro Installation
permalink: /manjaro/
img: manjaro1.jpg # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [Manjaro, Linux]
---
Commands to execute after a fresh installation of Manjaro Linux. This includes some of the apps that I recommend.

```bash
sudo pacman-mirrors --geoip
sudo pacman -Syu
sudo pacman -Sy yay base-devel telegram-desktop python-pip flameshot neofetch vlc
yay -S code
yay -S slack-desktop
yay -S google-chrome

```
