# Code Platoon Devcontainer
A development environment setup/configured for the Code Platoon curriculum.

## Prerequistites
- Docker Desktop
  > Mac, Linux, Windows (x64) or Raspberry Pi 4 4GB+ (ARMv8+ 64bit)
  > At least 4GB RAM
  > At least ~1.5GB free storage space
- [VSCode](https://code.visualstudio.com/)
- [Remote Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) - VSCode Extension

## How to use
The first time we run the steps below it will take far more time than the subsequent times. This is because the initial run the Docker image files needed dont exist and VSCode will download and prep the environment.

> Closing your VSCode window will automatically stop your running Docker containers. 
>
> Reopening VSCode to the parent (root) folder should always prompt you with a **Open in Container** which will start your Docker containers and relaunch VSCode into the context of those containers. Try not to close VSCode while it is performing setup for the first time.

1. Clone this current repo into a folder you are planning to designate as the parent (root) folder to where your code assignments folder will exist at. This repo will already provide a subfolder named `challenges` and `home` which both will be mounted inside our container. Honestly this can be wherever you want your code to live, as long as your user has access/permissions to that folder. Here are a few examples of this parent (root) folder.

   > Ex. Linux: `/home/<replace with your username path>/codeplatoon`

   > Ex. Mac: `/Users/<replace with your username path>/codeplatoon`

   > Ex. Windows: `C:\Users\<replace with your username path>\codeplatoon`

> **NOTE**: I will refer to this folder created by you from now on as **CP_ROOT**.

2. Open this **CP_ROOT** folder in VS Code either using VSCode's: **File -> Add Folder to Workspace** option or if you have the ability to type `code` in your terminal then `cd` into your **CP_ROOT** folder and type `code .`.

3. VSCode should prompt you with a popup that says: **Folder contains a Dev Container configuration file. Reopen folder to develop in a container** - Click the **Open in Container** button. This will relaunch VSCode but inside the context of the Docker container it is about to spin up for us.

4. When the Remote Container progress bar completes you should be able to open a new terminal inside VS Code and should be presented with a terminal that shows: 

   ```bash
   dev@devtools:/challenges $
   ```

5. If you see this, your environment is **READY**.

You can type `allversions` in the terminal to display the current versions of different executables already installed and ready to go in your environment. From this point you should be able to start working on your coding assignments, you will need VSCode opened inside your parent (root) folder which will always reopen inside your `/challenges` folder as the context for your working directory. 

## Things to understand && terminology
We are inside a Ubuntu environment, yes you are basically running a lightweight Linux distro even if you are running this on Mac/Windows or a Raspberry Pi the devtools terminal that runs believes it is in-fact running on Ubuntu.

**Host Machine** - This is YOUR computer the one you are on, the one that is running Docker and the containers.

**Docker Image**: This is basically a blueprint of an environment, a starting point, that lays out the configuration of a given "service". In our case our service is a Bash shell running on Ubuntu.

**Docker Container** - A single contained instance based off a Docker Image. Technically we could spin up MANY different container "instances" based off the same Docker Image. For our case VSCode just spins up 1 instance because we are using it just to leverage the bash environment and all the executables that have been setup.

## Extras included in the Environment
Predefined Aliases:
- `pymk` -> `python manage.py makemigrations`
- `pymg` -> `python manage.py migrate`
- `pyrs` -> `python manage.py runserver`

Packages
- [green](https://pypi.org/project/green/) - Colorized test runner for Python.
- [pytest](https://pypi.org/project/pytest/) - PyTest, another way to write tests.
- [Virtualenvwrapper](https://virtualenvwrapper.readthedocs.io/en/latest/) for creating Python environments, an alternative workflow instead of using `python -m venv`.

## Issues
If you run into errors with any of the steps listed above. Please reach out to the instructors to help determine if you should submit an issue against this repo.