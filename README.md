journal-chicago
===============

An "[RMarkdown](http://rmarkdown.rstudio.com/) HTML theme" for a bootstrapped, modern, clean interface intended for technical writings. This design is a modification of the [Bootswatch Journal](http://bootswatch.com/journal/) theme included in RMarkdown.

## Usage

Reference the stylesheet ```css/journal-chicago.css``` in your R source code.


### YAML
The design can be [included as a YAML header](http://rmarkdown.rstudio.com/html_document_format.html#custom-css) in your document.


```yaml
---
title: "Fun with RMarkdown" 
output:
	html_document:
		css: journal-chicago/css/journal-chicago.css
```

### options
Another method is to use R code. In a separate document, i.e., ```style.R```, include the following code:
```r
options(rstudio.markdownToHTML = 
            function(inputFile, outputFile) {      
                require(markdown)
                markdownToHTML(inputFile, outputFile, stylesheet='journal-chicago/css/journal-chicago.css')   
            }
)
```
Return to your source document and include the following line:
```r
source("style.R")
```

## Other uses

The stylesheet can be used for other purposes, but this repository will be tuned to generate RMarkdown files.

## League Spartan font

[League Spartan](https://www.theleagueofmoveabletype.com/league-spartan) is an open-source font released by Moveable Type and is referenced under ```font-family```. However, this font will not be used unless it is installed locally (e.g., the fonts are not included). This is due to issues with Pandoc recognizing the mime type of these font files.

## License

This project is licensed under Apache License 2.0. See [LICENSE](LICENSE) for more information.