---
title: 'Starting a New Lesson'
teaching: 30
exercises: 0
---

:::::::::::::::::::::::::::::::::::::: questions 

- How do I create and configure a new Workbench lesson?
- Which lesson template should I use?
- What do the files and folders in a Workbench lesson repository do?
- How do I add new pages to a lesson?
- What special formatted blocks can I include in my lesson?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

After following this part of the documentation, Workbench users will be able to...

- Create and configure a new Workbench lesson.
- Choose between the Markdown and R Markdown templates for a new lesson.
- Navigate the folder structure of a Workbench lesson repository.
- Add episodes to a lesson.
- Implement fenced divs of styled content in a lesson.

::::::::::::::::::::::::::::::::::::::::::::::::


::::::::::::::::::::::::::::::::::::: keypoints 

- A new Workbench lesson can be created with `sandpaper::create_lesson` or by copying one of the templates on GitHub.
- Global settings for a lesson are configured in `config.yaml`
- The R Markdown template is recommended for lessons that will include R code blocks.
- A Workbench lesson is built from source files in the root and `episodes`, `learners`, `instructors` and `profiles` folders of the repository.
- A new episode can be added to a lesson with `sandpaper::create_episode` or by adding a new file to the `episodes` folder then listing it in `config.yaml`.
- The Workbench provides a range of styled blocks, called fenced divs, to include in lessons.

::::::::::::::::::::::::::::::::::::::::::::::::

