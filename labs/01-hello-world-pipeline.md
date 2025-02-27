## Making "hello world"

Github Actions is configured through the YAML files.
In order for us to make the first `hello world` script, examine the following example:

```yaml
name: hello-world
on: push
jobs:
  my-job:
    runs-on: ubuntu-latest
    steps:
      - name: my-step
        run: echo "Hello World!"
```

Github Actions configuration files are written in `yaml`, and follow a follow a simple structure.
The trickiest part of writing the configuration files is typically getting the indentation right.

### Let’s examine the example:

- Line 1: The `name` attribute provides useful organizational information when returning warnings, errors, and output. The name should be meaningful to you as an action within your build process.
- Line 2: The `on` is the name of the GitHub event that triggers the workflow.
- Line 3: The `jobs` level contains a collection of jobs that make up the workflow.
- Line 4-5: The `my-job` is an example of the name for a job, `runs-on` describes on which operating system the pipeline should run.
- Line 6-8: The `steps` collection is an ordered list of `run` directives. Each `run` directive is executed in the order in which it is declared.

# Task

- Paste the example into `.github/workflows/hello-world.yaml`. Commit the file and push it to Github. Then, go to Github Actions and check the action status.

You should see something like this in the logs of Github Actions: (Note: The logs can be a bit hard to find the first time :-), but give it a shot)

```bash
#!/bin/sh -eo pipefail
echo 'Hello World!'

Hello World!
```
