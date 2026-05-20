---
title: 'Devcontainers'
---

Devcontainers are a way of remotely or locally setting up a coding environment based on a preconfigured "blueprint".
This blueprint is used by Integrated Development Environments (IDEs) like VSCode, vscodium, IDEA, or Zed, to initiate and configure an environment for you.
This can make it much quicker to get up and running with lesson development.

## Getting Started with Devcontainers {#101-devcontainer}

To use devcontainers you need:

- Docker: please read the [Docker installation instructions](docker.md#101-docker) to install Docker Desktop or the Docker Engine for your operating system.
- An IDE that supports devcontainers: We recommend [VSCode](https://code.visualstudio.com/) as it has the most complete and easy to set up devcontainer support. 
  We acknowledge that VSCode is free but not completely open source.

Please note, if you are not comfortable with using Docker for the Workbench, we recommend going through the [manual installation](local_install.md#101-manual) steps below.

### Starting up the devcontainer

Make sure Docker Desktop is running and that you are connected to the Internet.

Open VSCode:

- either, by double clicking the icon in your OS, going to `File`, `Open Folder...`, and navigating to a lesson folder 
- or, open a terminal, navigate to a lesson folder and start VSCode by typing:

```bash
  cd ~/lessons/shell-novice
  code .
```

NB: Note the space between `code` and `.`!

Once VSCode has opened the folder, after a short time, a pop-up should appear in the bottom right of the IDE saying `Folder contains a Devcontainer configuration file. Reopen folder to develop in a container`, with an option button to `Reopen in container`.
Click this button and wait for VSCode to read the configuration file and setup the devcontainer environment.

:::::::::::::::::::: callout

### Troubleshooting

If this pop-up does not appear, open the command menu in VSCode with the <kbd>F1</kbd> function key.
Your cursor will appear in the command menu bar at the top of the window, prefixed with a `>` symbol.
Start typing `open folder` and select the `Dev Containers: Open Folder in Container...` option.

Similarly if you have any issues with the container at any point, you can open the command menu with <kbd>F1</kbd>, start typing `rebuild`, and select the `Dev Containers: Rebuild and Reopen in Container...`. This should be used judiciously as it will often reinstall dependencies so can take a few minutes.

::::::::::::::::::::::::::::

Various pop-ups will appear in the bottom right, showing progress.
You can click on the `Show log` link in any of the popups that show it to see any logs of the setup process.

The setup process can take a few minutes the first time you run it for a lesson.
After the first time, it will be much quicker to start subsequent uses of the environment as the Docker image would be downloaded and stored for reuse.

:::::::::::::::::::: callout

### Lessons with a lot of dependencies

For those R Markdown lessons that require a large number of R packages, this first start of the devcontainer can take quite a long time.

::::::::::::::::::::::::::::


### Running the Workbench

Open a terminal in VSCode by going to the `Terminal` menu in the top menu bar and click `New Terminal`.
An Ubuntu `bash` terminal window should appear in VSCode.
This bash shell will be running **inside** the devcontainer, so should look something like:

```bash
rstudio@55a86b63e4ab:~/lesson$ 
```

Here, you can perform any shell or R actions as you would usually for lesson development.

For more information, please check the full [devcontainer documentation](devcontainer.md).

::::::::::::::::::::: callout

### What if I don't want to use VSCode?

Sadly the devcontainer specification is only fully supported in a small number of IDEs.
VSCode is recommended in our lessons and it natively supports devcontainers.
Getting devcontainers to work in other fully open source IDEs like `vscodium` and `zed` are not as simple.

Therefore we would recommend using VSCode as whilst it is partially open source, it is a reliable and very well supported piece of software.

If this is not an option, then we recommend using the [Docker image directly](docker.md#101-docker) as it comes bundled with RStudio which you can use to work on your lesson.

**Sneaky extra:** If you want to run RStudio Server from VSCode, in a terminal shell running in the VSCode devcontainer, type:

```bash
~/start.sh
```

This will start the RStudio Server within the devcontainer, and you can then access RStudio by opening a web browser and going to `http://localhost:8787`. Fancy!

:::::::::::::::::::::::::::::

::::::::::::::::::::: callout

### Are devcontainers available for all lessons?

Devcontainer blueprints are already provided by our [workbench-template-rmd][rmd-template] and [workbench-template-md][md-template] lesson templates, so when creating a new lesson you will get access to devcontainers automatically.

However, not all Workbench-compatible lessons will have devcontainers enabled (a `.devcontainer` folder within the repository).
To add devcontainer support to a pre-existing lesson, please follow the [devcontainer import instructions](devcontainer.md#importing)

We will also be rolling these out into existing lessons across our official lesson programs too!

:::::::::::::::::::::::::::::

## Using a lesson's devcontainer

The first thing to check is that a lesson supports devcontainers.

::::::::::::::::::::::: callout

### Which lessons support devcontainers?

Any lesson that has:

- A `.devcontainer` folder in the root of its repository
- and a `Dockerfile` and `devcontainer.json` inside that folder

can be run inside a devcontainer.

An example can be seen in [this repository](https://github.com/carpentries/workbench-docs/tree/main/.devcontainer).

The base workbench templates ([md](https://github.com/carpentries/workbench-template-md/tree/main/.devcontainer) and [rmd](https://github.com/carpentries/workbench-template-rmd/tree/main/.devcontainer)) both specify a `.devcontainer` environment, so new lessons using this template will be able to immediately use devcontainers!

:::::::::::::::::::::::::::::::

Once a lesson has a `.devcontainer` folder, Dockerfile and JSON specification, an IDE like VSCode can be used to setup and run that devcontainer to host your lesson within that IDE.
This makes it quick and easy to start developing and building a lesson without needing to install any system or R packages or dependencies.

## Running the Workbench

### Updating the Workbench

By default, the devcontainer environment will use the `latest` version of the `carpentries-workbench` Docker image, i.e. `carpentries-workbench:latest`. These images are prebuilt.

When first opening a devcontainer-enabled lesson the devcontainer system will download the latest image for you.

If a new version of the Workbench is released, your devcontainer will not automatically use these new versions. To update the devcontainer image, open the VSCode command menu with <kbd>F1</kbd> and select the `Dev Containers: Rebuild Container` option.
This will download the new image version for you.

### Using a specific Workbench Docker version

Similarly, if you want to use a specific Workbench release, edit the `.devcontainer/Dockerfile` file, replacing `latest` on the first line with the version you require.

For example, to use Workbench version `dev-0.2.6`:

```bash
FROM carpentries/workbench-docker:latest
```

becomes

```bash
FROM carpentries/workbench-docker:dev-0.2.6
```

Save the file, and rebuild the container by opening the command menu with <kbd>F1</kbd> and selecting the `Dev Containers: Rebuild Container` option.

::::::::::::::::::::::: callout

### What Docker image versions are available?

The full list of Docker images and their version _tags_ are [on Dockerhub](https://hub.docker.com/r/carpentries/workbench-docker/tags).

:::::::::::::::::::::::::::::::


## What's next?

### Not used the Workbench before?

Please follow the [Building your first Workbench lesson](episodes/01-first-lesson.md) to familiarise yourself with the lesson build process.

### What content can go in a lesson?

Please check the [Lesson Content and Styling](episodes/02-content-styling.md) and [Additional Lesson Content](03-additional-content.md) documentation.

### Using additional R packages?

Please familiarise yourself with our [Packages and renv](episodes/04-r-and-renv.md) information.

### Lesson in a non-English language?

Please read our [Internationalisation](episodes/05-il8n.md) guide.


[rmd-template]: https://github.com/carpentries/workbench-template-rmd
[md-template]: https://github.com/carpentries/workbench-template-md