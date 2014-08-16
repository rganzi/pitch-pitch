---
title       : Pitch - Pitch
subtitle    : A Shiny PitchFX Visualization
author      : 
job         : 
framework   : io2012     # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## The Real MLB Strike Zone

- Question: does the real Major League Baseball STRIKE ZONE, as called by umpires, conform to the MLB Rulebook's definition?
  
  - If not, what are the true shape and dimensions of the strike zone?

- Major League Baseball Rulebook, Rule 2.00, The STRIKE ZONE   
<http://mlb.mlb.com/mlb/official_info/umpires/rules_interest.jsp>:

  - "The STRIKE ZONE is that area over home plate the upper limit of which is a horizontal line at the midpoint between the top of the shoulders and the top of the uniform pants, and the lower level is a line at the hollow beneath the kneecap. The Strike Zone shall be determined from the batter's stance as the batter is prepared to swing at a pitched ball."

---

## The Shiny App

The Shiny app has two main parts (switched via the radio button):

1. Plots of pitch densities -- the actual location of pitches thrown -- and colored by whether those pitches were typically called a ball or strike.

2. Plots of a General Additive Model which show the probability that a pitch thrown in a certain location will be called a strike.

- The data are from the publicly-available PitchFX database.

- Options
  - The drop down menu allows the user to analyze any of a selection of MLB pitchers.
  - You can toggle the rulebook-defined strike zone.
  - You can adjust the bounds of the x- and y-axes.

--- &twocol

## Pitch Density Plot

*** =left

- The dotted black line represents the MLB Rulebook definition of the strike zone.

- The orange contour lines represent increasing densities of called strikes. 

- The "dodger blue" contour lines indicate increasing densities of balls. 

- Each densitiy is emphasized by the background coloring of the plot.

*** =right
![plot of chunk density.plot](assets/fig/density.plot.png) 

--- &twocol

## GAM Model Plot

*** =left

- Again, the dotted black line represents the MLB Rulebook definition of the strike zone.

- Each color band represents a different probability that a pitch in a specific location will be called a strike.

- The boundary between the green and blue bands forms the shape of the modeled strike zone. At this boundary, there is a 50/50 chance of the pitch being called a strike or ball.

*** =right
![plot of chunk model.plot](assets/fig/model.plot.png) 
