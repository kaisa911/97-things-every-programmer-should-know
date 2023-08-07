# 自动化你的编码标准。

You've probably been there too. At the beginning of a project, everybody has lots of good intentions — call them "new project's resolutions." Quite often, many of these resolutions are written down in documents. The ones about code end up in the project's coding standard. During the kick-off meeting, the lead developer goes through the document and, in the best case, everybody agrees that they will try to follow them. Once the project gets underway, though, these good intentions are abandoned, one at a time. When the project is finally delivered the code looks like a mess, and nobody seems to know how it came to be this way.

你可能也有过这样的经历。在项目开始时，每个人都有很多好意愿——称之为“新项目的决心”。很多这样的决心都写在文件中。关于代码的那些最终会出现在项目的编码标准中。在启动会议上，首席开发人员会浏览文件，并在最好的情况下，每个人都同意他们将尝试遵循它们。然而，一旦项目开始，这些好意愿就一个接一个地被放弃了。当项目最终交付时，代码看起来像一团糟，似乎没有人知道它是如何变成这样的。

When did things go wrong? Probably already at the kick-off meeting. Some of the project members didn't pay attention. Others didn't understand the point. Worse, some disagreed and were already planning their coding standard rebellion. Finally, some got the point and agreed but, when the pressure in the project got too high, they had to let something go. Well-formatted code doesn't earn you points with a customer that wants more functionality. Furthermore, following a coding standard can be quite a boring task if it isn't automated. Just try to indent a messy class by hand to find out for yourself.

什么时候出了问题？可能已经在启动会议上了。一些项目成员没有注意。其他人没有理解重点。更糟糕的是，有些人不同意，并已经计划了他们的编码标准叛乱。最后，有些人明白了重点并同意了，但当项目压力过大时，他们不得不放弃一些东西。格式良好的代码不能为想要更多功能的客户赢得分数。此外，如果没有自动化，遵循编码标准可能是一项相当无聊的任务。只需手动缩进一个混乱的类就可以自己找出来。

But if it's such a problem, why is that we want to have a coding standard in the first place? One reason to format the code in a uniform way is so that nobody can "own" a piece of code just by formatting it in his or her private way. We may want to prevent developers using certain anti-patterns, in order to avoid some common bugs. In all, a coding standard should make it easier to work in the project, and maintain development speed from the beginning to the end. It follows then that everybody should agree on the coding standard too — it does not help if one developer uses three spaces to indent code, and another one four.

但是，如果这是一个问题，为什么我们首先要有编码标准呢？统一格式化代码的原因之一是，这样没有人可以通过以他或她的私有方式格式化代码来“拥有”代码。我们可能希望防止开发人员使用某些反模式，以避免一些常见的错误。总之，编码标准应该使项目更容易工作，并从开始到结束保持开发速度。因此，每个人都应该同意编码标准——如果一个开发人员使用三个空格缩进代码，而另一个开发人员使用四个空格缩进代码，则没有帮助。

There exists a wealth of tools that can be used to produce code quality reports and to document and maintain the coding standard, but that isn't the whole solution. It should be automated and enforced where possible. Here are a few examples:

存在大量的工具可用于生成代码质量报告、文档和维护编码标准，但这并不是整个解决方案。应该在可能的情况下自动化和强制执行。以下是一些示例：

- Make sure code formatting is part of the build process, so that everybody runs it automatically every time they compile the code.
- Use static code analysis tools to scan the code for unwanted anti-patterns. If any are found, break the build.
- Learn to configure those tools so that you can scan for your own, project-specific anti-patterns.
- Do not only measure test coverage, but automatically check the results too. Again, break the build if test coverage is too low.

- 确保代码格式化是构建过程的一部分，这样每次编译代码时每个人都会自动运行它。
- 使用静态代码分析工具扫描代码以查找不需要的反模式。如果发现任何问题，请中断构建。
- 学习配置这些工具，以便您可以扫描您自己的项目特定反模式。
- 不仅要测量测试覆盖率，还要自动检查结果。同样，如果测试覆盖率过低，请中断构建。

Try to do this for everything that you consider important. You won't be able to automate everything you really care about. As for the things that you can't automatically flag or fix, consider them to be a set of guidelines supplementary to the coding standard that is automated, but accept that you and your colleagues may not follow them as diligently.

尝试为您认为重要的所有内容做到这一点。你无法自动化你真正关心的一切。至于那些你无法自动标记或修复的事情，请将它们视为补充编码标准的一组指南，该标准是自动化的，但请接受你和你的同事可能不会如此勤奋地遵循它们。

Finally, the coding standard should be dynamic rather than static. As the project evolves, the needs of the project change, and what may have seemed smart in the beginning, isn't necessarily smart a few months later.

最后，编码标准应该是动态而不是静态的。随着项目的发展，项目的需求发生变化，可能在开始时看起来很聪明，在几个月后并不一定聪明。

作者：[Filip van Laenen](http://programmer.97things.oreilly.com/wiki/index.php/Filip_van_Laenen)