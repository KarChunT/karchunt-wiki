# Environment Variables

## Environment variable in Taskfile

There are two ways to declare environment variables in Taskfile:

1. Using a `.env` file via the `dotnet` option in the Taskfile.
2. Using `env` option in the Taskfile.

<br />
If you want to **override the value of an environment variable**, you have to reference it using the `$ENV_NAME` format in the Taskfile, not `{{.ENV_NAME}}`. You can refer below for more details.

- `export STAGE=dev` will **override** the value of `STAGE` defined in `.env` file or `env` option in the Taskfile.

### Using .env file

!!! info
    You can specify `dotnet` option in **global** or **task level**.

```text
/home/<user>/
├── Taskfile.yml
├── .env
└── test/
    └── .env
```

Assume you have the following content:

=== "~/.env"

    ```text
    STAGE=test
    ```

=== "test/.env"

    ```text
    ENDPOINT=testing.com
    ```

```yaml title="Taskfile.yml"
version: '3'

dotenv: # global/system environment variables for all tasks
  - '.env'

env:
  MYENV: test

tasks:
  hello:
    dotenv: ['{{ .MYENV }}/.env', '{{ .HOME }}/.env']
    cmds:
      - 'echo "Endpoint is: $ENDPOINT, Stage is: $STAGE"'
```

- `.HOME` is a **magic variable** that **refers to the home directory** of the user.
- `export STAGE=dev`, if **set explicitly in the environment**, it will **override** the value of `STAGE` defined in `.env` file.
  - but if you set `export MYENV=prod`, it will **not override** the value of `MYENV` defined in Taskfile.

```bash title="demo and output"
ubuntu@touted-mite:~$ task hello 
task: [hello] echo "Endpoint is: $ENDPOINT, Stage is: $STAGE"
Endpoint is: testing.com, Stage is: test

# Override the value of STAGE
ubuntu@touted-mite:~$ export STAGE=dev
ubuntu@touted-mite:~$ task hello 
task: [hello] echo "Endpoint is: $ENDPOINT, Stage is: $STAGE"
Endpoint is: testing.com, Stage is: dev

# Try to override MYENV but it will not override
ubuntu@touted-mite:~$ export MYENV=dev
ubuntu@touted-mite:~$ task hello 
task: [hello] echo "Endpoint is: $ENDPOINT, Stage is: $STAGE"
Endpoint is: testing.com, Stage is: dev
```

### Using env option

```yaml title="Taskfile.yml"
version: '3'

env: # global/system environment variables for all tasks
  HOME: /root

tasks:
  msg:
    env:
      MESSAGE: Hello
    cmds:
      - 'echo "Message is: $MESSAGE"'
      - 'echo "Home directory is $HOME"'
```

## Override dotenv variable using env option

```text title=".env"
ENDPOINT=testing.com
```

```yaml title="Taskfile.yml"
version: '3'

tasks:
  hello:
    dotenv:
      - '.env'
    env:
      ENDPOINT: dev.com # Override the value of ENDPOINT [!code highlight]
    cmds:
      - 'echo "Endpoint is: $ENDPOINT"'
```

```bash title="demo and output"
ubuntu@touted-mite:~$ task hello 
task: [hello] echo "Endpoint is: $ENDPOINT"
Endpoint is: dev.com
```
