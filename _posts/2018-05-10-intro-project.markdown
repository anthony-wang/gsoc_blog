---
layout: post
title:  "Brief introduction to Julia and Makie.jl"
date:   2018-05-10 18:40 +0200
categories: jekyll update intro Julia Makie
---

Hi again.

Today we will talk briefly about the library package [`Makie.jl`](https://github.com/JuliaPlots/Makie.jl) that I will be working on as my GSoC project.

`Makie.jl​` is a ​new plotting library for [Julia](https://github.com/JuliaLang)[^julia-details], providing an interface for ​GLVisualize​, with emphasis on interactivity and speed. The ​[current documentation​](https://github.com/SimonDanisch/MakieDocs) is in need of a rewrite, to ensure that it is understandable and illustrative, and example code snippets and outputs need to be added to the documentation where necessary.

Additionally, there is a database containing example code snippets and example data that can be used to make plots with Makie. It is a working point of this project to programmatically integrate these code snippets including the Makie-generated output plots into the documentation pages. In addition, tests for the plotting need to be written to verify plotting functionality after coding changes.

Another goal of this project is to create more impressive and creative plotting examples (e.g. [these here](https://www.r-graph-gallery.com/all-graphs/)) for the examples gallery to showcase the power and flexibility of the `Makie.jl` library.

The full proposal, with more pretty plots🌈🤯 and the project working plan can be found hosted online on [Google Docs](https://docs.google.com/document/d/1JLog0PG7NPysdSjQNZRpaJUcJ2nb4jW9uvWqV0aRE6I/edit?usp=sharing).

The main working packages of my project are:
1. Extending the documentation and documentation capabilities of `Makie.jl`
1. Implement database reference queries in the documentation pages
1. Improve current documentation
1. Implement additional plot examples
1. Implement plots collage image for categorical pages (e.g. collage of all scatter plots)
1. Implement preview gallery / categorical pages of plot types (e.g. all scatter plots)

My mentor (also the owner and maintainer of the repo) is [Simon Danisch](https://github.com/SimonDanisch/).

Now, time to get started!!

[^julia-details]: For an introduction to Julia, consult the many online resources such as https://docs.julialang.org/en/stable/manual/introduction/.

<br>

---

<br>

![GSoC logo]({{ site.url }}/gsoc_blog/assets/img/GSoC-logo-horizontal-800.png)
<sub>Image source: [Google Summer of Code](https://developers.google.com/open-source/gsoc/resources/marketing#logos_and_artwork), CC BY-NC-ND 3.0</sub>