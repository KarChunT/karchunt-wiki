---
date:
  created: 2025-03-28
categories:
  - Technology
tags:
  - Docker Compose
---

# Fix Docker Compose error - max virtual memory areas vm.max_map_count 65530 is too low, increase to at least 262144

To resolve this issue, you need to increase the `vm.max_map_count` setting in your system.

<!-- more -->

Increase VM max map count to the respective value.

```bash
sudo sysctl -w vm.max_map_count=262144
```
