# The Carpentries Workbench Documentation

This lesson gives a high-level overview of how you can use The Carpentries Workbench to build beautiful and accessible lessons from markdown or RMarkdown sources.

## Setup the Workbench

To build this lesson locally, you should follow the [setup instructions for the Workbench](https://carpentries.github.io/workbench-docs/#101-local).

### Quick Installation
In short, make sure you have R, Git, and Pandoc installed, then open R and use the following commands to install/update the packages needed for the infrastructure:

```r
# register the repositories for The Carpentries and CRAN
options(repos = c(
  carpentries = "https://carpentries.r-universe.dev/",
  CRAN = "https://cran.rstudio.com/"
))

# Install the template packages to your R library
install.packages(c("sandpaper", "varnish", "pegboard", "tinkr"))
```

## Testing the Workbench Installation

### Download this lesson from GitHub

There are two ways to download this lesson from GitHub:

 - via the command line: 
   ```
   git clone https://github.com/carpentries/workbench-docs && cd workbench-docs
   ```
 - via R: 
   ```r
   usethis::create_from_github("https://github.com/carpentries/workbench-docs/")
   ```

### Build and Preview

Launch R in the `workbench-docs` folder and use this command to build and preview the lesson:

```r
library(sandpaper)
sandpaper::serve()
```

This should open a web browser with the rendered local version of this lesson, built using the Workbench!


[{sandpaper}]: https://carpentries.github.io/sandpaper/
