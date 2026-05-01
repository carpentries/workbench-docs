---
title: '101 Quick Start: Setting up your Workbench environment'
---

## Installation of the Workbench {#101-install}

We provide four mechanisms to interact with the Workbench:

- [Devcontainers](devcontainer.md) (online or local) **[recommended]**
  - We recommend using devcontainers as everything will be installed for you whether you are using an online or local environment, with minimal setup.
  - Lessons with devcontainer support will have a `.devcontainer` folder in the root of the repository.
  - **If no devcontainer is available for the lesson you wish to work on, please use the manual installation route, or Docker if you are comfortable with it.**
- [Docker](docker.md) (local)
  - The Docker option can be useful for those that already have experience with Docker and containers, and are happy to do some manual configuration or wish to have more flexibility.
  - **Initial setup with docker is very straightfoward but can get complicated depending on your operating system!**
- [Manual local installation from conda-forge with Pixi](local_install.md#101-conda-pixi) (local)
   - Installing all the requirements for development is one line and will create a fully reproducible environment.
  - **Initial setup with conda packages from conda-forge and Pixi is very straightfoward and is operating system agnostic.**
- [Manual local installation with operating system specific tools](local_install.md#101-conda-conda) (local)
  - Installing all the requirements manually on your local operating system is a longer process, but can be useful if you want to learn how to get an environment set up and will teach you more about the Workbench framework.
  - **If Docker and devcontainers are not suitable for you, installing things manually is a great option and still relatively quick to do!**
- [GitHub](github.md) (online)
  - Moving your development completely online by using GitHub's Codespaces or Dev environment is an excellent choice if you have a reliable internet connection and are comfortable with this process.
  - **Be advised that this option may incur a cost depending on your GitHub account status!**

::::::::::::::::::::: callout

### Why would I want to install locally if all these other options exist?

You can use the Workbench completely within devcontainers, Docker, or with [Pixi locally](local_install.md#101-conda-forge), or through GitHub using our templates.

However, we still would recommend working through the [local setup instructions](local_install.md#101-manual) at least once as they can save you a lot of time during lesson development and debugging in future.

:::::::::::::::::::::::::::::

Once your installation is complete with one of the mechanisms above, make sure to test your installation using the instructions below.


## Test your Workbench installation {#install-test}

To test your installation **open RStudio** either as the locally installed app or in the browser if using Docker (or launch R if you have not installed RStudio and are not using Docker/devcontainers) and enter the following commands to confirm everything works:

```r
rmarkdown::pandoc_version()
tmp <- tempfile()
sandpaper::no_package_cache()
sandpaper::create_lesson(tmp, open = FALSE)
sandpaper::build_lesson(tmp, preview = FALSE, quiet = TRUE)
fs::dir_tree(tmp, recurse = 1)
```

```output
[1] '3.9'
ℹ Consent for package cache revoked. Use `use_package_cache()` to undo.
→ Creating Lesson in '/tmp/RtmpnRjHyr/file12f34734be05f'...
✔ First episode created in '/tmp/RtmpnRjHyr/file12f34734be05f/episodes/01-introduction.Rmd'
ℹ Workflows up-to-date!
✔ Lesson successfully created in '/tmp/RtmpnRjHyr/file12f34734be05f'
/tmp/RtmpnRjHyr/file12f34734be05f
├── CODE_OF_CONDUCT.md
├── CONTRIBUTING.md
├── LICENSE.md
├── README.md
├── config.yaml
├── episodes
│   ├── 01-introduction.Rmd
│   ├── data
│   ├── fig
│   └── files
├── index.md
├── instructors
│   └── instructor-notes.md
├── learners
│   └── setup.md
├── profiles
│   └── learner-profiles.md
└── site
    ├── DESCRIPTION
    ├── README.md
    ├── _pkgdown.yaml
    ├── built
    └── docs
```

If the installation did not work, please [raise an issue on GitHub](https://github.com/carpentries/workbench/issues/new). 

## Connect to GitHub

To share your lessons with others, and to use our provided automated build and publishing workflows, you will need to use GitHub.

### Setting up Git

You will need to make sure your git session is connected to GitHub.
If you already push and pull from GitHub using the command line, you do not need to worry about setting this up as you will have done so already.

If you haven't used git or GitHub before, we recommend working through our Software Carpentry [Git lesson](https://swcarpentry.github.io/git-novice/) first.

To do so, you will need to use an SSH or HTTPS protocol.
It’s recommended to use the SSH protocol, unless you explicitly cannot, e.g. behind an institutional firewall or proxy.
If you do not have this set up, you should [choose a protocol](https://docs.github.com/en/github/getting-started-with-github/about-remote-repositories) and then set them up according to the instructions from GitHub.


:::::::::::::::: callout

### Docker/devcontainers and git

If you already have your git installation configured outside the Docker/devcontainer environment, the various scripts and commands used in this documentation include mapping your local SSH (and GPG signing) configuration into the container.
This means your git commands should "just work" inside the container as they would outside.

If you have any issues, please open an issue on the [workbench-docker](https://github.com/carpentries/workbench-docker/issues) GitHub repo and/or ask for help on the `workbench` channel in [The Carpentries Slack workspace](https://carpentries.org/community/get-involved/).

::::::::::::::::::::::::

:::::::::::::::: callout

### Is GitHub's Documentation Confusing?

You may find GitHub's documentation slightly confusing and/or lacking.
The following resources are extremely helpful for setting up authentication credentials for your account:

[Remotes in GitHub (Software Carpentry)](https://swcarpentry.github.io/git-novice/07-github)
: A walkthrough of creating a repository on GitHub and pushing to it via the command line.

[Connect to GitHub (Happy Git With R)](https://happygitwithr.com/push-pull-github.html)
: A walkthrough of creating a throwaway repository that gives you a good idea for the mechanics of working with GitHub.

[Cache credentials for HTTPS (Happy Git With R)](https://happygitwithr.com/credential-caching.html)
: Clear explanation on how to set up a Personal Access Token and the benefits of using HTTPS. This explains how to do this in both the shell and R.

[Set up keys for SSH (Happy Git With R)](https://happygitwithr.com/ssh-keys.html)
: Clear explanation on what SSH key pairs are and how to set up and connect them with GitHub. This has recommendations using both the shell and RStudio.

::::::::::::::::::::::::
