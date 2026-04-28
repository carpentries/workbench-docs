---
site: sandpaper::sandpaper_site
---


Welcome to the documentation for The Carpentries Workbench.

The Workbench is a suite of tools that takes lesson material content written in simple text, and builds a neat and consistent static website.

It is built on Git, the R language, and pandoc, and consists of four components:

1. The source content, i.e. the "lesson" (plain markdown or RMarkdown files organized into folders with a configuration yaml file)
2. The engine (R package [{sandpaper}]) to process the lesson content markdown to HTML
3. The validator (R package [{pegboard}]) to parse the source markdown files and highlight common errors
4. The renderer (R package [{varnish}]) to generate the final HTML, CSS, and JavaScript styling elements for the lesson website

Details of how these tools work together are explained in the [Workbench Internals](internals.md) documentation.
In short, you can interact with the lesson source content and the Workbench tools to author and preview your lesson.

Working examples of Workbench-powered lessons can be found as part of our Carpentries curriculum:

  - This documentation!
  - [The Unix Shell](http://swcarpentry.github.io/shell-novice/)
  - [Data Analysis and Visualization with R for Genomics](https://datacarpentry.org/genomics-r-intro/)
  - [Image Processing with Python](https://datacarpentry.org/image-processing)
  - [Introduction to Git for Librarians](https://librarycarpentry.org/lc-git/)


:::::::::::::::::: checklist

## Features of the The Carpentries Workbench

- [x] Automatic updates
- [x] Pandoc markdown syntax
- [x] Built entirely using R
- [x] Automatic rendering of code in R Markdown
- [x] Non-invasive package management with {renv}
- [x] Pull Request audits for rendered files
- [x] Compatible with RStudio
- [x] Containerised using Docker for reproducibility

::::::::::::::::::::::::::::

To get started using the Workbench, continue reading [below](learners/setup.md)!
