---
title: 'Devcontainer Extras'
---

It is good practice to use separate environments when developing software.
Many solutions exist across different programming languages and operating systems.

The Workbench needs additional system and R dependencies to work, and these can be time consuming to install.
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

For example, to use Workbench version `dev-0.2.2`:

```bash
FROM carpentries/workbench-docker:latest
```

becomes

```bash
FROM carpentries/workbench-docker:dev-0.2.2
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
