---
date: 
  created: 2025-06-27
categories:
  - Technology
tags:
  - Linux
  - Chrome
---

# Install Google Chrome using a .deb file

There are several ways to install Google Chrome on a Debian-based system, such as Ubuntu. One of the most straightforward methods is to download the .deb file directly from Google's official website and install it using the terminal. Here’s how you can do it:

<!-- more -->

```bash
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
sudo dpkg -i google-chrome-stable_current_amd64.deb

# when you faced Issues when install google, run the below command
sudo apt --fix-broken install or sudo apt-get install -f
```

After the installation is complete, you can launch Google Chrome from your applications menu or by running the following command in the terminal:

```bash
# choose either one command to launch Google Chrome
google-chrome
google-chrome-stable
```