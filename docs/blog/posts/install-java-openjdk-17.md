---
date:
  created: 2025-03-26
categories:
  - Technology
tags:
  - Java
---

# Install Java OpenJDK 17

There are several ways to install Java OpenJDK 17 on a Debian-based system, such as Ubuntu. One of the most straightforward methods is to use the terminal. Here’s how you can do it:

<!-- more -->

1. Update **apt** package
    ```bash
    sudo apt update
    ```

2. Install OpenJDK and JRE 17
    ```bash
    sudo apt-get install openjdk-17-jdk openjdk-17-jre -y
    ```

3. Check Java Version
    ```bash
    java -version
    ```
