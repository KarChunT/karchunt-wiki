---
date:
  created: 2025-06-27
categories:
  - Technology
tags:
  - Linux
  - Ubuntu
  - Chrome
---

# Unable to open X display when trying to run Google Chrome on Ubuntu

When you try to run Google Chrome on Ubuntu and encounter the following error:

<!-- more -->

```bash
[4520:4520:0529/072952.636189:ERROR:ui/ozone/platform/x11/ozone_platform_x11.cc:248] Missing X server or $DISPLAY
[4520:4520:0529/072952.636223:ERROR:ui/aura/env.cc:257] The platform failed to initialize.  Exiting.
```

This indicates that the X server is not running or the `$DISPLAY` environment variable is not set correctly. Here are some steps to resolve this issue:

## Step 1: Install `Xvfb` if haven't install.

It does not require additional hardware.
```bash
sudo apt-get install -y xvfb
```

## Step 2: Install some dependencies to make "**headless**" Chrome/selenium work

```bash
sudo apt-get -y install xorg xvfb gtk2-engines-pixbuf
sudo apt-get -y install dbus-x11 xfonts-base xfonts-100dpi xfonts-75dpi xfonts-cyrillic xfonts-scalable
```

## Step 3: (Optional) Install dependencies for capturing screenshots of Xvfb display

```bash
sudo apt-get -y install imagemagick x11-apps
```

## Step 4: Make sure that `Xvfb` stars every time the box/vm is booted.

You can add the above commands to your `.bashrc` or `.profile` file to ensure they are executed every time you log in.

```bash
Xvfb -ac :99 -screen 0 1280x1024x16 &
export DISPLAY=:99
```

## Step 5: Rerun the Google chrome command

```bash
google-chrome
```
