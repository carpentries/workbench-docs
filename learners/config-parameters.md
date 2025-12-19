---
title: 'Global Lesson Parameters'
---

The `config.yaml` file contains global settings for the lesson as a whole.

analytics
: (Optional) Configuration for web analytics, e.g. with [Matomo](https://matomo.org/) or Google Analytics. There are currently three options for `analytics`:

1. `NULL`: disables tracking for that lesson. This is the default behviour, and is equivalent to omitting the `analytics` field from `config.yaml` altogether.
2. `carpentries`: adds the tracking script needed for the lesson to be tracked by The Carpentries self-hosted Matomo system. 
    This option works only for lessons belonging to The Carpentries.
3. `<user_string>`: allows the user to define their own tracker script string. 
   For legibility, use the `|` symbol to indicate that the value of the YAML field will be split across multiple indented lines ([known as a 'literal block' in YAML](https://stackoverflow.com/a/21699210)). 
   For example, to configure for Google Analytics:

    ```yaml
    analytics: |
    <!-- Global site tag (gtag.js) - Google Analytics -->
    <script async src='https://www.googletagmanager.com/gtag/js?id={YOUR TRACKING ID}#' ></script>
    <script>
        window.dataLayer = window.dataLayer || [];
        function gtag(){dataLayer.push(arguments);}
        gtag('js', new Date());

        gtag('config', '{YOUR TRACKING ID}');
    </script>
    ```

Tracking scripts configured with the `analytics` option are added to the footer element of the lesson website HTML.

branch
: The default branch of the lesson (typically `main`). 

carpentry
: The code for the specific carpentry that the lesson belongs to. The Carpentries supports the following values: 

* `cp`: The Carpentries branding, for lessons belonging to The Carpentries, e.g. [Instructor Training](https://carpentries.github.io/instructor-training/).
* `dc`: Data Carpentry branding, for lessons belonging to Data Carpentry, e.g. [Image Processing with Python](https://datacarpentry.github.io/image-processing/).
* `incubator`: The Carpentries Incubator branding, for lessons belonging to their developers, whether or not the lesson is in [the Incubator](https://carpentries-incubator.org/). _(Default for new lessons)_
* `lab`: The Carpentries Lab branding, for lessons belonging to their developers, which have passed peer review and been accepted to [The Carpentries Lab](https://carpentries-lab.org/).
* `lc`: Library Carpentry branding, for Library Carpentry lessons, e.g. [Introducing Computational Thinking](https://librarycarpentry.github.io/lc-computational-thinking/). 
* `swc`: Software Carpentry branding, for Software Carpentry lessons, e.g. [Plotting and Programming with Python](https://swcarpentry.github.io/python-novice-gapminder/).

Refer to [Custom Lesson Branding](FIXME) for information about how to use a custom logo/styling for your lesson.

carpentry_description
: (Optional) Full organisation name. Not needed when `carpentry` is `cp`, `dc`, `incubator`, `lab`, `lc`, or `swc`.  Refer to [Custom Lesson Branding](FIXME) for information about how to use a custom logo/styling for your lesson.

contact
: An email address that can be used to contact the developer(s) of the lesson.

disable_sidebar_numbering
: (Optional) A Boolean setting to disable the display of numbers next to each episode title in the sidebar navigation. Add `disable_sidebar_numbering: true` to `config.yaml` to remove the numbering. 

episodes
: A list of the names of the episode source files, in their desired order.

instructors
: A list of the names of source files for pages to support instructors teaching the lesson.

lang
: [ISO 639 two letter code](https://en.wikipedia.org/wiki/List_of_ISO_639_language_codes#Table) for the language used for headers, callouts and other Workbench elements. Defaults to `en` for English. Refer to [Internationalisation in The Carpentries Community](FIXME) for more information about how our community is translating and localising lessons together.

languages
: If the lesson is available in more than one language you can use this setting to provide a drop-down menu to navigate between languages. This option can also be used to link between different flavors of the same material (e.g. Python vs R, GitHub vs GitLab). Refer to [Internationalisation in The Carpentries Community](FIXME) for more information about how our community is translating and localising lessons together.

`languages` is configured with the following fields:
 * `default`: the label attached to this version of the lesson in the dropdown. (Defined once.)
 * `other`: an array of pairs of `lang` and `url` fields, each defining a label to display in the dropdown and the URL to link to respectively.

```yaml
lang: en

languages:
  default: English
  other:
    - lang: "Español"
      url: https://example.org/shell-novice-es/
    - lang: Deutsch
      url: https://example.org/shell-novice-de/
    - lang: Italiano
      url: https://example.org/shell-novice-it/
```

learners
: A list of the names of source files for additional pages to provide to learners following the lesson, e.g. a list of recommended further reading, etc.

life_cycle
: What phase of [the lesson life cycle](https://docs.carpentries.org/resources/curriculum/lesson-life-cycle.html) is the lesson in? Possible values are `pre-alpha`, `alpha`, `beta`, and `stable`. Adjusting this setting changes a badge displayed in the banner at the top of the lesson site, designed to give visitors an impression of the maturity of the lesson. No badge is displayed when `life_cycle` is `stable`.

license
: The license the lesson is published under. Defaults to CC-BY 4.0, to match the license of the lesson template. To adopt a different license, change the `license` variable to the name of your desired license and replace the contents of `LICENSE.md` with the text of your license *or* add the `license_url` variable, set to the URL for your license.

license_url
: The URL of a page containing the text of your chosen license. This parameter is excluded from the template `config.yaml` and must be added by lesson developers who need it.

profiles
: A list of the names of source files for pages describing learner profiles for the lesson.

source
: The URL of the source repository for the lesson, e.g. a GitHub repository.

title
: The main title of the lesson.

url
: The URL of the lesson site homepage.
