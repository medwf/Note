Let’s automate things. Everything.

Let’s also figure out a way to do this using a single tool. One that is easy to program, easy to use. And why not do all this with nothing but SSH installed on the remote machine – all commands scripted at a single location for executing locally or on any number of various servers.

Use Cases fabric :

- Deployments
- Maintenance tasks
- Anything repetitious
- Especially on remote servers

Fabric provides a command-line interface (CLI) that allows you to define tasks and execute them on remote servers. Here are some basic concepts related to the Fabric command-line interface:

1. Fabric and Python Programming Language
2. System/Server Administration
3. Application Deployment

1. **Task**: In Fabric, a task is a function or a set of commands that you define to be executed on one or more remote servers.

2. **fab Command**: The primary command-line tool for interacting with Fabric is called `fab`. You use it to run tasks defined in your Fabric script.

3. **Fabric Script**: A Fabric script is a Python file that contains the tasks you want to execute remotely. It often includes the definition of hosts (remote servers), user credentials, and the tasks themselves.

Here's a simple example of a Fabric script (`fabfile.py`):

from fabric import task

@task

def hello(c):

    print("Hello, Fabric!")

@task

def deploy(c):

    # Your deployment logic here

    print("Deploying the application...")

You can run these tasks using the `fab` command:

- fab hello
- fab deploy

Note that Fabric is not limited to the examples provided here; it can be customized to perform various tasks, such as code deployment, server configuration, and more.

If you were referring to a different context or tool when mentioning "fabric command line," please provide additional details for clarification.

Install fabric :

- pip uninstall  fabric
- pip install 'fabric<2.0'
- export PATH="$PATH:/home/ubuntu/.local/bin"