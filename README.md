
## About this slide deck

This slide deck is created with the `xaringan` R package (https://github.com/yihui/xaringan), which generates remark.js slides from R-Markdown. For additional documentation on `xaringan` see [R Markdown: The Definitive Guide (Ch 7)](https://bookdown.org/yihui/rmarkdown/xaringan.html).

### Style

There is a custom css file to use called chopr.css. 

If the theme uses google fonts, you need an active internet connection during the presentation to show the slides with your chosen fonts. To print the slide deck to pdf (for sharing or offline use), use `pagedown::chrome_print()`.

### Packages

You may need the following: `install.packages("xaringan", "fontawesome")`

## Tips for translating from ppt to rmd

### Accessibility

Be sure to include informative alt text for every image. End alt text with punctuation (like a period), since that will make a screen reader read it more naturally. 

### Slide notes

At the bottom of a slide, type `???` and a new line to begin the slide notes. These will show up in presenter mode. Note that you can't have spaces after the ?'s, just the newline. If you provide live coding instructions in the slide notes, use `>` to distinguish that from speaking notes. 

Note that on incremental slides, the presenter notes only show up on the last slide, which may not be what you want. If you use layout slides (see [incremental slides](#incremental-slides)) instead, you can specify notes for each incremental slide.  

### Preview slides as you go

It's important to see how formatting looks on the slides, so you can adjust as needed. Instead of knitting to see how your changes look on the slides, use xaringan's inifnite moon reader to see updates in real time as you type. In the console, run

```
xaringan::inf_mr()
```

And then edit your .rmd file and you'll see changes show up as you go in the preview. When ever you save, it will re-knit the whole file, but even between saves it will update with all your changes as you make them. 

Note that every once in a while something will get wonky with the css in the preview; if you save the .rmd file (which knits), that should fix it. You can also try clearing the preview from the viewer, and then knitting or re-running `inf_mr()`. 

### Controlling slide layout

There are a few classes of slides available with different layouts. 

* make a smaller header for the slide (e.g. if the text is running onto a second line) with `class: small-header`
* a set of classes are available to highlight one or more items in a list, e.g. `class: emphasize-1` to highlight the first item in a list. These can be used as an alternative to making each point show up incrementally. You can combine classes, so to highlight lines 1-2, `class: emphasize-1,  emphasize-2`
* create the title slide with `class: title-slide`. Note that you must set `seal: false` in the YAML or xaringan will also auto-generate a title slide (which is not nicely formatted). The title slide can be built with variables called from the YAML, which means you should just copy-paste it exactly for each new presentation, only updating the info in the YAML header to change the content (talk title, author, etc.). 
* create a section slide with `class: section-slide`, to denote a new subsection within the presentation
* create a special Your Turn slide with `class: your-turn`, for learner engagement activities
* create a CHOPR announcement slide with `class: chopr-slide`, for slides at the beginning or end of a talk with CHOPR info or announcements. For these slides, be sure to insert the CHOPR logo image

Note that often the easiest way to control vertical space on a slide is to add `<br>` lines wherever you want more space. For example, if you have a slide with a small amount of text on it, you may want to put one or more `<br>` lines between the header and the text to move the text down a bit. [Remember that just entering blank lines in markdown usually has no effect on the output document](https://yihui.org/en/2021/06/markdown-breath/).

You can also use `.pull-left[]`, `.pull-right[]`, and `.pull-down[]` to position content on the left, right, or bottom of the slide respectively. 

You can make a section of text smaller or larger than it normally would be with `.small[]` or `.big[]`, respectively, and `.tiny[]` or `.huge[]` for more extreme change. 

To get small text at the bottom of the screen, such as for citations or footnotes, use `.footnote[]`.

### Highlighting code

You can [highlight lines of code](https://bookdown.org/yihui/rmarkdown/some-tips.html#highlight-code-lines) to draw attention to them. If you're highlighting entire lines, then it can be done on functioning R code (i.e. it can be a code chunk that gets evaluated). 

You can also [highlight parts of lines](https://stackoverflow.com/questions/52016911/highlight-selection-of-code-in-xaringan/52018533) (if you just want to highlight a single argument in a function, for example) by using `highlightSpans: true` in the YAML and backticks around the piece you want to highlight, but that will break the code --- so you can only use this on chunks with eval set fo FALSE. 

By default, the code is highlighted with the same color as items in a list are with the `emphasize` classes, so you can use that to coordinate code and text. For an example, see the "Statistical models in R" slides --- it is a set of incremental layout slides, with each one highlighting a different piece of code and corresponding item in the text list. 

### Incremental slides

There are a few ways to do incremental slides in xaringan. The easiest is to separate material that should appear incrementally by `--` (note that `---` denotes a new slide, and `--` incremental additions to the current slide). Note that any notes you have for the slide will only show up in presenter view on the last slide in the series, so this may not work for all cases. 

Another approach is to use [layout slides](https://slides.yihui.org/xaringan/incremental.html#12). If you have a list in your layout slide and you want to emphasize one item at a time in the list, you can use the `emphasize-1`, `emphasize-2` etc. slide classes to highlight the 1st, 2nd, etc. item in a list.  

### Watch out for curly quotes 

When you copy-paste content from MS Office products, it often uses curly single and double quotes, which will look weird in your rendered document. 

After you've done all your copy-pasting, do a find and replace through the whole document for single and double curly quotes, both opening and closing. Here are examples you can use in your search: ‘ ’ “ ”
