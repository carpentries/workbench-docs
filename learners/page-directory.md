---
title: Lesson Page Directory
---

The Carpentries Workbench builds a lesson website with a fixed set of default pages.
Most pages exist in two versions: a **Learner View** (the default) and an **Instructor View** (under the `/instructor/` URL path).
The Instructor View shows additional content such as instructor notes and a timing schedule.

## Learner View Pages

Home (`index.html`)
: The lesson homepage, built by combining `index.md` and `learners/setup.md`. Contains the lesson summary and setup instructions (data downloads, software installation, etc), and serves as the entry point for learners.

Episode (`<episode-slug>.html`)
: One page per episode, rendered from the source files listed in the `episodes` field of `config.yaml`. Each episode page displays the questions, learning objectives, lesson content, and key points for that episode.

Key Points (`key-points.html`)
: An aggregation of the key points from every episode. This page has no source file of its own.

Reference (`reference.html`)
: A reference page for learners, built from `learners/reference.md`. Intended to hold a glossary, links to literature references or futher reading, and any other supplementary reference material that may be useful to learners.

Learner Profiles (`profiles.html`)
: Descriptions of the intended audience for the lesson, built from files listed the `profiles` filed of `config.yaml`. Helps prospective learners decide whether the lesson is appropriate for them.

All-in-One (`aio.html`)
: An aggregation of the content from every episode. This can be useful for searching across the whole lesson or for printing. This page has no source file of its own.

Acknowledgements and Citations (`citation.html`)
: Built from the information in `CITATION.cff`. Provides citation information for the lesson and links to citation guidance for the Workbench itself. Linked from the page footer.

License (`LICENSE.html`)
: A rendered version of the license for the lesson, built from `LICENSE.md`. Linked from the page footer.

Code of Conduct (`CODE_OF_CONDUCT.html`)
: A rendered version of the code of conduct for the lesson project, built from `CODE_OF_CONDUCT.md`. Linked from the page footer.

## Instructor View Pages
All Learner View pages also have an Instructor View equivalent at the same path, with the filename prefixed with `instructor/`.
The pages listed below are exclusive to the Instructor View, or have significant differences to their equivalent in the Learner View.

Instructor Notes (`instructor/instructor-notes.html`)
: Guidance for instructors teaching the lesson, built by combining the content of `instructors/instructor-notes.md` with an aggregation of all the inline instructor notes from every episode. Exclusive to the Instructor View.

Extract All Images (`instructor/images.html`)
: An aggregation of every image used across all episodes displayed on a single page, with captions and alternative text descriptions. Useful for checking figures before teaching, sharing during a workshop, and/or for preparing slide materials. Exclusive to the Instructor View.

Home (`instructor/index.html`)
: In the Instructor View, the lesson homepage includes a schedule table -- showing each episode, its guiding question(s), and estimated duration -- between the content of `index.md` and `learners/setup.md`.

Episode (`instructor/<episode-slug>.html`)
: The instructor version of each episode page. Identical to the learner version but with instructor note callouts visible inline, which are hidden in the Learner View.
