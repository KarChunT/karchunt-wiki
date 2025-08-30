---
date:
  created: 2025-04-20
categories:
  - Technology
tags:
  - Linux
---

# Clear Linux History

To clear all history in Linux, you can use **either one** of the following command:

<!-- more -->

```bash
history -c # clear the current session history
cat /dev/null > ~/.bash_history # clear the history file
```

Additionally, you can use `export HISTSIZE=0` to set the **history size to **zero, which will **prevent any commands from being saved** in the history file.

If you want to ensure that the history is cleared for all users, you can login as the root user and clear the history files for each user in the `/home` directory.
