
## About this slide deck

This slide deck is created with the `xaringan` R package (https://github.com/yihui/xaringan), which generates remark.js slides from R-Markdown. For additional documentation on `xaringan` see [R Markdown: The Definitive Guide (Ch 7)](https://bookdown.org/yihui/rmarkdown/xaringan.html).

### Style

The theme is controlled by the `xaringanthemer` package (https://pkg.garrickadenbuie.com/xaringanthemer/articles/xaringanthemer.html). 

Matching themes for ggplot: https://pkg.garrickadenbuie.com/xaringanthemer/index.html#matching-ggplot-themes 

Using apron for additional css: https://github.com/xaprb/story/blob/master/static/css/apron.css 
See options for slide layouts using apron here: https://story.xaprb.com/slides/adirondack/#5

If the theme uses google fonts, you need an active internet connection during the presentation to show the slides with your chosen fonts. To print the slide deck to pdf (for sharing or offline use), use `pagedown::chrome_print()`.

## Tips for translating from ppt to rmd

### Preview slides as you go

It's important to see how formatting looks on the slides, so you can adjust as needed. Instead of knitting to see how your changes look on the slides, use xaringan's inifnite moon reader to see updates in real time as you type. In the console, run

```
xaringan::inf_mr()
```

And then edit your .rmd file and you'll see changes show up as you go in the preview. When ever you save, it will re-knit the whole file, but even between saves it will update with all your changes as you make them. 

Note that every once in a while something will get wonky with the css in the preview; if you save the .rmd file (which knits), that should fix it. 

### Controlling slide layout

There are a few classes of slides available with different layouts. 

* make a smaller header for the slide (e.g. if the text is running onto a second line) with `class: small-header`

Note that often the easiest way to control vertical space on a slide is to add `<br>` lines wherever you want more space. For example, if you have a slide with a small amount of text on it, you may want to put one or more `<br>` lines between the header and the text to move the text down a bit. [Remember that just entering blank lines in markdown usually has no effect on the output document](https://yihui.org/en/2021/06/markdown-breath/).

### Highlighting code

You can [highlight lines of code](https://bookdown.org/yihui/rmarkdown/some-tips.html#highlight-code-lines) to draw attention to them. If you're highlighting entire lines, then it can be done on functioning R code (i.e. it can be a code chunk that gets evaluated). 

You can also [highlight parts of lines](https://stackoverflow.com/questions/52016911/highlight-selection-of-code-in-xaringan/52018533) (if you just want to highlight a single argument in a function, for example) by using `highlightSpans: true` in the YAML and backticks around the piece you want to highlight, but that will break the code --- so you can only use this on chunks with eval set fo FALSE. 

### Incremental slides

There are a few ways to do incremental slides in xaringan. The easiest is to separate material that should appear incrementally by `--` (note that `---` denotes a new slide, and `--` incremental additions to the current slide). Note that any notes you have for the slide will only show up in presenter view on the last slide in the series, so this may not work for all cases. 

Another approach is to use [layout slides](https://slides.yihui.org/xaringan/incremental.html#12). If you have a list in your layout slide and you want to emphasize one item at a time in the list, you can use the `emphasize-1`, `emphasize-2` etc. slide classes in the chopr.css file to highlight the 1st, 2nd, etc. item in a list.  

### Watch out for curly quotes 

When you copy-paste content from MS Office products, it often uses curly single and double quotes, which will look weird in your rendered document. 

After you've done all your copy-pasting, do a find and replace through the whole document for single and double curly quotes, both opening and closing. Here are examples you can use in your search: ‘ ’ “ ”