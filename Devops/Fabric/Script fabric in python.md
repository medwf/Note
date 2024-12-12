```python

#!/usr/bin/python3

"""import fabric.api"""

from fabric.api import *

# env: manage all setting of fabric file.

# define ssh config is exist = True, it is false in default

env.use_ssh_config = True

# env.hots: define which hots server

# env.hosts = ['web01', 'web02'] # u can define one or more hosts

# task if the way to tell fabric that is task methods

@task

def my_host():

    """have your host name"""

    # run command localy

    local('uname -s')

    # run command remotly.

    run('whoami')

# parallel tell fabric i want to execute this function in all hosts in sametimes

@task

@parallel

def Rn():

    local('uname -s')

# runs_once tell fabric i want to execute this function in all hosts in sametimes

@task

@runs_once

def Rn():

    local('uname -s')

# ________________________________Example repo in remote server__________________________ #

@task

def clone():

    """this method help to clone your repo in ~/ALX folder"""

    # run is a function that run command in remote server

    run('ls ~/')

    run('mkdir -p ~/ALX')

    # cd is a function that change directory to THE PATH to want to.

    with cd('~/ALX'):

        # in This path do this.

        run('git clone [https://token@github.com/medwf/AirBnB_clone_v2.git'](https://token@github.com/medwf/AirBnB_clone_v2.git'))

@task

def pull():

    """this function help to git pull repo"""

    with cd('~/ALX/AirBnB_clone_v2'):

        run('git pull')

#

#!/usr/bin/python3

"""

import modules

this file is fabfile

"""

from fabric.api import local, task, env, put, run

from datetime import datetime

import os

env.hosts = ['100.25.110.123', '54.208.156.46']

env.user = 'ubuntu'

@task

def do_pack():

    """

    this function execute script that generates a .tgz

        archive from the contents of the web_static folder

    """

    local("mkdir -p versions")

    date = datetime.now().strftime("%Y%m%d%H%M%S")

    file_path = f'versions/web_static_{date}.tgz'

    print(f'Packing web_static to {file_path}')

    try:

        local(f"tar -czvf {file_path} web_static")

        size = os.path.getsize(file_path)

        print(f'web_static packed: {file_path} -> {size}Bytes')

        return file_path

    except Exception:

        return None

@task

def do_deploy(archive_path):

    """this function distributes an archive to your web servers"""

    if os.path.exists(archive_path):

        File = os.path.basename(archive_path)

        Dir = os.path.splitext(File)[0]

        FullPath = "/data/web_static/releases/{}".format(Dir)

        put(archive_path, "/tmp/")

        run("rm -rf {}".format(FullPath))

        run("mkdir -p {}/".format(FullPath))

        run("tar -xzf /tmp/{} -C {}/".format(File, FullPath))

        run("rm /tmp/{}".format(File))

        run("mv {0}/web_static/* {0}/".format(FullPath))

        run("rm -rf {}/web_static".format(FullPath))

        run("rm -rf /data/web_static/current")

        run("ln -s {} /data/web_static/current".format(FullPath))

        print("New version deployed!")

        return True

    return False
 ```