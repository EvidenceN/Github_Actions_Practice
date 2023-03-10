## **"ON" keyword**

“ON” Trigger event types for workflow - https://docs.github.com/en/actions/using-workflows/events-that-trigger-workflows

Activity types for ON events - https://docs.github.com/en/actions/using-workflows/workflow-syntax-for-github-actions#onevent_nametypes

Example of ON trigger events.  


```
on:
  pull_request:
    types: [opened, reopened]
```

Multiple events trigger syntax - 

`on: [push, pull_request]`

List format can be used even for one event trigger as well. 

`on: [push]`


## **ACTIONS and USES**

Actions can be more robust, providing more functionality than regular **multiple** run command.      

Actions utilize "uses" which executes action in the operating system.

**"USES" keyword requires us to put in where to find the code for the action.**

Actions can be sources from 3 different locations

- A public Repo
    - Example:
    - {owner}/{repo}@{ref}
    - octocet/super-cool-action@v1
- Same repo as the workflow
    - Example:
    - uses: ./path/to/the/action
    - uses: ./.github/actions/my-local-action
- A docker image.
    - Example:
    - uses: docker://{iamge}:{tag}
    - uses: docker://hellow-world:latest

## **RUN KEYWORD COMMAND**

- specify a command using "RUN Attribute" that will execute in the default shell system.
- For Ubuntu and MacOS systems, Default is BASH and POWERSHELL for windows systems.
- To run a command: RUN followed by the command, parameters, and arguments to execute. Example
    - Single like command
        - run: {command} {parameters} {arguments}
        - run: mv ./output ./archive (move command followed by the files/directories to move)
    - Multiline Command
        - run: |<br>
            Command 1 <br>
            Command 2