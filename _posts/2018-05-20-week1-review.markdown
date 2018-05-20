---
layout: post
title:  "Week 1 of GSoC"
date:   2018-05-20 11:00 +0200
categories: jekyll update Julia Makie GSoC progress report
---

Week 1 of GSoC is **done**! 😎

This was a huge week filled with excitement and hard work—and of course, there were challenges to be overcome.

The following is a short progress report of this week's work.


#### Finished
* started a new branch of [`Makie.jl`](https://github.com/JuliaPlots/Makie.jl) at [`aw/documentation`](https://github.com/JuliaPlots/Makie.jl/tree/aw/documentation) for my work during GSoC
* implemented a `help` function and other helper functions, including `help_arguments` and `help_attributes`.
	* `help` can be used by calling `help(::Function)` or `help(::Type{T})` on a plotting function or a plot type, and returns a list of the accepted function signatures and keyword arguments (attributes).
	* `extended` is an optional keyword argument (default = false) that can in addition print out the default values of the plot attributes:

		```julia
		julia> help(Makie.Scatter; extended = true)
		Makie.scatter has the following function signatures:

		  (Vector, Vector)
		  (Vector, Vector, Vector)
		  (Matrix)
		Available attributes and their defaults for Makie.Scatter are:

		  colormap        nothing
		  colorrange      nothing
		  fxaa            false
		  glowcolor       RGBA{N0f8}(0.0,0.0,0.0,0.0)
		  glowwidth       0.0
		  ...
		```

	* in addition, these help functions take an io stream as input, so the output can be redirected to an output file, for example (this may be useful for future plans!)
* pushed four commits related to this, [fb0f166](https://github.com/JuliaPlots/Makie.jl/commit/fb0f1668b424320e7c0f40f48a39a580dd21e060), [b08e000](https://github.com/JuliaPlots/Makie.jl/commit/b08e0007928ea4363d9e07513d19ce42de9e2b40), [9d2218e](https://github.com/JuliaPlots/Makie.jl/commit/9d2218ef326571f3b6a4256fc366ebe030d0bdfe), and [31835c3](https://github.com/JuliaPlots/Makie.jl/commit/31835c3517657a42c6f2249094a6d59f1479f1d4).
* met with mentor twice this week and worked together to define tasks for this week / next week, and to solve some problems I ran into this week.


#### TODOs
* one of next week's first TODOs is to check out [`Plots.jl`](https://github.com/JuliaPlots/Plots.jl) and see what available function arguments they support, e.g.

	```julia
	plot(AbstractArray, AbstractArray; kw_args...)
	plot(AbstractArray, AbstractArray, AbstractArray; kw_args...)
	plot(AbstractArray, AbstractArray, Function; kw_args...)
	```

#### Difficulties encountered
* I encountered some difficulties in estimating the time I needed to accomplish some tasks, and also some difficulties finding time to solidly work on GSoC. I've discussed this with my mentor and we have plans and goals in place to rectify this starting the next week.

So, that's it for today's post! Onwards to the next week!


<br>

---

<br>

![GSoC logo]({{ site.url }}/gsoc_blog/assets/img/GSoC-logo-horizontal-800.png)
<sub>Image source: [Google Summer of Code](https://developers.google.com/open-source/gsoc/resources/marketing#logos_and_artwork), CC BY-NC-ND 3.0</sub>