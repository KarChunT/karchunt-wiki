# Basic

## How to get started with Taskfile

### Step 1: Create your Taskfile

There are multiple ways to create a **Taskfile**.

- Create a Taskfile in the **current directory**
- Create a Taskfile in a **specific directory**
- Create a Taskfile with a **custom filename**
- **Manually** create a Taskfile

```bash
# This will create a Taskfile.yml in the current directory
task --init

# This will create a Taskfile.yml in the specified directory
# Make sure the directory exists
task --init ./directory-path

# This will create a custom Taskfile
task --init CustomTaskfile.yml

# Manually create a Taskfile
touch Taskfile.yml
```

### Step 2: Open the Taskfile in your favorite text editor.

The Taskfile will look like this:

```yaml title="Taskfile.yml"
version: '3'

vars:
  GREETING: Hello, World!

tasks:
  default:
    cmds:
      - echo "{{.GREETING}}"
    silent: true
```

- The task name is `default`.
- You can **define more tasks** by adding them to the `task` section.

Here is a breakdown of the Taskfile:

| Field | Description |
| ----- | ----------- |
| `version` | The version of the Taskfile format to run |
| `vars` | Variables that can be used in the Taskfile |
| `tasks` | The tasks to run |
| `cmds` | The commands to run |
| `silent` | If true, The tasks metadata will not be printed, it will only print the output of the command. |


### Step 3: Add a new task to the Taskfile

```yaml title="Taskfile.yml"
version: '3'

vars:
  GREETING: Hello, World!

tasks:
  default:
    cmds:
      - echo "{{.GREETING}}"
    silent: true
  hello:
    cmds: # commands to run
      - echo 'Hello World from Task!' > output.txt
```

### Step 4: Call a task

!!! info "More Info"
    You can use `task --help` to see all available options and flags.

When you run the `task` command, it will **look for a Taskfile** in the **current directory** or in the **specified directory**.

```bash
task <task-name>

# run the task in the current directory
task default

# run the task in the specified directory
task --dir ./directory-path default

# run the task with a custom Taskfile
task --taskfile CustomTaskfile.yml default
```

In this case, we will run the `hello` task that we just added to the Taskfile.

```bash
task hello
```

### Step 5: Verify the output by checking the contents of `output.txt`

```bash
cat output.txt
```

You should see the following output:

```text title="output.txt"
Hello World from Task!
```
