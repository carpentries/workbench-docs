---
title: 'Devcontainer Extras'
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

An example can be seen in [this repository](https://github.com/carpentries/workbench-docs/tree/main/.devcontainer).

The base workbench templates ([md](https://github.com/carpentries/workbench-template-md/tree/main/.devcontainer) and [rmd](https://github.com/carpentries/workbench-template-rmd/tree/main/.devcontainer)) both specify a `.devcontainer` environment, so new lessons using this template will be able to immediately use devcontainers!

:::::::::::::::::::::::::::::::

Once a lesson has a `.devcontainer` folder, Dockerfile and JSON specification, an IDE like VSCode can be used to setup and run that devcontainer to host your lesson within that IDE.
This makes it quick and easy to start developing and building a lesson without needing to install any system or R packages or dependencies.

### Using VSCode to start the devcontainer

Make sure Docker Desktop is running and that you are connected to the Internet.

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

:::::::::::::::::::: callout

### Troubleshooting

If this popup does not appear, open the command menu in VSCode with the `F1` function key.
Your cursor will appear in the command menu bar at the top of the window, prefixed with a `>` symbol.
Start typing `open folder` and select the `Dev Containers: Open Folder in Container...` option.

Similarly if you have any issues with the container at any point, you can open the command menu with `F1`, start typing `rebuild`, and select the `Dev Containers: Rebuild and Reopen in Container...`. This should be used judiciously as it will often reinstall dependencies so can take a few minutes.

::::::::::::::::::::::::::::

Various popups will appear in the bottom right, showing progress.
You can click on the `Show log` link in any of the popups that show it to see any logs of the setup process.

The setup process can take a few minutes the first time you run it for a lesson.
After the first time, it will be much quicker to start subsequent uses of the environment as the Docker image would be downloaded and stored for reuse.

## Running the Workbench

As all Workbench components are preinstalled in the devcontainer for you, you can start building your lesson!

Open a terminal in VSCode by going to the `Terminal` menu in the top menu bar and click `New Terminal`.
An Ubuntu `bash` terminal window should appear in VSCode.
This bash shell will be running **inside** the devcontainer, so should look something like:

```bash
rstudio@55a86b63e4ab:~/lesson$ 
```

Here, you can perform any shell or R actions as you would usually for lesson development.

### Updating the Workbench

By default, the devcontainer environment will use the `latest` version of the `carpentries-workbench` Docker image, i.e. `carpentries-workbench:latest`. These images are prebuilt.

When first opening a devcontainer-enabled lesson the devcontainer system will download the latest image for you.

If a new version of the Workbench is released, your devcontainer will not automatically use these new versions. To update the devcontainer image, open the VSCode command menu with `F1` and select the `Dev Containers: Rebuild Container` option.
This will download the new image version for you.

### Using a specific Workbench Docker version

Similarly, if you want to use a specific Workbench release, edit the `.devcontainer/Dockerfile` file, replacing `latest` on the first line with the version you require.

For example, to use Workbench version `dev-0.2.2`:

```bash
FROM carpentries/workbench-docker:latest
```

becomes

```bash
FROM carpentries/workbench-docker:dev-0.2.2
```

Save the file, and rebuild the container by opening the command menu with `F1` and selecting the `Dev Containers: Rebuild Container` option.


## What's next?

### Not used the Workbench before?

Please follow the [Building your first Workbench lesson](episodes/01-first-lesson.md) to familiarise yourself with the lesson build process.

### What content can go in a lesson?

Please check the [Lesson Content and Styling](episodes/02-content-styling.md) and [Additional Lesson Content](03-additional-content.md) documentation.

### Using additional R packages?

Please familiarise yourself with our [Packages and renv](episodes/04-r-and-renv.md) information.

### Lesson in a non-English language?

Please read our [Internationalisation](episodes/05-il8n.md) guide.

### Using different Workbench versions

The devcontainer will always use the `latest` version of 
