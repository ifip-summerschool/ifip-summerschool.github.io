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
│   │   ├── archive   --> content for archive pages
│   │   │   └── 2022  --> assets for archive 2022 page
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
│   ├── archive       --> subfolder for old summer-school pages
│   │   └── 2022.md --> Combined Archive Page of Summer School 2022 (for HowTo see below)
│   ├── call_for_papers.md
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

## How To Archive

To create an archive follow the steps below:

1. Create a File in *_pages/archive/{year}.md*
    - change title accordingly
    - change permalink to "/archive/{year}"
1. copy assets (mainly images) into */assets/images/archive/{year}*
1. Copy the necessary content from the current IFIP Pages (we used):
    - Image from *Welcome* Page
    - *Call For Papers* Page (removing EasyChair Link)
    - *Committee* Page
    - Sponsors (from *Welcome* Page)
    - make sure to adapt asset links to use */assets/images/archive/{year}/...*
1. Create a new entry in the Previous Conferences Page (*/_pages/previous_conferences*)
