---
title       : John Hopkins Data Scientist Developing Data Products
subtitle    : Peer Assignment to sell 'Iris Species Predictor' application
author      : Trevor Kelley
framework   : html5slides   # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
warning     : Must set library(slidify) before knitr
---

## Overview
<h4>The <b>Iris Species Predictor</b> application</h4>

- An interactive web site.
- Helps you identify the species of an Iris.
- Compares your specimen to a large database.
- Uses the latest in Machine Learning to predict.
<p/>
&nbsp;
<p/>
&nbsp;
<p/>
&nbsp;
<p/>
&nbsp;
<p/>
Hint: Click &lt;Space Bar&gt; to view next slide.

---

## How you use it

- Measure the <b>Sepal</b> length and width in centimetres.
- Use the sliding bar to set the metrics for your specimen.
- The the <b>Species</b> of your specimen will be predicted.<br/>
  (setosa, versicolor, virginica)
- Where your specimen falls in relation to the reference iris is displayed.




--- 

## How it works under the covers




```r
# Use a random forest algorithm to fit non-linear relationships.
modFit <- train(Species ~ ., method = "rpart", data = iris)
irisP <- data.frame(Sepal.Length = numeric(1), Sepal.Width = numeric(1), Petal.Length = numeric(1), 
    Petal.Width = numeric(1), Species = character(1), stringsAsFactors = TRUE)

irisP$Sepal.Length <- 6  # Entered by slider
irisP$Sepal.Width <- 3.2  # Entered by slider
irisP$Petal.Length <- 3  # Entered by slider
irisP$Petal.Width <- 1.5  # Entered by slider
irisP$Species <- predict(modFit, irisP)
irisP$Species
```

```
## [1] versicolor
## Levels: setosa versicolor virginica
```


---

## What you see

![plot of chunk unnamed-chunk-3](figure/unnamed-chunk-3.png) 

Notice your specimen is shown as an <font face="verdana" color="green"><b>X</b></font> in the predicted color.

---


## Where to get it

You can start using the <b>Iris Species Predictor</b> at

URL: <a ref='https://trevorbkelley.shinyapps.io/PeerAssessment_A_Shiny'><small>https://trevorbkelley.shinyapps.io/PeerAssessment_A_Shiny</small></a>
<p/>
![alt Picture of an Iris](http://www.flower-arrangement-advisor.com/images/dark_blue_iris_flowers.jpg)


