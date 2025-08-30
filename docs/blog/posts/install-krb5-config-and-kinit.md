---
date:
  created: 2025-07-01
categories:
  - Technology
tags:
  - Kerberos
  - krb5-config
  - kinit
---

# Install krb5-config and kinit

To install `krb5-config` and `kinit`, you can use the following commands based on your Linux distribution:

<!-- more -->

```bash
sudo apt update
sudo apt install -y libkrb5-dev krb5-user
```

Check `krb5-config` installation by running:

```bash
which krb5-config && krb5-config --version
```

You might faced an error about **missing C compiler**. This is normal if you only need the configuration tool itself. However, if you need full functionality, you can install build essential packages:

```bash
sudo apt install -y build-essential
```

To check if `kinit` is installed, run:

```bash
which kinit && kinit
```
