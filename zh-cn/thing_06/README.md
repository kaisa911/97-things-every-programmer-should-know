# 重构之前

At some point every programmer will need to refactor existing code. But before you do so please think about the following, as this could save you and others a great deal of time (and pain):

每个程序员都会有需要重构现有代码的时候。但在这样做之前，请考虑以下几点，因为这可以为你和其他人节省大量的时间（和痛苦）：

- _The best approach for restructuring starts by taking stock of the existing codebase and the tests written against that code._ This will help you understand the strengths and weaknesses of the code as it currently stands, so you can ensure that you retain the strong points while avoiding the mistakes. We all think we can do better than the existing system... until we end up with something no better — or even worse — than the previous incarnation because we failed to learn from the existing system's mistakes.

- *重构的最佳方法是从评估现有的代码库和针对该代码编写的测试开始。*我们都认为自己可以做得比现有系统更好...直到我们最终得到的东西并不比以前的化身更好，甚至更糟，因为我们没能从现有系统的错误中吸取教训。

- _Avoid the temptation to rewrite everything._ It is best to reuse as much code as possible. No matter how ugly the code is, it has already been tested, reviewed, etc. Throwing away the old code — especially if it was in production — means that you are throwing away months (or years) of tested, battle-hardened code that may have had certain workarounds and bug fixes you aren't aware of. If you don't take this into account, the new code you write may end up showing the same mysterious bugs that were fixed in the old code. This will waste a lot of time, effort, and knowledge gained over the years.

- _避免重写一切的诱惑_ 尽可能多地重复使用代码是上策。无论代码有多难看，它都已经过测试、审查等。扔掉旧代码，尤其是生产中的旧代码，意味着你扔掉了数月（或数年）经过测试、实战磨练的代码，而这些代码中可能有你不知道的变通方法和错误修复。如果不考虑这一点，您编写的新代码最终可能会出现与旧代码中已修复的相同的神秘错误。这将浪费大量的时间、精力和多年积累的知识。

- _Many incremental changes are better than one massive change._ Incremental changes allows you to gauge the impact on the system more easily through feedback, such as from tests. It is no fun to see a hundred test failures after you make a change. This can lead to frustration and pressure that can in turn result in bad decisions. A couple of test failures is easy to deal with and provides a more manageable approach.

- _多次增量更改胜过一次大规模更改_ 通过测试等反馈，增量更改可以更容易地衡量对系统的影响。在进行变更后，看到上百次测试失败可不是件好玩的事。这会导致挫败感和压力，进而做出错误的决定。几次测试失败很容易处理，而且提供了一种更易于管理的方法。

- _After each iteration, it is important to ensure that the existing tests pass._ Add new tests if the existing tests are not sufficient to cover the changes you made. Do not throw away the tests from the old code without due consideration. On the surface some of these tests may not appear to be applicable to your new design, but it would be well worth the effort to dig deep down into the reasons why this particular test was added.

- _在每次迭代后，确保现有测试通过是很重要的。_ 如果现有测试不足以覆盖你所做的更改，则添加新的测试。如果现有的测试不足以覆盖你所做的更改，请添加新的测试。不要不加考虑地丢弃旧代码中的测试。从表面上看，有些测试可能并不适用于您的新设计，但如果能深入研究一下添加该测试的原因，那就非常值得了。

- _Personal preferences and ego shouldn't get in the way._ If something isn't broken, why fix it? That the style or the structure of the code does not meet your personal preference is not a valid reason for restructuring. Thinking you could do a better job than the previous programmer is not a valid reason either.

- _个人喜好和自我意识不应成为阻碍_ 如果东西没坏，为什么要修？代码的风格或结构不符合你的个人偏好并不能成为重组的正当理由。认为自己能比前任程序员做得更好也不是合理的理由。

- _New technology is insufficient reason to refactor._ One of the worst reasons to refactor is because the current code is way behind all the cool technology we have today, and we believe that a new language or framework can do things a lot more elegantly. Unless a cost–benefit analysis shows that a new language or framework will result in significant improvements in functionality, maintainability, or productivity, it is best to leave it as it is.

- *新技术不足以成为重构的理由。*重构的最糟糕理由之一就是当前的代码远远落后于当今所有的先进技术，而我们认为新的语言或框架可以更优雅地完成工作。除非成本效益分析表明，新的语言或框架能在功能、可维护性或生产率方面带来重大改进，否则最好还是保持原样。

- _Remember that humans make mistakes._ Restructuring will not always guarantee that the new code will be better — or even as good as — the previous attempt. I have seen and been a part of several failed restructuring attempts. It wasn't pretty, but it was human.

- _请记住，人都会犯错。_ 重组并不总能保证新代码会更好，甚至不如之前的尝试。我曾目睹并参与过几次失败的重组尝试。这并不美观，但这是人之常情。

by [Rajith Attapattu](http://programmer.97things.oreilly.com/wiki/index.php/Rajith_Attapattu)
