---
title       : R Slidify Tutorial
subtitle    : Quick Start to Slidify in R
author      : Kory Becker
job         : http://www.primaryobjects.com
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [bootstrap, quiz]            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Introduction

Creating a slideshow presentation in R is easy!

1. Install slidify.
2. Edit Rmd document to create slides.
3. Publish to html and web!

--- .class #id
## Installing Slidify

The following code installs slidify in R.


```r
## Including the required R packages.
packages <- c('devtools', 'stringi')
if (length(setdiff(packages, rownames(installed.packages()))) > 0) {
  install.packages(setdiff(packages, rownames(installed.packages())))  
}

library(devtools)

install_github('ramnathv/slidify')
install_github('ramnathv/slidifyLibraries')

library(slidify)
author('Slidify')
```

That last command should create ~/Slidify/index.Rmd for you.

--- .class #id
## Set the Title and Author

index.Rmd should be opened automatically for you.

Set the title, subtitle, and author. 


```r
---
title       : Your Title Here
subtitle    : Your subtitle here
author      : Me
job         : Cool Guy
framework   : io2012
highlighter : highlight.js
hitheme     : tomorrow
widgets     : [bootstrap, quiz]
mode        : selfcontained
knit        : slidify::knit2slides
---
```

We're including the widgets "bootstrap, quiz" to support interactive slides.

--- .class #id
## Adding a Slide

To create a slide, include the following code per slide.


```r
--- .class #id 
## A Slide Title

This is my first slide.
```

Separate slides with 3 dashes.

--- .class #id
## Previewing

To preview the slideshow, run the command:


```r
slidify('index.Rmd')
```

Then open your folder, navigate into the presentation folder, and double-click index.html.

--- .class #id
## Making Changes

Any time you modify a slide, run the command again.


```r
slidify('index.Rmd')
```

Then refresh the web page to see the results.

--- .class #id
## Publishing

Slidify automatically creates a git repository for you.

This makes publishing easy.

1. Commit your local changes to git, under the branch name "gh-pages".
2. Create a repository on GitHub.
3. Push your repository to GitHub.
4. Access your presentation at http://username.github.io/project-name

Example:
http://primaryobjects.github.io/slidify

--- &radio
## Quiz 1/2

What do the widgets "bootstrap, quiz" allow?

1. Displaying a blue background for the presentation.
2. Starting a new presentation from scratch.
3. _Including support for interactive slides._
4. Creating a black & white presentation.

*** .hint
One of the widgets is named "quiz", which lets the user interact with elements on the slide.

*** .explanation
bootstrap and quiz allow support for interactive slides, specifically Quiz-enabled slides. See http://slidify.github.io/dcmeetup/demos/interactive/

--- &radio
## Quiz 2/2

What command separates slides in a presentation?

1. *
2. ##
3. _---_
4. ====

*** .hint
Three symbols separate slides in a presentation, but which symbol is it?

*** .explanation
To separate slides in a slidify Rmd presentation, use 3 dashes. You can follow this by a class name for styling.

For example:


```r
--- .class #id 
```

--- .class #id
## Conclusion

Now, you're a slidify professional!

http://www.primaryobjects.com
