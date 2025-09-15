---
title: 'Devcontainers'
---

It's good practice to use separate environments when developing software.
Many solutions exist across different programming languages and operating systems.

The Workbench needs additional system and R dependencies to work, and these can be long-winded to install.
As such, we provide specific separate environments using Docker which have all the required dependencies installed for you, so you can get to using the Workbench straight away on any PC or operating system that supports Docker.

:::::::::::::::::::::: prereq

You will need to have followed the [101 Quick Setup](learners/setup.md#101-docker) instructions for Docker to proceed.

We also presume you have installed and are using the VSCode IDE, which can be installed using the following [link](https://code.visualstudio.com/)

:::::::::::::::::::::::::::::

## Using a lesson's devcontainer

The first thing to check is that a lesson supports devcontainers.

::::::::::::::::::::::: callout

### Which lessons support devcontainers?

Any lesson that has:

- A `.devcontainer` folder
- A `Dockerfile` and `devcontainer.json` inside that folder

in the root of its repository can be run inside a devcontainer.

An example can be seen in the [x](TODO.md) repository.

The base workbench templates ([md](https://github.com/carpentries/workbench-template-md/tree/main/.devcontainer) and [rmd](https://github.com/carpentries/workbench-template-rmd/tree/main/.devcontainer)) both specify a `.devcontainer` environment, so new lessons using this template will be able to immediately use devcontainers!

:::::::::::::::::::::::::::::::

Once a lesson has a `.devcontainer` folder, Dockerfile and JSON specification, an IDE like VSCode can be used to setup and run that devcontainer to host your lesson within that IDE.
This makes it quick and easy to start developing and building a lesson without needing to install any system or R packages or dependencies.

### Using VSCode to start the devcontainer

Make sure Docker Desktop is running.

Open VSCode:

- either, by double clicking the icon in your OS, going to `File`, `Open Folder...`, and navigating to a lesson folder 
- or, open a terminal, navigate to a lesson folder and type:

```bash
  cd ~/lessons/shell-novice
  code .
```

NB: Note the space between `code` and `.`!

Once VSCode has opened the folder, after a short time, a popup should appear in the bottom right of the IDE saying `Folder contains a Devcontainer configuration file. Reopen folder to develop in a container`, with an option button to `Reopen in container`.
Click this button and wait for VSCode to read the configuration file and setup the devcontainer environment.

Various popups will appear in the bottom right, showing progress.
You can click on the `Show log` link in any of the popups that show it to see any logs of the setup process.

The setup process can take a while the first time you run it for a lesson.
After the first time, it will be much quicker to start subsequent uses of the environment.
