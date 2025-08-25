# Run task in specific order

We know that dependencies **actually run in parallel**, so dependencies are **not guaranteed to run in order**. If you want to **run tasks in a specific order** or **run serially**, then you can do the following:

```yaml title="Taskfile.yml"
version: '3'
tasks:
  build:
    desc: Build the project
    cmds:
      - echo "Building the project..."

  test:
    desc: Run tests
    cmds:
      - echo "Running tests..."

  lint:
    desc: Lint the code
    cmds:
      - echo "Linting code..."

  all:
    desc: Run lint, build, and test in order
    cmds:
      - task: lint # [!code highlight]
      - task: build # [!code highlight]
      - task: test # [!code highlight]
      - echo "All tasks completed!"
```