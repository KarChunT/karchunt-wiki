---
date:
  created: 2025-03-28
categories:
  - Technology
tags:
  - Linux
---

# Add apt repository unable to support jammy

We will learn how to add an apt repository that is not officially supported on Ubuntu Jammy (22.04).

<!-- more -->

```bash
cd /usr/lib/python3/dist-packages
sudo cp apt_pkg.cpython-310-x86_64-linux-gnu.so apt_pkg.so
```
