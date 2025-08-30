---
date: 
  created: 2025-03-28
categories:
  - Technology
tags:
  - Docker
---

# Fix docker permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock

When you try to run a Docker command and get a permission denied error, it usually means that your user is not part of the Docker group. Here are the steps to fix this issue:

<!-- more -->

```bash
sudo groupadd docker
sudo usermod -aG docker $USER
newgrp docker
sudo chmod 666 /var/run/docker.sock

docker ps # test connection
```
