---
date:
  created: 2025-03-26
categories:
  - Technology
tags:
  - Java
links:
  - Documentation: https://www.digitalocean.com/community/tutorials/how-to-install-java-with-apt-on-ubuntu-22-04
---

# Install Java with APT on Ubuntu

Learn how to install Java with APT on Ubuntu.

<!-- more -->

1. Update **apt** package

    ```bash
    sudo apt update
    ```

2. Install JRE

    ```bash
    sudo apt install default-jre
    ```

3. Verify Java installation

    ```bash
    java -version
    ```

4. Install Java JDK

    ```bash
    sudo apt install default-jdk
    ```

5. Verify Java JDK installation
    ```bash
    javac -version
    ```
