# Task Aliases

!!! info
    Refer [here](../include-other-taskfile#namespace-aliases-shortform) for namespace aliases.

You can create **aliases for tasks** in Taskfile to simplify command execution. This allows you to define shorter or more intuitive names for tasks, making it easier to run them.

```yaml title="Taskfile.yaml"
version: '3'
tasks:
  complex-task-name:
    aliases: [complex]
    cmds:
      - echo "This is a complex task name"
```
