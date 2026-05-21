---
title: "Quickstart: Building a Lesson"
---

:::::::::::::::::::::::::::::::::::::: questions 

- How do we build lessons using a local Workbench installation?
- How do we build lessons using the online GitHub architecture?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Build a lesson site locally.
- Trigger lesson builds on a GitHub repository.

::::::::::::::::::::::::::::::::::::::::::::::::

## Local Lesson Builds
Build a lesson on your local system with [`sandpaper::build_lesson`](https://carpentries.github.io/sandpaper/reference/build_lesson.html) or [`sandpaper::serve`](https://carpentries.github.io/sandpaper/reference/serve.html):

```R
# while working in the root lesson folder:
sandpaper::build_lesson() # build a static site from the current version of the lesson repository
# or
sandpaper::serve() # serve a live preview of the lesson that refreshes when new changes are made
```

Similar to `create_lesson`, `build_lesson` produces a lot of output:

:::::::::::::::::::::: spoiler

### `build_lesson` output

```output
── Validating Fenced Divs ──────────────────────────────────────────────────────────────────────────────────────────────────────────
── Validating Internal Links and Images ────────────────────────────────────────────────────────────────────────────────────────────
ℹ Checking renv dependencies
ℹ Consent to use package cache provided
→ Searching for and installing available dependencies
Done!ng R package dependencies ... 
→ Restoring any dependency versions
- The library is already synchronized with the lockfile.
→ Recording changes in lockfile
- The lockfile is already up to date.
ℹ Using package cache in /Users/hodges/Library/Caches/org.R-project.R/R/renv
|

processing file: /Users/hodges/Documents/Miscellaneous/buoyant-barnacle/episodes/introduction.Rmd
1/3          
2/3 [pyramid]
3/3          
output file: /Users/hodges/Documents/Miscellaneous/buoyant-barnacle/site/built/introduction.md

◉ pandoc found
  version : 3.1.6
  path    : /usr/local/bin
── Initialising site ───────────────────────────────────────────────────────────────────────────────────────────────────────────────
Copying <pkgdown>/BS3/assets/bootstrap-toc.css to bootstrap-toc.css
Copying <pkgdown>/BS3/assets/bootstrap-toc.js to bootstrap-toc.js
Copying <pkgdown>/BS3/assets/docsearch.css to docsearch.css
Copying <pkgdown>/BS3/assets/docsearch.js to docsearch.js
Copying <pkgdown>/BS3/assets/link.svg to link.svg
Copying <pkgdown>/BS3/assets/pkgdown.css to pkgdown.css
Copying <pkgdown>/BS3/assets/pkgdown.js to pkgdown.js
Copying <varnish>/pkgdown/assets/android-chrome-192x192.png to android-chrome-192x192.png
Copying <varnish>/pkgdown/assets/android-chrome-512x512.png to android-chrome-512x512.png
Copying <varnish>/pkgdown/assets/apple-touch-icon.png to apple-touch-icon.png
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-Black.eot to assets/fonts/Mulish-Black.eot
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-Black.svg to assets/fonts/Mulish-Black.svg
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-Black.ttf to assets/fonts/Mulish-Black.ttf
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-Black.woff to assets/fonts/Mulish-Black.woff
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-Black.woff2 to assets/fonts/Mulish-Black.woff2
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-BlackItalic.eot to assets/fonts/Mulish-BlackItalic.eot
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-BlackItalic.svg to assets/fonts/Mulish-BlackItalic.svg
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-BlackItalic.ttf to assets/fonts/Mulish-BlackItalic.ttf
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-BlackItalic.woff to assets/fonts/Mulish-BlackItalic.woff
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-BlackItalic.woff2 to assets/fonts/Mulish-BlackItalic.woff2
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-Bold.eot to assets/fonts/Mulish-Bold.eot
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-Bold.svg to assets/fonts/Mulish-Bold.svg
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-Bold.ttf to assets/fonts/Mulish-Bold.ttf
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-Bold.woff to assets/fonts/Mulish-Bold.woff
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-Bold.woff2 to assets/fonts/Mulish-Bold.woff2
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-BoldItalic.eot to assets/fonts/Mulish-BoldItalic.eot
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-BoldItalic.svg to assets/fonts/Mulish-BoldItalic.svg
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-BoldItalic.ttf to assets/fonts/Mulish-BoldItalic.ttf
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-BoldItalic.woff to assets/fonts/Mulish-BoldItalic.woff
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-BoldItalic.woff2 to assets/fonts/Mulish-BoldItalic.woff2
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-ExtraBold.eot to assets/fonts/Mulish-ExtraBold.eot
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-ExtraBold.svg to assets/fonts/Mulish-ExtraBold.svg
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-ExtraBold.ttf to assets/fonts/Mulish-ExtraBold.ttf
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-ExtraBold.woff to assets/fonts/Mulish-ExtraBold.woff
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-ExtraBold.woff2 to assets/fonts/Mulish-ExtraBold.woff2
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-ExtraBoldItalic.eot to assets/fonts/Mulish-ExtraBoldItalic.eot
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-ExtraBoldItalic.svg to assets/fonts/Mulish-ExtraBoldItalic.svg
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-ExtraBoldItalic.ttf to assets/fonts/Mulish-ExtraBoldItalic.ttf
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-ExtraBoldItalic.woff to assets/fonts/Mulish-ExtraBoldItalic.woff
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-ExtraBoldItalic.woff2 to assets/fonts/Mulish-ExtraBoldItalic.woff2
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-ExtraLight.eot to assets/fonts/Mulish-ExtraLight.eot
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-ExtraLight.svg to assets/fonts/Mulish-ExtraLight.svg
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-ExtraLight.ttf to assets/fonts/Mulish-ExtraLight.ttf
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-ExtraLight.woff to assets/fonts/Mulish-ExtraLight.woff
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-ExtraLight.woff2 to assets/fonts/Mulish-ExtraLight.woff2
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-ExtraLightItalic.eot to assets/fonts/Mulish-ExtraLightItalic.eot
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-ExtraLightItalic.svg to assets/fonts/Mulish-ExtraLightItalic.svg
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-ExtraLightItalic.ttf to assets/fonts/Mulish-ExtraLightItalic.ttf
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-ExtraLightItalic.woff to assets/fonts/Mulish-ExtraLightItalic.woff
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-ExtraLightItalic.woff2 to assets/fonts/Mulish-ExtraLightItalic.woff2
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-Italic-VariableFont_wght.ttf to
assets/fonts/Mulish-Italic-VariableFont_wght.ttf
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-Italic.eot to assets/fonts/Mulish-Italic.eot
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-Italic.svg to assets/fonts/Mulish-Italic.svg
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-Italic.ttf to assets/fonts/Mulish-Italic.ttf
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-Italic.woff to assets/fonts/Mulish-Italic.woff
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-Italic.woff2 to assets/fonts/Mulish-Italic.woff2
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-Light.eot to assets/fonts/Mulish-Light.eot
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-Light.svg to assets/fonts/Mulish-Light.svg
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-Light.ttf to assets/fonts/Mulish-Light.ttf
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-Light.woff to assets/fonts/Mulish-Light.woff
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-Light.woff2 to assets/fonts/Mulish-Light.woff2
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-LightItalic.eot to assets/fonts/Mulish-LightItalic.eot
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-LightItalic.svg to assets/fonts/Mulish-LightItalic.svg
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-LightItalic.ttf to assets/fonts/Mulish-LightItalic.ttf
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-LightItalic.woff to assets/fonts/Mulish-LightItalic.woff
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-LightItalic.woff2 to assets/fonts/Mulish-LightItalic.woff2
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-Medium.eot to assets/fonts/Mulish-Medium.eot
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-Medium.svg to assets/fonts/Mulish-Medium.svg
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-Medium.ttf to assets/fonts/Mulish-Medium.ttf
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-Medium.woff to assets/fonts/Mulish-Medium.woff
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-Medium.woff2 to assets/fonts/Mulish-Medium.woff2
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-MediumItalic.eot to assets/fonts/Mulish-MediumItalic.eot
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-MediumItalic.svg to assets/fonts/Mulish-MediumItalic.svg
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-MediumItalic.ttf to assets/fonts/Mulish-MediumItalic.ttf
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-MediumItalic.woff to assets/fonts/Mulish-MediumItalic.woff
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-MediumItalic.woff2 to assets/fonts/Mulish-MediumItalic.woff2
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-Regular.eot to assets/fonts/Mulish-Regular.eot
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-Regular.svg to assets/fonts/Mulish-Regular.svg
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-Regular.ttf to assets/fonts/Mulish-Regular.ttf
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-Regular.woff to assets/fonts/Mulish-Regular.woff
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-Regular.woff2 to assets/fonts/Mulish-Regular.woff2
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-SemiBold.eot to assets/fonts/Mulish-SemiBold.eot
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-SemiBold.svg to assets/fonts/Mulish-SemiBold.svg
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-SemiBold.ttf to assets/fonts/Mulish-SemiBold.ttf
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-SemiBold.woff to assets/fonts/Mulish-SemiBold.woff
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-SemiBold.woff2 to assets/fonts/Mulish-SemiBold.woff2
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-SemiBoldItalic.eot to assets/fonts/Mulish-SemiBoldItalic.eot
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-SemiBoldItalic.svg to assets/fonts/Mulish-SemiBoldItalic.svg
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-SemiBoldItalic.ttf to assets/fonts/Mulish-SemiBoldItalic.ttf
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-SemiBoldItalic.woff to assets/fonts/Mulish-SemiBoldItalic.woff
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-SemiBoldItalic.woff2 to assets/fonts/Mulish-SemiBoldItalic.woff2
Copying <varnish>/pkgdown/assets/assets/fonts/Mulish-VariableFont_wght.ttf to assets/fonts/Mulish-VariableFont_wght.ttf
Copying <varnish>/pkgdown/assets/assets/fonts/MulishExtraLight-Regular.eot to assets/fonts/MulishExtraLight-Regular.eot
Copying <varnish>/pkgdown/assets/assets/fonts/MulishExtraLight-Regular.svg to assets/fonts/MulishExtraLight-Regular.svg
Copying <varnish>/pkgdown/assets/assets/fonts/MulishExtraLight-Regular.woff to assets/fonts/MulishExtraLight-Regular.woff
Copying <varnish>/pkgdown/assets/assets/fonts/MulishExtraLight-Regular.woff2 to assets/fonts/MulishExtraLight-Regular.woff2
Copying <varnish>/pkgdown/assets/assets/fonts/mulish-v5-latin-regular.eot to assets/fonts/mulish-v5-latin-regular.eot
Copying <varnish>/pkgdown/assets/assets/fonts/mulish-v5-latin-regular.svg to assets/fonts/mulish-v5-latin-regular.svg
Copying <varnish>/pkgdown/assets/assets/fonts/mulish-v5-latin-regular.ttf to assets/fonts/mulish-v5-latin-regular.ttf
Copying <varnish>/pkgdown/assets/assets/fonts/mulish-v5-latin-regular.woff to assets/fonts/mulish-v5-latin-regular.woff
Copying <varnish>/pkgdown/assets/assets/fonts/mulish-v5-latin-regular.woff2 to assets/fonts/mulish-v5-latin-regular.woff2
Copying <varnish>/pkgdown/assets/assets/fonts/mulish-variablefont_wght.woff to assets/fonts/mulish-variablefont_wght.woff
Copying <varnish>/pkgdown/assets/assets/fonts/mulish-variablefont_wght.woff2 to assets/fonts/mulish-variablefont_wght.woff2
Copying <varnish>/pkgdown/assets/assets/images/carpentries-logo-sm.svg to assets/images/carpentries-logo-sm.svg
Copying <varnish>/pkgdown/assets/assets/images/carpentries-logo.svg to assets/images/carpentries-logo.svg
Copying <varnish>/pkgdown/assets/assets/images/data-logo-sm.svg to assets/images/data-logo-sm.svg
Copying <varnish>/pkgdown/assets/assets/images/data-logo.svg to assets/images/data-logo.svg
Copying <varnish>/pkgdown/assets/assets/images/dropdown-arrow.svg to assets/images/dropdown-arrow.svg
Copying <varnish>/pkgdown/assets/assets/images/incubator-logo-sm.svg to assets/images/incubator-logo-sm.svg
Copying <varnish>/pkgdown/assets/assets/images/incubator-logo.svg to assets/images/incubator-logo.svg
Copying <varnish>/pkgdown/assets/assets/images/lab-logo-sm.svg to assets/images/lab-logo-sm.svg
Copying <varnish>/pkgdown/assets/assets/images/lab-logo.svg to assets/images/lab-logo.svg
Copying <varnish>/pkgdown/assets/assets/images/library-logo-sm.svg to assets/images/library-logo-sm.svg
Copying <varnish>/pkgdown/assets/assets/images/library-logo.svg to assets/images/library-logo.svg
Copying <varnish>/pkgdown/assets/assets/images/minus.svg to assets/images/minus.svg
Copying <varnish>/pkgdown/assets/assets/images/orcid_icon.png to assets/images/orcid_icon.png
Copying <varnish>/pkgdown/assets/assets/images/parrot_icon.svg to assets/images/parrot_icon.svg
Copying <varnish>/pkgdown/assets/assets/images/parrot_icon_colour.svg to assets/images/parrot_icon_colour.svg
Copying <varnish>/pkgdown/assets/assets/images/plus.svg to assets/images/plus.svg
Copying <varnish>/pkgdown/assets/assets/images/software-logo-sm.svg to assets/images/software-logo-sm.svg
Copying <varnish>/pkgdown/assets/assets/images/software-logo.svg to assets/images/software-logo.svg
Copying <varnish>/pkgdown/assets/assets/scripts.js to assets/scripts.js
Copying <varnish>/pkgdown/assets/assets/styles.css to assets/styles.css
Copying <varnish>/pkgdown/assets/assets/styles.css.map to assets/styles.css.map
Copying <varnish>/pkgdown/assets/assets/themetoggle.js to assets/themetoggle.js
Copying <varnish>/pkgdown/assets/favicon-16x16.png to favicon-16x16.png
Copying <varnish>/pkgdown/assets/favicon-32x32.png to favicon-32x32.png
Copying <varnish>/pkgdown/assets/favicons/cp/apple-touch-icon-114x114.png to favicons/cp/apple-touch-icon-114x114.png
Copying <varnish>/pkgdown/assets/favicons/cp/apple-touch-icon-120x120.png to favicons/cp/apple-touch-icon-120x120.png
Copying <varnish>/pkgdown/assets/favicons/cp/apple-touch-icon-144x144.png to favicons/cp/apple-touch-icon-144x144.png
Copying <varnish>/pkgdown/assets/favicons/cp/apple-touch-icon-152x152.png to favicons/cp/apple-touch-icon-152x152.png
Copying <varnish>/pkgdown/assets/favicons/cp/apple-touch-icon-57x57.png to favicons/cp/apple-touch-icon-57x57.png
Copying <varnish>/pkgdown/assets/favicons/cp/apple-touch-icon-60x60.png to favicons/cp/apple-touch-icon-60x60.png
Copying <varnish>/pkgdown/assets/favicons/cp/apple-touch-icon-72x72.png to favicons/cp/apple-touch-icon-72x72.png
Copying <varnish>/pkgdown/assets/favicons/cp/apple-touch-icon-76x76.png to favicons/cp/apple-touch-icon-76x76.png
Copying <varnish>/pkgdown/assets/favicons/cp/favicon-128.png to favicons/cp/favicon-128.png
Copying <varnish>/pkgdown/assets/favicons/cp/favicon-16x16.png to favicons/cp/favicon-16x16.png
Copying <varnish>/pkgdown/assets/favicons/cp/favicon-196x196.png to favicons/cp/favicon-196x196.png
Copying <varnish>/pkgdown/assets/favicons/cp/favicon-32x32.png to favicons/cp/favicon-32x32.png
Copying <varnish>/pkgdown/assets/favicons/cp/favicon-96x96.png to favicons/cp/favicon-96x96.png
Copying <varnish>/pkgdown/assets/favicons/cp/favicon.ico to favicons/cp/favicon.ico
Copying <varnish>/pkgdown/assets/favicons/cp/mstile-144x144.png to favicons/cp/mstile-144x144.png
Copying <varnish>/pkgdown/assets/favicons/cp/mstile-150x150.png to favicons/cp/mstile-150x150.png
Copying <varnish>/pkgdown/assets/favicons/cp/mstile-310x150.png to favicons/cp/mstile-310x150.png
Copying <varnish>/pkgdown/assets/favicons/cp/mstile-310x310.png to favicons/cp/mstile-310x310.png
Copying <varnish>/pkgdown/assets/favicons/cp/mstile-70x70.png to favicons/cp/mstile-70x70.png
Copying <varnish>/pkgdown/assets/favicons/dc/apple-touch-icon-114x114.png to favicons/dc/apple-touch-icon-114x114.png
Copying <varnish>/pkgdown/assets/favicons/dc/apple-touch-icon-120x120.png to favicons/dc/apple-touch-icon-120x120.png
Copying <varnish>/pkgdown/assets/favicons/dc/apple-touch-icon-144x144.png to favicons/dc/apple-touch-icon-144x144.png
Copying <varnish>/pkgdown/assets/favicons/dc/apple-touch-icon-152x152.png to favicons/dc/apple-touch-icon-152x152.png
Copying <varnish>/pkgdown/assets/favicons/dc/apple-touch-icon-57x57.png to favicons/dc/apple-touch-icon-57x57.png
Copying <varnish>/pkgdown/assets/favicons/dc/apple-touch-icon-60x60.png to favicons/dc/apple-touch-icon-60x60.png
Copying <varnish>/pkgdown/assets/favicons/dc/apple-touch-icon-72x72.png to favicons/dc/apple-touch-icon-72x72.png
Copying <varnish>/pkgdown/assets/favicons/dc/apple-touch-icon-76x76.png to favicons/dc/apple-touch-icon-76x76.png
Copying <varnish>/pkgdown/assets/favicons/dc/favicon-128.png to favicons/dc/favicon-128.png
Copying <varnish>/pkgdown/assets/favicons/dc/favicon-16x16.png to favicons/dc/favicon-16x16.png
Copying <varnish>/pkgdown/assets/favicons/dc/favicon-196x196.png to favicons/dc/favicon-196x196.png
Copying <varnish>/pkgdown/assets/favicons/dc/favicon-32x32.png to favicons/dc/favicon-32x32.png
Copying <varnish>/pkgdown/assets/favicons/dc/favicon-96x96.png to favicons/dc/favicon-96x96.png
Copying <varnish>/pkgdown/assets/favicons/dc/favicon.ico to favicons/dc/favicon.ico
Copying <varnish>/pkgdown/assets/favicons/dc/mstile-144x144.png to favicons/dc/mstile-144x144.png
Copying <varnish>/pkgdown/assets/favicons/dc/mstile-150x150.png to favicons/dc/mstile-150x150.png
Copying <varnish>/pkgdown/assets/favicons/dc/mstile-310x150.png to favicons/dc/mstile-310x150.png
Copying <varnish>/pkgdown/assets/favicons/dc/mstile-310x310.png to favicons/dc/mstile-310x310.png
Copying <varnish>/pkgdown/assets/favicons/dc/mstile-70x70.png to favicons/dc/mstile-70x70.png
Copying <varnish>/pkgdown/assets/favicons/lc/apple-touch-icon-114x114.png to favicons/lc/apple-touch-icon-114x114.png
Copying <varnish>/pkgdown/assets/favicons/lc/apple-touch-icon-120x120.png to favicons/lc/apple-touch-icon-120x120.png
Copying <varnish>/pkgdown/assets/favicons/lc/apple-touch-icon-144x144.png to favicons/lc/apple-touch-icon-144x144.png
Copying <varnish>/pkgdown/assets/favicons/lc/apple-touch-icon-152x152.png to favicons/lc/apple-touch-icon-152x152.png
Copying <varnish>/pkgdown/assets/favicons/lc/apple-touch-icon-57x57.png to favicons/lc/apple-touch-icon-57x57.png
Copying <varnish>/pkgdown/assets/favicons/lc/apple-touch-icon-60x60.png to favicons/lc/apple-touch-icon-60x60.png
Copying <varnish>/pkgdown/assets/favicons/lc/apple-touch-icon-72x72.png to favicons/lc/apple-touch-icon-72x72.png
Copying <varnish>/pkgdown/assets/favicons/lc/apple-touch-icon-76x76.png to favicons/lc/apple-touch-icon-76x76.png
Copying <varnish>/pkgdown/assets/favicons/lc/favicon-128.png to favicons/lc/favicon-128.png
Copying <varnish>/pkgdown/assets/favicons/lc/favicon-16x16.png to favicons/lc/favicon-16x16.png
Copying <varnish>/pkgdown/assets/favicons/lc/favicon-196x196.png to favicons/lc/favicon-196x196.png
Copying <varnish>/pkgdown/assets/favicons/lc/favicon-32x32.png to favicons/lc/favicon-32x32.png
Copying <varnish>/pkgdown/assets/favicons/lc/favicon-96x96.png to favicons/lc/favicon-96x96.png
Copying <varnish>/pkgdown/assets/favicons/lc/favicon.ico to favicons/lc/favicon.ico
Copying <varnish>/pkgdown/assets/favicons/lc/mstile-144x144.png to favicons/lc/mstile-144x144.png
Copying <varnish>/pkgdown/assets/favicons/lc/mstile-150x150.png to favicons/lc/mstile-150x150.png
Copying <varnish>/pkgdown/assets/favicons/lc/mstile-310x150.png to favicons/lc/mstile-310x150.png
Copying <varnish>/pkgdown/assets/favicons/lc/mstile-310x310.png to favicons/lc/mstile-310x310.png
Copying <varnish>/pkgdown/assets/favicons/lc/mstile-70x70.png to favicons/lc/mstile-70x70.png
Copying <varnish>/pkgdown/assets/favicons/swc/apple-touch-icon-114x114.png to favicons/swc/apple-touch-icon-114x114.png
Copying <varnish>/pkgdown/assets/favicons/swc/apple-touch-icon-120x120.png to favicons/swc/apple-touch-icon-120x120.png
Copying <varnish>/pkgdown/assets/favicons/swc/apple-touch-icon-144x144.png to favicons/swc/apple-touch-icon-144x144.png
Copying <varnish>/pkgdown/assets/favicons/swc/apple-touch-icon-152x152.png to favicons/swc/apple-touch-icon-152x152.png
Copying <varnish>/pkgdown/assets/favicons/swc/apple-touch-icon-57x57.png to favicons/swc/apple-touch-icon-57x57.png
Copying <varnish>/pkgdown/assets/favicons/swc/apple-touch-icon-60x60.png to favicons/swc/apple-touch-icon-60x60.png
Copying <varnish>/pkgdown/assets/favicons/swc/apple-touch-icon-72x72.png to favicons/swc/apple-touch-icon-72x72.png
Copying <varnish>/pkgdown/assets/favicons/swc/apple-touch-icon-76x76.png to favicons/swc/apple-touch-icon-76x76.png
Copying <varnish>/pkgdown/assets/favicons/swc/favicon-128.png to favicons/swc/favicon-128.png
Copying <varnish>/pkgdown/assets/favicons/swc/favicon-16x16.png to favicons/swc/favicon-16x16.png
Copying <varnish>/pkgdown/assets/favicons/swc/favicon-196x196.png to favicons/swc/favicon-196x196.png
Copying <varnish>/pkgdown/assets/favicons/swc/favicon-32x32.png to favicons/swc/favicon-32x32.png
Copying <varnish>/pkgdown/assets/favicons/swc/favicon-96x96.png to favicons/swc/favicon-96x96.png
Copying <varnish>/pkgdown/assets/favicons/swc/favicon.ico to favicons/swc/favicon.ico
Copying <varnish>/pkgdown/assets/favicons/swc/mstile-144x144.png to favicons/swc/mstile-144x144.png
Copying <varnish>/pkgdown/assets/favicons/swc/mstile-150x150.png to favicons/swc/mstile-150x150.png
Copying <varnish>/pkgdown/assets/favicons/swc/mstile-310x150.png to favicons/swc/mstile-310x150.png
Copying <varnish>/pkgdown/assets/favicons/swc/mstile-310x310.png to favicons/swc/mstile-310x310.png
Copying <varnish>/pkgdown/assets/favicons/swc/mstile-70x70.png to favicons/swc/mstile-70x70.png
Copying <varnish>/pkgdown/assets/mstile-150x150.png to mstile-150x150.png
Copying <varnish>/pkgdown/assets/safari-pinned-tab.svg to safari-pinned-tab.svg
Copying <varnish>/pkgdown/assets/site.webmanifest to site.webmanifest
── Scanning episodes to rebuild ────────────────────────────────────────────────────────────────────────────────────────────────────
── Creating citation page ──────────────────────────────────────────────────────────────────────────────────────────────────────────
══ Validating cff ══════════════════════════════════════════════════════════════════════════════════════════════════════════════════
✔ Congratulations! /Users/hodges/Documents/Miscellaneous/buoyant-barnacle/CITATION.cff is valid
Writing `instructor/citation.html`
Writing `citation.html`
Writing `instructor/CODE_OF_CONDUCT.html`
Writing `CODE_OF_CONDUCT.html`
Writing `instructor/LICENSE.html`
Writing `LICENSE.html`
Writing `instructor/introduction.html`
Writing `introduction.html`
Writing `instructor/reference.html`
Writing `reference.html`
── Creating 404 page ───────────────────────────────────────────────────────────────────────────────────────────────────────────────
Writing `instructor/404.html`
Writing `404.html`
── Creating learner profiles ───────────────────────────────────────────────────────────────────────────────────────────────────────
Writing `instructor/profiles.html`
Writing `profiles.html`
── Creating homepage ───────────────────────────────────────────────────────────────────────────────────────────────────────────────
Writing `instructor/index.html`
Writing `index.html`
── Creating keypoints summary ──────────────────────────────────────────────────────────────────────────────────────────────────────
Writing 'instructor/key-points.html'
Writing 'key-points.html'
── Creating All-in-one page ────────────────────────────────────────────────────────────────────────────────────────────────────────
Writing 'instructor/aio.html'
Writing 'aio.html'
── Creating Images page ────────────────────────────────────────────────────────────────────────────────────────────────────────────
Writing 'instructor/images.html'
Writing 'images.html'
── Creating Instructor Notes ───────────────────────────────────────────────────────────────────────────────────────────────────────
Writing 'instructor/instructor-notes.html'
Writing 'instructor-notes.html'
── Creating sitemap.xml ────────────────────────────────────────────────────────────────────────────────────────────────────────────
ℹ Previewing site

Output created: /Users/hodges/Documents/Miscellaneous/buoyant-barnacle/site/docs/index.html
```

::::::::::::::::::::::::::::::

As before, let's break this output down by section.

### Validation

```output
── Validating Fenced Divs ──────────────────────────────────────────────────────────────────────────────────────────────────────────
── Validating Internal Links and Images ────────────────────────────────────────────────────────────────────────────────────────────
```

Before building the site, the Workbench performs some validation to ensure that lesson content is correctly formatted and accessible.
If the validation checks identify any problems, they will be reported with warnings in this section of the build output.

This is discussed further in [_Lesson Validation Checks_](FIXME).

### Package cache
The first time `build_lesson` is run on a lesson using R Markdown source files, you will be prompted to authorise the use of the R package cache to track your lesson dependencies.

```output
FIXME
```

It is good practice to keep your lesson dependencies separate from system R packages.
Choose option 1 to allow this.
Management of lesson dependencies is discussed further in [_Using the Package Cache_](FIXME).

### R Markdown execution
Output for lessons using R Markdown source files will include logging of the execution of those files and their conversion to standard Markdown.

```output
processing file: /home/captainhaddock/buoyant-barnacle/episodes/introduction.Rmd
1/3          
2/3 [pyramid]
3/3          
output file: /home/captainhaddock/buoyant-barnacle/site/built/introduction.md
```

This is discussed further in [_R Markdown Execution_](FIXME).

### Pandoc information
Details of the version of Pandoc used in the build.
This information can be useful when debugging.

```output
◉ pandoc found
  version : 3.1.6
  path    : /usr/local/bin
```

### Initialising site
A short message confirming that the build has entered the initial setup phase.

```output
── Initialising site ───────────────────────────────────────────────────────────────────────────────────────────────────────────────
```

### Asset acquisition
A long list of files (mostly fonts and images) copied from the template to use in the new lesson.

```output
Copying <pkgdown>/BS3/assets/bootstrap-toc.css to bootstrap-toc.css
Copying <pkgdown>/BS3/assets/bootstrap-toc.js to bootstrap-toc.js
Copying <pkgdown>/BS3/assets/docsearch.css to docsearch.css
Copying <pkgdown>/BS3/assets/docsearch.js to docsearch.js
Copying <pkgdown>/BS3/assets/link.svg to link.svg
[...]
Copying <varnish>/pkgdown/assets/favicons/swc/mstile-310x310.png to favicons/swc/mstile-310x310.png
Copying <varnish>/pkgdown/assets/favicons/swc/mstile-70x70.png to favicons/swc/mstile-70x70.png
Copying <varnish>/pkgdown/assets/mstile-150x150.png to mstile-150x150.png
Copying <varnish>/pkgdown/assets/safari-pinned-tab.svg to safari-pinned-tab.svg
Copying <varnish>/pkgdown/assets/site.webmanifest to site.webmanifest
```

### Determining what needs to be built
The Workbench only (re)builds source files that have changed since the last build.
At this stage, it searches for these files that have been modified since last time, to prepare the rest of the process.

```output
── Scanning episodes to rebuild ────────────────────────────────────────────────────────────────────────────────────────────────────
```

### Building a citation page
The lesson's `CITATION.cff` file (a placeholder in any new lesson) is validated and built into a citation page.

```output
── Creating citation page ──────────────────────────────────────────────────────────────────────────────────────────────────────────
══ Validating cff ══════════════════════════════════════════════════════════════════════════════════════════════════════════════════
✔ Congratulations! /Users/hodges/Documents/Miscellaneous/buoyant-barnacle/CITATION.cff is valid
```

Lesson citation pages and `CITATION.cff` are discussed further in [_Making Your Lesson Citable_](FIXME).

### Building the lesson pages
The other pages of the lesson site are built.

```output
Writing `instructor/citation.html`
Writing `citation.html`
Writing `instructor/CODE_OF_CONDUCT.html`
Writing `CODE_OF_CONDUCT.html`
Writing `instructor/LICENSE.html`
Writing `LICENSE.html`
Writing `instructor/introduction.html`
Writing `introduction.html`
Writing `instructor/reference.html`
Writing `reference.html`
── Creating 404 page ───────────────────────────────────────────────────────────────────────────────────────────────────────────────
Writing `instructor/404.html`
Writing `404.html`
── Creating learner profiles ───────────────────────────────────────────────────────────────────────────────────────────────────────
Writing `instructor/profiles.html`
Writing `profiles.html`
── Creating homepage ───────────────────────────────────────────────────────────────────────────────────────────────────────────────
Writing `instructor/index.html`
Writing `index.html`
── Creating keypoints summary ──────────────────────────────────────────────────────────────────────────────────────────────────────
Writing 'instructor/key-points.html'
Writing 'key-points.html'
── Creating All-in-one page ────────────────────────────────────────────────────────────────────────────────────────────────────────
Writing 'instructor/aio.html'
Writing 'aio.html'
── Creating Images page ────────────────────────────────────────────────────────────────────────────────────────────────────────────
Writing 'instructor/images.html'
Writing 'images.html'
── Creating Instructor Notes ───────────────────────────────────────────────────────────────────────────────────────────────────────
Writing 'instructor/instructor-notes.html'
Writing 'instructor-notes.html'
── Creating sitemap.xml ────────────────────────────────────────────────────────────────────────────────────────────────────────────
```

Refer to [_Lesson Page Directory_](learners/page-directory.md) for a description of each of these pages.

### Preview output
Finally, the path is provided to the front page of the built lesson site.

```output
ℹ Previewing site

Output created: /home/captainhaddock/buoyant-barnacle/site/docs/index.html
```

Now that we know the lesson builds successfully, we are ready to begin adding content.

## GitHub Lesson Builds
The lesson build and publication process is automated in GitHub repositories via the _01 Maintain: Build and Deploy_ [GitHub Actions](https://docs.github.com/en/actions/get-started/understand-github-actions) workflow.
Any new commit to the `main` branch of the GitHub repository will trigger this workflow, building the latest version of the lesson and commiting the new built pages to the `gh-pages` branch.

### Configure GitHub Pages

:::::::::::::::::::::::::::::::::::::::::::::::: callout

#### Is Pages already configured?
If you selected _"Copy all branches"_ when you [created your lesson from one of the template repositories](../episodes/01-quick-create.md), GitHub Pages will already be activated on your repository.
You can confirm this by visiting _Settings_ -> _Code and automation_ -> _Pages_ in the repository settings.

::::::::::::::::::::::::::::::::::::::::::::::::::::::::

The first time you push the contents of your lesson project to the `main` branch of your remote repository on GitHub, the _01 Maintain: Build and Deploy_ workflow will be triggered.
After this workflow has completed (check its status in [the _Actions_ tab](https://docs.github.com/en/actions/how-tos/monitor-workflows/view-workflow-run-history) of your repository), you can [activate GitHub Pages](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site#publishing-from-a-branch) to serve your lesson website from the root folder of the `gh-pages` branch.

![The recommended GitHub Pages configuration for a lesson repository](
  fig/github-pages-config.png
){
  alt="The recommended GitHub Pages configuration for a Carpentries Workbench lesson repository"
}

The build and deployment workflow is discussed further in [_Lesson Maintenance Workflows_](FIXME).

You can now begin editing your lesson. 

:::::::::::::::::::::::::::::::::::::: keypoints 

- `sandpaper`'s `build_lesson` and `serve` functions are used to build a local version of the lesson website.
- The _01 Maintain: Build and Deploy_ workflow builds the lesson with GitHub Actions, serving it to the internet with GitHub Pages.

::::::::::::::::::::::::::::::::::::::::::::::::
