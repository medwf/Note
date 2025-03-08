Fab command :

- fab [options] <command> [:arg1,arg2=val2,host=foo,hosts='h1;h2',...] …
- List all tasks function in fabfile:

- fab -l
- fab --list

• fab [options] <command> [:arg1,arg2=val2,host=foo, hosts='h1;h2',...] …

    • List all tasks function in fab_file:

        ○ fab -l

        ○ fab --list

    • define hots in command-line:

        # the command should execute in multi hosts that you define.

        * fab -H <hosts name> # one host

        * fab -H <hosts name>,<hostname>,<hosts name> # multi hosts

        # to excluded specific <hostname>

        * fab -H user@host1,user@host2 -x user@host2 my_task

            # In this case, the my_task will be executed only on host1,

            # as host2 is excluded using the -x flag.

    * fab -f 2-do_deploy_web_static.py do_deploy:archive_path=versions/web_static_20170315003959.tgz -i my_ssh_private_key -u ubuntu

File fabfile.py

From fabric.api import *

# to define hosts with ssh config u have to use this :

Env.use_ssh_config = True

Def connect_with_remote_server():

Env.hosts = ['name alias of your config ssh']

Def name_function():

What you wanna do …

Local : make command locally .

Run : make command in remote server

Sudo : make command in super user

Cd : change working directory syntax is `with cd('directory')`: do