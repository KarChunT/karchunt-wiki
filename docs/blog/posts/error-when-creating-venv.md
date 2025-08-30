---
date:
  created: 2025-04-26
categories:
  - Technology
tags:
  - Python
  - venv
---

# Error when creating venv

When creating a virtual environment in Python, you might encounter the following error:

<!-- more -->

```bash
python -m venv venv

# Error message:
Error: Command '['/home/ubuntu/venv/bin/python', '-m', 'ensurepip', '--upgrade', '--default-pip']' returned non-zero exit status 1.
```

This error typically occurs when the `ensurepip` module fails to install `pip` in the virtual environment. Here are some steps to resolve this issue:

```bash
# Check python version
python --version # in this case, mine is 3.13.1
sudo apt install python3.13-venv # replace your version accordingly

python3.13 -m venv myenv
```