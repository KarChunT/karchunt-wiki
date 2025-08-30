---
date:
  created: 2025-05-10
categories:
  - Technology
tags:
  - Linux
  - Docker
---

# Check Docker APT repo

To determine which Linux distribution the Docker installation is configure to download from, you can check the Docker APT repository configuration on your system.

<!-- more -->

## Step 1: **Inspect Docker APT repository**/**Check the Repository** file.

If the repository is found in a file (e.g., `/etc/apt/sources.list.d/docker.list`), you can inspect it directly:

```bash
# option 1: inspect the docker apt repository
grep -r "download.docker.com" /etc/apt/sources.list /etc/apt/sources.list.d/

# option 2: check the repository file
cat /etc/apt/sources.list.d/docker.list
```

If you see **multiple entries** for `download.docker.com` in your APT sources, you can determine which one is being used by checking the pinned priority or by inspecting the package metadata.


## Step 2: Look for the Distribution name.

In the output, look for the distribution name (e.g., focal, jammy, bullseye). It will look something like this:

```text
deb [arch=amd64] https://download.docker.com/linux/ubuntu jammy stable
```

## Step 3: Verify the current distribution

To confirm the distribution your system is running, use:

```bash
lsb_release -cs
```

This will return the codename of your distribution (e.g., jammy for Ubuntu 22.04).

## Step 4: Compare the results

Ensure that the distribution in the Docker repository **matches** your system's distribution. If they don't match, you may need to **update** the repository configuration.
