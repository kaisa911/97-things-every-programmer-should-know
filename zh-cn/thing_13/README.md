# 代码布局的重要性

An infeasible number of years ago I worked on a Cobol system where staff weren't allowed to change the indentation unless they already had a reason to change the code, because someone once broke something by letting a line slip into one of the special columns at the beginning of a line. This applied even if the layout was misleading, which it sometimes was, so we had to read the code very carefully because we couldn't trust it. The policy must have cost a fortune in programmer drag.

多年前，我曾在一个 Cobol 系统中工作过，该系统不允许员工更改缩进，除非他们有理由更改代码。因此，我们必须非常仔细地阅读代码，因为我们不能相信它。这项政策一定耗费了程序员大量的人力物力。

There's research to show that we all spend much more of our programming time navigating and reading code — finding *where* to make the change — than actually typing, so that's what we want to optimize for.

有研究表明，在编程过程中，我们花在浏览和阅读代码上的时间要比实际键入代码的时间多得多。因为我们要找到*哪儿*要修改的地方，所以这也是我们要优化的地方。

- *Easy to scan.* People are really good at visual pattern matching (a leftover from the time when we had to spot lions on the savannah), so I can help myself by making everything that isn't directly relevant to the domain, all the "accidental complexity" that comes with most commercial languages, fade into the background by standardizing it. If code that behaves the same looks the same, then my perceptual system will help me pick out the differences. That's why I also observe conventions about how to lay out the parts of a class within a compilation unit: constants, fields, public methods, private methods.

- *便于扫描* 人们非常擅长视觉模式匹配（这是我们在大草原上发现狮子的时代遗留下来的），因此我可以通过标准化，让所有与领域不直接相关的东西，即大多数商业语言中的所有 "意外复杂性"，淡出我们的视野。如果行为相同的代码看起来都是一样的，那么我的感知系统就会帮我找出它们的不同之处。这就是为什么我也会遵守关于如何在编译单元中布局类的各个部分的约定：常量、字段、公共方法、私有方法。

- *Expressive layout.* We've all learned to take the time to find the right names so that our code expresses as clearly as possible what it does, rather than just listing the steps — right? The code's layout is part of this expressiveness too. A first cut is to have the team agree on an automatic formatter for the basics, then I might make adjustments by hand while I'm coding. Unless there's active dissension, a team will quickly converge on a common "hand-finished" style. A formatter cannot understand my intentions (I should know, I once wrote one), and it's more important to me that the line breaks and groupings reflect the intention of the code, not just the syntax of the language. (Kevin McGuire freed me from my bondage to automatic code formatters.)

- *富有表现力的布局* 我们都学会了花时间找到正确的名称，这样我们的代码就能尽可能清楚地表达它所做的事情，而不仅仅是罗列步骤，对吗？代码的布局也是表现力的一部分。第一步是让团队就基本的自动格式化达成一致，然后我可能会在编码时手动进行调整。除非存在积极的分歧，否则一个团队会很快形成一种共同的 "手工完成 "风格。对我来说，更重要的是换行和分组要反映代码的意图，而不仅仅是语言的语法。(凯文-麦奎尔（Kevin McGuire）让我摆脱了自动代码格式化工具的束缚）。

- *Compact format.* The more I can get on a screen, the more I can see without breaking context by scrolling or switching files, which means I can keep less state in my head. Long procedure comments and lots of whitespace made sense for 8-character names and line printers, but now I live in an IDE that does syntax coloring and cross linking. Pixels are my limiting factor so I want every one to contribute towards my understanding of the code. I want the layout to help me understand the code, but no more than that.

- *结构紧凑* 屏幕上的内容越多，我就能看到越多的内容，而不会因为滚动或切换文件而中断上下文，这意味着我可以在脑中保留更少的状态。对于 8 个字符的名称和行式打印机来说，长程序注释和大量空白是合理的，但现在我使用的集成开发环境可以进行语法着色和交叉链接。像素是我的限制因素，因此我希望每一个像素都能帮助我理解代码。我希望布局能帮助我理解代码，但仅此而已。

A non-programmer friend once remarked that code looks like poetry. I get that feeling from really good code, that everything in the text has a purpose and that it's there to help me understand the idea. Unfortunately, writing code doesn't have the same romantic image as writing poetry.

一位非程序员朋友曾说过，代码看起来就像一首诗。我从真正优秀的代码中体会到了这种感觉，即文本中的一切都有其目的，都是为了帮助我理解代码的思想。遗憾的是，写代码并不像写诗那样浪漫。

By [Steve Freeman](http://programmer.97things.oreilly.com/wiki/index.php/Steve_Freeman)
