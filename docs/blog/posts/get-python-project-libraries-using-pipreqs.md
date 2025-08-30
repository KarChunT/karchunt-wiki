---
date:
  created: 2025-04-26
categories:
  - Technology
tags:
  - Python
---

# Get Python Project Libraries Using pipreqs

To get the libraries used in a Python project, you can use the `pipreqs` tool. This tool scans your Python files and generates a `requirements.txt` file with the libraries used in your project.

```bash
pip install pipreqs
pipreqs /path/to/your/project --force

# verify the generated requirements.txt
cat requirements.txt
```