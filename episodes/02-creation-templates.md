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

## Configuring a new lesson
Global parameters of the lesson -- the lesson title, contact information, etc -- are configured in `config.yaml`.
The following settings are likely to be most relevant when starting a new lesson: 

* `title`: the title of your lesson.
* `created`: the date that your lesson was created, in YYYY-MM-DD format.
* `keywords`: a comma-separated list of keywords for your lesson. 
  These keywords will be embedded in the HTML of your lesson website, for use in search engine indexing, etc.
* `life_cycle`: the stage of the [lesson life cycle](https://docs.carpentries.org/resources/curriculum/lesson-life-cycle.html) that your lesson has reached. 
  The default, `pre-alpha` is most appropriate for a brand new lesson.
* `source`: the URL of your lesson's source repository.
* `contact`: a contact email address for the lesson.

All of the fields listed above are marked with `FIXME` in the `config.yaml` of a newly-created lesson.
Review [the complete list of parameters that can be set in `config.yaml`](../learners/config-parameters.md) for more details about the settings available for a lesson.

::::::::::::::::::::::::::::::::::::: keypoints 

- A new Workbench lesson can be created with `sandpaper::create_lesson` or by copying one of the templates on GitHub.
- Global settings for a lesson are configured in `config.yaml`
- The R Markdown template is recommended for lessons that will include R code blocks.
- A Workbench lesson is built from source files in the root and `episodes`, `learners`, `instructors` and `profiles` folders of the repository.
- A new episode can be added to a lesson with `sandpaper::create_episode` or by adding a new file to the `episodes` folder then listing it in `config.yaml`.
- The Workbench provides a range of styled blocks, called fenced divs, to include in lessons.

::::::::::::::::::::::::::::::::::::::::::::::::

