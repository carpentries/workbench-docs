---
title: 'Docker'
---

It is good practice to use separate environments when developing software.
Many solutions exist across different programming languages and operating systems.

The Workbench needs additional system and R dependencies to work, and these can be time consuming to install.
As such, we provide specific separate environments using Docker which have all the required dependencies installed for you, so you can get to using the Workbench straight away on any PC or operating system that supports Docker.

## Getting started with Docker {#101-docker}

:::::::::::::::::::::: prereq

You will need to have followed the [101 Quick Setup](setup.md#101-docker) instructions for Docker to proceed.

We also presume you have installed and are using the VSCode IDE, which can be installed using the following [link](https://code.visualstudio.com/)

:::::::::::::::::::::::::::::

The Workbench development team provides Docker images of each release of the Workbench that are used for our GitHub workflows that build our core curriculum lessons.
You can use these Docker images to run the Workbench on your local system too!

Docker Desktop is available for all operating systems (Windows, Mac and Linux), so we recommend installing this.

### Docker Desktop

Install Docker Desktop for [your operating system](https://docs.docker.com/desktop/).

Once installed, choose one of the following ways to interact with the Docker system:

1. Via the Docker Desktop GUI app
2. Via the command line terminal (bash on Linux/Windows WSL/git bash, terminal on the Mac)

### Running the Workbench Docker container

After Docker Desktop/Docker Engine is set up, you can use the following command from the terminal (`git bash`, WSL, or MacOS Terminal app):

```bash
# go home
cd ~

# make a `lessons` folder in your home directory and clone in a lesson
mkdir ~/lessons
cd ~/lessons
git clone git@github.com:swcarpentry/shell-novice.git

# create a workbench-lessons named volume, and copy in the shell-novice content
curl -s https://raw.githubusercontent.com/carpentries/workbench-docker/main/scripts/setup_named_volume.sh | bash -s -- ~/lessons/shell-novice

# start the workbench container
curl -s https://raw.githubusercontent.com/carpentries/workbench-docker/main/scripts/run_workbench.sh | bash
```

Or with `docker run` directly, if you want to control various docker options:

```bash
docker run --name carpentries-workbench \
           -p 8787:8787 \
           -v ~/.ssh:/home/rstudio/.ssh:ro \
           -v ~/.gitconfig:/home/rstudio/.gitconfig \
           -e DISABLE_AUTH=true \
           -d carpentries/workbench-docker:latest
```

In the Docker Desktop app, you should see an entry appear in the "Containers" tab with the name `carpentries-workbench`.

You can now open a web browser and navigate to `http://localhost:8787` which will connect to the RStudio server running in the Docker container.
You're good to go!
Please continue with the [Test Your Installation](local_install.md#install-test) instructions.

More information and docker runtime options are described in the [In-depth Docker guide](docker.md#in-depth) and [Workbench developer docker documentation](https://github.com/froggleston/workbench-dev/blob/frog-docker-update-1/docker.qmd).

Please note, if you are not comfortable with Docker or the Workbench, we recommend going through the [manual installation steps](local_install.md#101-manual) below.


## What's next?

### Not used the Workbench before?

Please follow the [Building your first Workbench lesson](episodes/01-first-lesson.md) to familiarise yourself with the lesson build process.

### What content can go in a lesson?

Please check the [Lesson Content and Styling](episodes/02-content-styling.md) and [Additional Lesson Content](03-additional-content.md) documentation.

### Using additional R packages?

Please familiarise yourself with our [Packages and renv](episodes/04-r-and-renv.md) information.

### Lesson in a non-English language?

Please read our [Internationalisation](episodes/05-il8n.md) guide.
