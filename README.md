# STAT545-hw-Fibke-Chad


## STAT545-hw01-An Introduction to github

Hey everyone, my name is Chad Fibke and I've just started a MSc in *Population & Public Health* working under [Dr.Amee Manges](http://spph.ubc.ca/person/amee-manges/)! We are working on **Poop enemas** and how they can prevent infections! **All of these fancy words were added using R-studio**. 

![](https://github.com/googlei18n/noto-emoji/blob/f2a4f72/svg/emoji_u1f4a9.svg)

When I'm not wrking with poop enemas I like to:
  + Bike
  + Run
  + Paintball
  + Swing-dance 
  
### GitHub Workflow & RMarkdown Experience 

#### GitHub Workflow
  + The README.md will introduce who I am 
  + The file hw01_gapminder_files/figure-markdown_github-ascii_identifiers/ will show you the plots I made!
  + The file named hw01_gapminder.md, ~~not hw01_gapminder.Rmd~~, will include a quick exploration of the gapminder data. It will show you the steps I take when loading a new data set! 
  
  
#### RMarkdown Experience 
  + I had problems with adding color to each code chunk. I think adding color would help with the flow.
  + I used the [This site](http://rmarkdown.rstudio.com/lesson-1.html) to get some more information on the idea behind Rmarkdown
  + I tried using [This site](https://yihui.name/knitr/options/), but it was intimidating!

## STAT545-hw02-Data wrangling with dplyr


Here I show a way to explore a new dataset (gapminder), and use dplyr functions to wrangle the dataset: select() filter() group_by() summarize() arrange()


+ [HW02.md](https://github.com/ChadFibke/STAT545-hw-Fibke-Chad/blob/master/HW02_Dplyr/HW02_Dplyr.md) is where I take you on a coding adventure through the assignment.
+ And [Over here](https://github.com/ChadFibke/STAT545-hw-Fibke-Chad/tree/master/HW02_Dplyr/figure-markdown_github-ascii_identifiers) is where you can find my graphs!

I had problems trying to pick a problem to look at in depth! Once I found an issue to look at a lot of the filtering was an issue. There was a lot of objects building up in my work environment, so at times I found myself calling on the wrong object (I thought R knew what I was thinking!). I also wanted to make some adjustments to the graph outside of the points so I had to do some googling! 

I used a lot of resources for ggplots! There is:

+ [One](http://www.sthda.com/english/wiki/ggplot2-themes-and-background-colors-the-3-elements) that will allow you to customize your background.
+ [Two](http://ggplot2.tidyverse.org/reference/index.html) is a good place for labels, scales, and any other need you may have!

## STAT545-hw03-Data visualization with ggplot2


Here I show some grammar for graphics and use ggplot2 to view the gapminder dataset:

[HW03.Rmd](https://github.com/ChadFibke/STAT545-hw-Fibke-Chad/blob/master/HW03_GGPLOT2/HW03_GGPLOT2.Rmd)

[HW03.md](https://github.com/ChadFibke/STAT545-hw-Fibke-Chad/blob/master/HW03_GGPLOT2/HW03_GGPLOT2.md)
### Report on progress

+ I had a lot of problems trying to plot 2 different y-variables to the same plot **AND** keeping the original units/trend. I feel like I really over did it on the line graphs, but there is a little bit of magic in each :).
+ I also had a problem labeling the text once it was in jitter form! Adding text only seemed to align to the geom_point position.

### Here are some references that really helped me:
+ [One](http://www.sthda.com/english/wiki/ggplot2-themes-and-background-colors-the-3-elements) that will allow you to customize your background.
+ [Two](http://ggplot2.tidyverse.org/reference/index.html) is a good place for labels, scales, and any other need you may have!
+ [Three](https://stackoverflow.com/questions/10349206/add-legend-to-ggplot2-line-plot) helped me add a legend and also helped with adding multiple y variables to a plotand.
+ [Four](https://stackoverflow.com/questions/1330989/rotating-and-spacing-axis-labels-in-ggplot2) helped with some of my axis issues!
+ [Five](https://stackoverflow.com/questions/15624656/label-points-in-geom-point) helped with adding text directly to my plots!

## STAT545-hw04- Reshaping, joining, and life lessons about data frames

Over here, I show how to subset the gapminder dataset and show how to reshape and join other datasets to gapminder using: spread() gather(), and xxx_join() 

[HW04.Rmd](https://github.com/ChadFibke/STAT545-hw-Fibke-Chad/blob/master/HW04_Reshaping_joining/HW04.Rmd)

[HW04.md](https://github.com/ChadFibke/STAT545-hw-Fibke-Chad/blob/master/HW04_Reshaping_joining/HW04.md)
### Report on progress

+ I had problems trying to get the 2 mini data frames side by side. I tried "knitr::kable(list(DF.1,DF.2)), which would be executed properly in R, but it did not work when I tried to knit it.     


### Here are some references that really helped me:
+ [One](https://stackoverflow.com/questions/31788195/how-to-control-new-variables-names-after-tidyrs-spread) showed me how to rename variables after spreading them out.
+ [Two](http://ggplot2.tidyverse.org/reference/annotate.html) helped me add the R-squared value to my plot.
+ [Three](http://r4ds.had.co.nz/tidy-data.html) helped teach me how to reshape data.
+ [Four](http://stat545.com/bit001_dplyr-cheatsheet.html) help me understand how to use the join functions!
+ The economic status for selected countries was found [Here](http://www.un.org/en/development/desa/policy/wesp/wesp_current/2014wesp_country_classification.pdf)
+ The HDI stands for **H**uman **D**evelopment **I**ndex. This index is an indirect measure the quality of life in the respective country. An HDI score of 1 = you live in a paradise, and an HDI of 0 = you live in a cruel place. The HDI information was collected [Over Here](http://hdr.undp.org/en/composite/HDI)

## STAT545-hw05- Where it all comes together 

Here I show how to play with factors, read files in and out of R, and using Dplyr and ggplots along the way:

[HW05.Rmd](https://github.com/ChadFibke/STAT545-hw-Fibke-Chad/blob/master/HW05_THE_FINISHER/HW05.Rmd)

[HW05.md](https://github.com/ChadFibke/STAT545-hw-Fibke-Chad/blob/master/HW05_THE_FINISHER/HW05.md)

### Report on progress

+ I thought cow plots was fun to use, **BUT** it took me forever to figure out that to use cow plots you need to have the plot previously printed and assigned. At first I was only assigning them and I consistently got an error!
+ I also had problems getting the pathway to the attached PDF. To attach a PDF to the report I had to specify the path from our work environment to  pdf... which was in the same spot, so I ended up only needing to state the name of the pdf.


### Here are some references that really helped me:
+ [One](https://cran.r-project.org/web/packages/cowplot/vignettes/introduction.html) showed me how to use cow plots!
+ [Two](http://stat545.com/block029_factors.html) showed me how to work with factors!
+ [Three](http://stat545.com/block026_file-out-in.html) showed me how to save files and bring them back into R.