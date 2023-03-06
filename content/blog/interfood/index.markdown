---
title: Web scraping with Shiny - automate your weekly food order
author: Marcell Granat
date: '2023-03-06'
format: hugo
slug: interfood
tags:
  - shiny
  - scraping
summary: "Simple, but useful application of static web scraping in a shiny web application to find your favorites in the menu."
links:
- icon: code
  icon_pack: fas
  name: GitHub
  url: https://github.com/MarcellGranat/interfood
- icon: link
  icon_pack: fas
  name: Application
  url: https://marcellgranat.com/interfood
---


# Web scraping with Shiny - automate your weekly food order <img src="https://raw.githubusercontent.com/MarcellGranat/interfood/main/logo.png" align="right" width="120px" />

Web scraping is a technology that can be used to automatically download data from online pages. It can be used in many areas: collecting data for research, monitoring prices, and automatically reporting any regularly updated online data source. In this fun project, I give an example of the latter.

The menu of Interfood is immense and I usually like to get the weekly order done quickly, so I built a small shiny application for it (Do not laugh, pancakes are really hard to find). Shiny is an application written in R (or Python) that can be stored on an online server, the biggest advantage of which is that it is incredibly easy to create.

The application works as follows: when you open it, it visits the Interfood's menu for the given week and downloads the entire offer.

``` r
read_html("https://www.interfood.hu/etlap-es-rendeles/") |> # download the entire website
    html_nodes(paste0(".cell:nth-child(1) .food-etlap-szoveg")) |> # 1st day
    html_text() |> # format to text
    head() # first 6 item

#> [1] "Zöldborsós csirkeragu leves" "Zöldborsós csirkeragu leves" "Tejfölös gombaleves V"       "Tejfölös gombaleves V"
#> [5] "Tejszínes őszibarackleves V" "Tejszínes őszibarackleves V"
```

After a few cleaning steps, the entire menu is loaded, as if reading it on the web page. The next function of the application is that we can specify which dishes we have rated and which days we would like to order. The Shiny then simply collects the dishes with the highest ratings for the given days and visually displays the recommended order.

This is not a serious data analysis task, but an excellent example of how an application that can be written in seconds can help us in many areas of life and how rewarding coding can be. The full code is available in the attached GitHub repository just as the link to the app.

