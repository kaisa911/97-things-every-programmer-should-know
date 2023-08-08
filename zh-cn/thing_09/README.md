# 在责怪他人之前，先检查您的代码

Developers — all of us! — often have trouble believing our own code is broken. It is just so improbable that, for once, it must be the compiler that's broken.

开发者——我们所有人！——经常难以相信自己的代码是有问题的。这太不可能了，以至于，这一次，一定是编译器出了问题。

Yet in truth it is very (very) unusual that code is broken by a bug in the compiler, interpreter, OS, app server, database, memory manager, or any other piece of system software. Yes, these bugs exist, but they are far less common than we might like to believe.

然而，事实上，代码被编译器、解释器、操作系统、应用服务器、数据库、内存管理器或其他任何系统软件的 bug 所破坏是非常（非常）罕见的。是的，这些 bug 存在，但它们比我们想象的要少得多。

I once had a genuine problem with a compiler bug optimizing away a loop variable, but I have imagined my compiler or OS had a bug many more times. I have wasted a lot of my time, support time, and management time in the process only to feel a little foolish each time it turned out to be my mistake after all.

我曾经遇到过一个真正的编译器 bug，它把一个循环变量优化掉了，但我想象过我的编译器或操作系统有 bug 的次数要多得多。在这个过程中，我浪费了很多自己的时间、支持时间和管理时间，每次发现最后还是我的错误时，都会感到有点傻。

Assuming the tools are widely used, mature, and employed in various technology stacks, there is little reason to doubt the quality. Of course, if the tool is an early release, or used by only a few people worldwide, or a piece of seldom downloaded, version 0.1, Open Source Software, there may be good reason to suspect the software. (Equally, an alpha version of commercial software might be suspect.)

假设工具被广泛使用、成熟，并且在各种技术栈中使用，那么没有理由怀疑它们的质量。当然，如果工具是一个早期版本，或者只有少数人在全球使用，或者是一个很少下载的、0.1 版本的开源软件，那么可能有充分的理由怀疑软件。（同样地，商业软件的 alpha 版本也可能值得怀疑。）

Given how rare compiler bugs are, you are far better putting your time and energy into finding the error in your code than proving the compiler is wrong. All the usual debugging advice applies, so isolate the problem, stub out calls, surround it with tests; check calling conventions, shared libraries, and version numbers; explain it to someone else; look out for stack corruption and variable type mismatches; try the code on different machines and different build configurations, such as debug and release.

考虑到编译器 bug 是多么罕见，你最好把你的时间和精力放在找到你代码中的错误上，而不是证明编译器是错的。所有通常的调试建议都适用，所以要隔离问题、替换调用、用测试包围它；检查调用约定、共享库和版本号；向别人解释；注意栈损坏和变量类型不匹配；在不同的机器和不同的构建配置上尝试代码，比如调试和发布。

Question your own assumptions and the assumptions of others. Tools from different vendors might have different assumptions built into them — so too might different tools from the same vendor.
When someone else is reporting a problem you cannot duplicate, go and see what they are doing. They maybe doing something you never thought of or are doing something in a different order.

质疑你自己和他人的假设。来自不同供应商的工具可能有不同的内置假设——来自同一供应商的不同工具也可能如此。 当别人报告一个你无法复现的问题时，去看看他们在做什么。他们可能在做你从未想过的事情，或者以不同的顺序做事情。

As a personal rule if I have a bug I can't pin down, and I'm starting to think it's the compiler, then it's time to look for stack corruption. This is especially true if adding trace code makes the problem move around.

作为一个个人规则，如果我有一个无法确定的 bug，并且我开始认为是编译器的问题，那么就是时候去寻找栈损坏了。如果添加跟踪代码使问题移动了位置，那就更是如此。

Multi-threaded problems are another source of bugs to turn hair gray and induce screaming at the machine. All the recommendations to favor simple code are multiplied when a system is multi-threaded. Debugging and unit tests cannot be relied on to find such bugs with any consistency, so simplicity of design is paramount.

多线程问题是另一种让头发变灰并引起对机器尖叫的 bug 来源。所有推荐使用简单代码的建议，在系统是多线程时都要乘以很多倍。调试和单元测试不能被依赖来一致地找到这样的 bug，所以设计的简单性至关重要。

So before you rush to blame the compiler, remember Sherlock Holmes' advice, "Once you eliminate the impossible, whatever remains, no matter how improbable, must be the truth," and prefer it to Dirk Gently's, "Once you eliminate the improbable, whatever remains, no matter how impossible, must be the truth."

所以，在你急于责怪编译器之前，记住夏洛克·福尔摩斯（Sherlock Holmes） 的建议，“一旦你排除了不可能的事情，剩下的无论多么不可能，都必须是真相”，并且优先于迪克·金特利（Dirk Gently）的，“一旦你排除了不可能的事情，剩下的无论多么不可能，都必须是真相。”

By [Allan Kelly](http://programmer.97things.oreilly.com/wiki/index.php/Allan_Kelly)