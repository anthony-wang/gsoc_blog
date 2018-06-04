---
layout: post
title:  "Week 3 of GSoC"
date:   2018-06-04 13:00 +0200
categories: jekyll update Julia Makie GSoC progress report
---

Week 3 of GSoC is **done**! 😎🤠

The last two weeks were packed with lots of learning, programming, and of course debugging (including what is possibly the most embarassing programming mistake of my life :sweat_smile:[^footnote1]).

I am also happy to announce that I will be attending [JuliaCon 2018](http://juliacon.org/2018/)! This will take place during Aug. 7–11, 2018 at University College London. For a student like me, this shall be a great opportunity for learning from the best minds, seeing what else is possible with Julia, and networking. Also, it would be great to visit London :wink:.

The following is a short progress report of the past two weeks' work.


#### Finished
* documentation of function signatures from [`Plots.jl`](https://github.com/JuliaPlots/Plots.jl).
* documentation of the argiment conversion functions in [`argument_conversion.jl`](https://github.com/JuliaPlots/Makie.jl/blob/aw/documentation/src/argument_conversion.jl).
* further extension of the help functions, `help`, `help_arguments`, and `help_attributes` to be more detailed and robust, and to handle more input types.
* extension of the help functions to print to a specified `io` stream (if unspecified -> `STDOUT`). This is useful to redirect the output to a file, for example (see later).
	* external `help` function prints as Markdown-parsed text
	* internal `_help` function prints plaintext
* implement `find_indices` and `example_database` functions which accept `input_tags` as the input and has optional keyword arguments `author` and `title` to further filter the results.
	* `find_indices` searches the example database for examples matching the input tags, and returns the indices. 
	* `example_database` returns the entries associated with the input tags and prints the source to the REPL by overloading `Base.show` on the `CellEntry` type.
* rewrite docstrings for plotting atomics functions
* automatically generate an overview Docs page of all plotting atomics functions in `Makie.jl` including their function signatures and attributes
* automatically generate an Docs page (examples gallery) of all examples sorted and cross-referenced by `tag`, including example code and generated plots (plots currently not working—see TODOs section).
	* implement an internal `_print_source` function that prints the source code of the plot example, including specifying the code flavor in a fenced block (e.g. "\`\`\`julia")
* pushed commits related to the above, [fb0f166](https://github.com/JuliaPlots/Makie.jl/commit/fb0f1668b424320e7c0f40f48a39a580dd21e060), [9d2218e](https://github.com/JuliaPlots/Makie.jl/commit/9d2218ef326571f3b6a4256fc366ebe030d0bdfe), [e01b10d](https://github.com/JuliaPlots/Makie.jl/commit/e01b10da95c3f24e96dc7b2f539766c128b8e030), [6c47286](https://github.com/JuliaPlots/Makie.jl/commit/6c472865a658d3e587d304f7a4f8c9277bcf35ce), [a453cf7](https://github.com/JuliaPlots/Makie.jl/commit/a453cf7f203401aa37e021f3ab432e1d4a9f435f), [1fd65fa](https://github.com/JuliaPlots/Makie.jl/commit/1fd65fa294fb0d7c87d748464bad7233d54d1f09), [9d5e7e9](https://github.com/JuliaPlots/Makie.jl/commit/9d5e7e9bff13aba5bc6515f0beda82e5dfe6ed93), [223e5b6](https://github.com/JuliaPlots/Makie.jl/commit/223e5b6d9232ce1ac936df4e8327c5184b66fe67), [888479d](https://github.com/JuliaPlots/Makie.jl/commit/888479d1383e3f3777a3d98a2ded559f476f2d4b), [31f482a](https://github.com/JuliaPlots/Makie.jl/commit/31f482ae04e032391237ba7e0bbc23bfd01c4024), [57d8505](https://github.com/JuliaPlots/Makie.jl/commit/57d850560837c2c95e00c3465c0663029c48286e), [62159ef](https://github.com/JuliaPlots/Makie.jl/commit/62159ef33438a7135e1a203b1f648c91ab5ff72d), and [5cf47ad](https://github.com/JuliaPlots/Makie.jl/commit/5cf47adbd0f5e084c4f0b05b80c149c29f8cf230). For more commits, please see the [`aw/documentation` branch](https://github.com/JuliaPlots/Makie.jl/tree/aw/documentation).
* one merged pull request for refactoring [\(PR #89\)](https://github.com/JuliaPlots/Makie.jl/pull/89)
* met with mentor five times in total (including yesterday).


#### TODOs
Some of next week's TODOs are:
* go through the plot examples in the examples database and test them; fix the non-functioning ones
* automatically generate a detailed Docs page of all plotting atomics functions, including plot examples and the source code for the plots
	* the source code embedding is working, but plotting is not working yet due to non-functioning backend. This should hopefully be resolved soon.
* using `Documenter.jl`'s `Selectors.matcher` and `Selectors.runner` to match and select specific plot examples from the examples database (for example by matching the specific example's title).

#### Difficulties encountered
* misunderstandings due to incorrect assumptions during debugging -- this has taught me to not rely on my own assumptions, and to improve my debugging skills!
* the backend for the plotting hasn't been fully implemented yet, as a result I cannot do the plot export + embed in the documentation pages yet. But hopefully this will be available soon!

I would like to express my gratitude to Simon Danisch for guiding me through he past two weeks, and for helping me debug my code ^^

So, that's it for today's post! Onwards to the next weeks!


<br>

[^footnote1]: This will never see the light of day.

---

<br>

![GSoC logo]({{ site.url }}/gsoc_blog/assets/img/GSoC-logo-horizontal-800.png)
<sub>Image source: [Google Summer of Code](https://developers.google.com/open-source/gsoc/resources/marketing#logos_and_artwork), CC BY-NC-ND 3.0</sub>
