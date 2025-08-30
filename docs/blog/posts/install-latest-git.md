---
date:
  created: 2025-03-26
categories:
  - Technology
tags:
  - Git
links:
  - PPA Git: https://launchpad.net/~git-core/+archive/ubuntu/ppa?ref=itsfoss.com
---

# Install latest Git

Learn how to install the latest version of Git on your system.

<!-- more -->

1. Install stable Git version

    ```bash
    sudo add-apt-repository ppa:git-core/ppa
    sudo apt-get update
    sudo apt-get install git
    ```

2. Check Git version
    ```bash
    git --version
    ```

3. Optional: Configure Git
    ```bash
    git config --global user.name "Your name"
    git config --global user.email "Your email"

    # enable color output
    git config --global color.ui author

    # check configuration
    git config --global --list
    ```
