---
title: 'Workbench FAQs'
---

## Installation FAQ

### Is the Workbench open source?

Yes! All the Workbench dependencies are open source.

If you are choosing to use Docker or devcontainers, we acknowledge that some of these tools including the VSCode IDE, are not completely open source.
You do not need to use these technologies to use the Workbench if you choose not to - the manual local installation of the Workbench will work in the exact same way.

### Why does it take 5 lines of code to install the infrastructure locally?

As the Workbench packages are in The Carpentries R-Universe and not CRAN, we need to tell R to get the packages from R-Universe.

### What is an R Library?

An R library is a folder on your computer that stores R packages.
When you install R packages, the first message you will see will probably be something like (on Windows):

```
Installing packages into ‘C:/Users/USER/Documents/R/win-library/4.0’
(as ‘lib’ is unspecified)
```

On Ubuntu, this may look like:

```
Installing packages into ‘/home/<user>/R/x86_64-pc-linux-gnu-library/4.4’
```

This folder is where all of the R packages you install via `install.packages()` will live.
If you ever need to look this up, you can use the `.libPaths()` function.

### Using a personal library

Sometimes, your R session will issue a warning that says a folder is not writeable and asks if you would like to use a personal library instead.
In this case, select "yes".

## Opening your R environment

### RStudio

If you are using RStudio, you can open it by:

- going to the RStudio Server URL provided when you run the Docker or devcontainer environment
- or, double-clicking on the RStudio icon in your application launcher

You do not have to open R separately to use RStudio.

### R

If you are using R, you can open it in your terminal application by typing `R`.
Your prompt will be replaced by a `>`, which indicates that you are in R's interactive [REPL](https://glosario.carpentries.org/en/#repl).

You can exit R or RStudio by typing `q()` in the R console.

::::::::: prereq

### Setting up your R workspace

When you set up R, it's important to make sure you set it up to always start R with a clean slate[^workspace]: never save your workspace on exit and never load a previously saved workspace on startup.

#### Via RStudio 

If you are using RStudio, you can [follow the instructions in this forum post](https://forum.posit.co/t/first-line-of-every-r-script/799/12?u=zkamvar):

1. From the menu, select <cmd>Tools<cmd> > <cmd>Global Options</cmd>
2. Under **Workspace Options**, de-select "Restore .RData into workspace at startup" and set "Save workspace to .RData on exit" to "Never"

#### Via Command Line Interface

The flags `--no-restore` and `--no-save` will set these defaults, so you can create an alias for R in the `.bashrc` file in your home directory:

```bash
alias R='R --no-restore --no-save'
```

::::::::::::::::::