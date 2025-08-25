# Internal Tasks

!!! info
    Refer here for [Internal includes](../include-other-taskfile#internal-includes)

Internal tasks in Taskfile are used to **define tasks that are not intended to be run directly by users**. They are useful for **organizing utility tasks** that **support the main tasks** of your project **without cluttering the task list**.

```yaml title="Taskfile.yml"
version: '3'
tasks:
  secret-task:
    internal: true # [!code highlight]
    cmds:
      - echo "This is a secret task"
  public-task:
    cmds:
      - echo "This is a public task"
      - task: secret-task
```

```bash title="Demo and output"
ubuntu@touted-mite:~$ task -a
task: Available tasks for this project:
* public-task:       
```

In this case, it will only show the `public-task` in the task list, while `secret-task` is hidden from the user.
