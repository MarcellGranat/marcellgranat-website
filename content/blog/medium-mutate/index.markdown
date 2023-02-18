---
title: "Being effective in R: manage memory demanding iterations in the Tidyverse"
author: Marcell Granat
date: '2023-01-29'
format: hugo
slug: medium-mutate
tags:
  - R programming
  - Medium
summary: "My new blogpost on [Medium](https://medium.com/@granatcellmar98/being-effective-in-r-manage-memory-demanding-iteration-in-the-tidyverse-9dfb05607e3f) presents  a universally working solution to memory-demanding iterations that is easy to interpret and has other beneficial features."
links:
- icon: medium
  icon_pack: fas
  name: Medium
  url: https://medium.com/@granatcellmar98/being-effective-in-r-manage-memory-demanding-iteration-in-the-tidyverse-9dfb05607e3f
---

Without a question, the popularity of R is related to the excellent human-readable pipeline of the Tidyverse. It is a game-changer how easily you can manipulate your data with dyplr functions and how easy these expressions are to understand.

You can simply use the mutate function to create or modify a variable of the table, and the code can interpret easily (even for non-programming co-workers).

But a common issue is that if you write complex iterations, which may be computationally demanding from a memory usage aspect, then most users stand by using this readable framework and apply snippets that solve the issue, but no one will understand what happens there (after a week, not even the one who wrote it).

My new blogpost on [Medium](https://medium.com/@granatcellmar98/being-effective-in-r-manage-memory-demanding-iteration-in-the-tidyverse-9dfb05607e3f) presents  a universally working solution by extending the dplyr::mutate() function.
