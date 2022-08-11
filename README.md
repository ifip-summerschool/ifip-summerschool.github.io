# ifip-summerschool.github.io

Website for IFIP Summerschool provided via Github Pages (reachable under: 
https://ifip-summerschool.github.io).
Using the Template [Minimal Mistakes](https://github.com/mmistakes/minimal-mistakes) providing well documented [Quick Start Guide](https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/).

## Directory Layout
```terminal
├── assets
│   ├── css
│   │   └── main.scss           --> contains styling (e.g. headline colors)
│   ├── images                  --> contains images (like Landing)
│   │   ├── ...
│   │   ├── keynotes            --> subfolder for speaker images
│   │   │   ├── ...
│   │   └── logos               --> subfolder for logos
│   │       ├── ...
│   └── programme.pdf           --> manual generated pdf of programme page
├── _config.yml                 --> base coonfig for jekyll
├── _data
│   ├── navigation.yml          --> contains names and links for top navigation bar
│   └── ui-text.yml             --> contains translation for screen readers, etc.
├── Gemfile                     --> only used if website is build locally
├── index.html                  --> placeholder index.html file (no adaption needed)
├── _pages                      --> contains markdown files that will be displayed as webpages ->here is the main content<-
│   ├── call_for_paper.md
│   ├── ...
│   └── welcome.md
└── README.md                   --> the file you are currently reading mostly containing a short documentation
```

## Short Description for Important Files

### main.scss
conatinins current Coloring Scheme for page defined as variables. Main and secondary accents can be adapted easily here.
````css

:root {
  /* colors are defined on top e.g. */
  --digit-main-first: #06A69E;
  --digit-main-second: #066862;
  --digit-main-third: #A8D2CF;

  /* these are the important values (primary- & secondary-color) that are reused for styling later
  either define new values on top and use them via var(yourVariable) or set color here directly */
  --primary-color: var(--digit-main-second);
  --secondary-color: var(--digit-main-first);
}
````

### _config.yml
containing important titles and behavior of the site in general (*the following is just a description and not the correct syntax*) e.g.
````yml
name: the name displayed in the footer
title & subtitle: name and subtitle displayed in the top left corner
...
footer: containing links, icons and names displayed in the footer

further configuration of plugins & template
````


### _data/navigation.yml
containing elements for top navigation
````yml
main:
  - title: name of element
    url: reference (external links are possible)
````

### _pages/something.md
Page with content that will be displayed.
Pages start with a header with jekyll configuration (in between the `---`) following the markdown content
````markdown
---
title: title of the page
permalink: link, where the page should be reachable (otherwise internal references has to be used in navigation etc.)
---

## Markdown content following below
Markdown can be used normally and will be compiled into HTML later.
````

### programme.pdf and creation
The `programme.pdf` is a pdf of the current Programme web page. It has to be manually created via the following command:
````bash
# google-chrome can be used instead of chromium as well
chromium --print-to-pdf=programme.pdf --print-to-pdf-no-header --headless --disable-gpu --virtual-time-budget=5000 https://ifip-summerschool.github.io/programme/
````

Please make sure to move it to the correct location after creating the pdf.