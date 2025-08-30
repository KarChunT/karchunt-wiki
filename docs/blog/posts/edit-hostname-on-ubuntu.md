---
date:
  created: 2025-03-28
categories:
  - Technology
tags:
  - Linux
---

# Edit hostname on Ubuntu

To change the hostname on Ubuntu, follow these steps:

<!-- more -->

1. Edit `/etc/hostname`
      ```bash
      sudo nano /etc/hostname
      ```

2. Replace any hostname you like. Save the file.
      ```bash title="/etc/hostname"
      hello-laptop
      ```

3. Reboot the system
      ```bash
      sudo reboot
      ```

4. Check your hostname
      ```bash
      hostname
      ```
