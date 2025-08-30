---
date:
  created: 2025-04-20
categories:
  - Technology
tags:
  - Linux
  - NodeJS
links:
  - NodeSource: https://github.com/nodesource/distributions/blob/master/README.md
---

# Setup Node JS

There are multiple ways to install Node.js on your system. One of the most popular methods is to use the NodeSource PPA (Personal Package Archive).

<!-- more -->

## Installing Node JS using a NodeSource PPA

```bash
# Download the latest NodeSource setup script
curl -fsSL https://deb.nodesource.com/setup_lts.x -o nodesource_setup.sh
sudo -E bash nodesource_setup.sh

# Use either one of the following commands to install Node.js
sudo apt-get install -y nodejs or sudo apt-get install -y nsolid

# check node version
node -v
```
