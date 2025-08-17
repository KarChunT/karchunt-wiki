# Reset and Revert

Sometimes we commit changes that we don't intend to commit. If that is the case, we have several options to undo the action.

- [Revert](#revert)
- [Reset](#reset)
    - [soft](#soft)
    - [hard](#hard)
    - [mixed](#mixed)

## Revert

!!! info
    If you want to undo changes and keep them in your Git history, you can use the
    `git revert` command

The `git revert` command will **create a new commit**, which **reverses** all the changes made on the specified commit. Let's say that we want to revert the commit where we create the `test` file.

```mermaid
---
config:
  logLevel: 'debug'
  theme: 'default'
  themeVariables:
      'git0': '#ff0000'
      'git1': '#ff00ff'
      'git2': '#00ffff'
      'git3': '#ffff00'
      'git4': '#ff00ff'
      'git5': '#00ffff'
---
gitGraph
  commit id: "docs: create first story"
  commit id: "docs: create second story"
  commit id: "docs: create programming"
  commit id: "docs: create test"
```

```bash
git revert <docs: create test-commit-id>
```

```mermaid
---
config:
  logLevel: 'debug'
  theme: 'default'
  themeVariables:
      'git0': '#ff0000'
      'git1': '#ff00ff'
      'git2': '#00ffff'
      'git3': '#ffff00'
      'git4': '#ff00ff'
      'git5': '#00ffff'
---
gitGraph
  commit id: "docs: create first story"
  commit id: "docs: create second story"
  commit id: "docs: create programming"
  commit id: "docs: create test"
  commit id: "Revert docs: create test"
```

- In the "docs: create test" commit, `test` file has created. The reverted commit contains all the opposite changes. It will then deletes the `test` file.

![git-sim-revert](../../assets/git/git-sim-revert.png)

[Watch animation](../../assets/git/git-sim-revert.webm)

## Reset

The another way is to use the `git reset` command. There are three ways to reset the commit to undo it.

- soft
- hard
- mixed

### soft

With the `--soft` flag, we still have all the changes that we have made, and these changes will **move to staged changes**. You can use `git status` to check all the staged changes.

```mermaid
---
config:
  logLevel: 'debug'
  theme: 'default'
  themeVariables:
      'git0': '#ff0000'
      'git1': '#ff00ff'
      'git2': '#00ffff'
      'git3': '#ffff00'
      'git4': '#ff00ff'
      'git5': '#00ffff'
---
gitGraph
  commit id: "docs: create first story"
  commit id: "docs: create second story"
  commit id: "docs: create programming"
  commit id: "docs: create test"
  commit id: "docs: create hello"
```

Let's reset the "docs: create hello" commit with a soft flag. Reset commands also receive the number of commits that we want to reset, in this case we want to reset one commit.

```bash
git reset --soft <commit-id>
git reset --soft HEAD~1
```

```mermaid
---
config:
  logLevel: 'debug'
  theme: 'default'
  themeVariables:
      'git0': '#ff0000'
      'git1': '#ff00ff'
      'git2': '#00ffff'
      'git3': '#ffff00'
      'git4': '#ff00ff'
      'git5': '#00ffff'
---
gitGraph
  commit id: "docs: create first story"
  commit id: "docs: create second story"
  commit id: "docs: create programming"
  commit id: "docs: create test"
```

![git-sim-reset-soft](../../assets/git/git-sim-reset-soft.png)

[Watch animation](../../assets/git/git-sim-reset-soft.webm)

### hard

With the `--hard` flag, we will lose all the changes that we have made on that commit.

```mermaid
---
config:
  logLevel: 'debug'
  theme: 'default'
  themeVariables:
      'git0': '#ff0000'
      'git1': '#ff00ff'
      'git2': '#00ffff'
      'git3': '#ffff00'
      'git4': '#ff00ff'
      'git5': '#00ffff'
---
gitGraph
  commit id: "docs: create first story"
  commit id: "docs: create second story"
  commit id: "docs: create programming"
  commit id: "docs: create test"
  commit id: "docs: create hello"
```

Let's reset the "docs: create hello" commit with a hard flag.

```bash
git reset --hard <commit-id>
git reset --hard HEAD~1
```

```mermaid
---
config:
  logLevel: 'debug'
  theme: 'default'
  themeVariables:
      'git0': '#ff0000'
      'git1': '#ff00ff'
      'git2': '#00ffff'
      'git3': '#ffff00'
      'git4': '#ff00ff'
      'git5': '#00ffff'
---
gitGraph
  commit id: "docs: create first story"
  commit id: "docs: create second story"
  commit id: "docs: create programming"
  commit id: "docs: create test"
```

![git-sim-reset-hard](../../assets/git/git-sim-reset-hard.png)

[Watch animation](../../assets/git/git-sim-reset-hard.webm)

### mixed

With the `--mixed` flag, we still have all the changes that we have made, and these changes will **move to unstaged changes**. You can use `git status` to check all the unstaged changes.

```mermaid
---
config:
  logLevel: 'debug'
  theme: 'default'
  themeVariables:
      'git0': '#ff0000'
      'git1': '#ff00ff'
      'git2': '#00ffff'
      'git3': '#ffff00'
      'git4': '#ff00ff'
      'git5': '#00ffff'
---
gitGraph
  commit id: "docs: create first story"
  commit id: "docs: create second story"
  commit id: "docs: create programming"
  commit id: "docs: create test"
  commit id: "docs: create hello"
```

Let's reset the "docs: create hello" commit with a mixed flag.

```bash
git reset --mixed <commit-id>
git reset --mixed HEAD~1
```

```mermaid
---
config:
  logLevel: 'debug'
  theme: 'default'
  themeVariables:
      'git0': '#ff0000'
      'git1': '#ff00ff'
      'git2': '#00ffff'
      'git3': '#ffff00'
      'git4': '#ff00ff'
      'git5': '#00ffff'
---
gitGraph
  commit id: "docs: create first story"
  commit id: "docs: create second story"
  commit id: "docs: create programming"
  commit id: "docs: create test"
```

![git-sim-reset-mixed](../../assets/git/git-sim-reset-mixed.png)

[Web animation](../../assets/git/git-sim-reset-mixed.webm)
