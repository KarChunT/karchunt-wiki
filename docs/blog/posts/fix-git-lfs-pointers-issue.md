---
date:
  created: 2025-03-28
categories:
  - Technology
tags:
  - Git
---

# Fix Git LFS pointers issue

To fix the Git LFS pointers issue, you can follow these steps:

<!-- more -->

```bash
git lfs migrate import --no-rewrite "file_path" "file_path"
git lfs ls-files | grep "file_path"
git lfs push origin --all
git push origin --all
```

Basically, the first comand is to reimport back those files into pointer files in LFS, without writing the history. Do take note that you can include as many `file_path` as you can.

Next, the second command is to help us to check whether the `file_path` already been imported as Git LFS pointers files.

Lastly, we just need to push back the LFS files and the contents to the repository itself.
