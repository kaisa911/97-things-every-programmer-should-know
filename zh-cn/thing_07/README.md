# 当心分享

It was my first project at the company. I'd just finished my degree and was anxious to prove myself, staying late every day going through the existing code. As I worked through my first feature I took extra care to put in place everything I had learned — commenting, logging, pulling out shared code into libraries where possible, the works. The code review that I had felt so ready for came as a rude awakening — reuse was frowned upon!

这是我在公司的第一个项目。我刚刚完成学业，急于证明自己的能力，每天都加班到很晚，检查现有的代码。在完成我的第一个功能时，我格外小心，把我学到的所有知识都用上了--注释、日志、尽可能把共享代码拉到库里，等等。代码审查让我大吃一惊--重用代码是不被允许的！

How could this be? All through college reuse was held up as the epitome of quality software engineering. All the articles I had read, the textbooks, the seasoned software professionals who taught me. Was it all wrong?

怎么会这样？在大学期间，重用一直被视为高质量软件工程的缩影。我读过的所有文章、教科书、经验丰富的软件专家都教过我。难道这一切都错了吗？

It turns out that I was missing something critical.

事实证明，我缺少了一些关键的东西。

Context.

上下文。

The fact that two wildly different parts of the system performed some logic in the same way meant less than I thought. Up until I had pulled out those libraries of shared code, these parts were not dependent on each other. Each could evolve independently. Each could change its logic to suit the needs of the system's changing business environment. Those four lines of similar code were accidental — a temporal anomaly, a coincidence. That is, until I came along.

事实上，系统中两个完全不同的部分以相同的方式执行某些逻辑，并没有我想象的那么重要。在我调出这些共享代码库之前，这些部分并不相互依赖。每个部分都可以独立发展。每个部分都可以改变其逻辑，以适应系统不断变化的业务环境的需要。这四行相似的代码是偶然的--一种时间上的反常，一种巧合。直到我的出现。

The libraries of shared code I created tied the shoelaces of each foot to each other. Steps by one business domain could not be made without first synchronizing with the other. Maintenance costs in those independent functions used to be negligible, but the common library required an order of magnitude more testing.

我创建的共享代码库将每只脚的鞋带绑在了一起。如果不与另一个业务领域同步，一个业务领域就无法前进。过去，这些独立功能的维护成本可以忽略不计，但共用库需要的测试量却要高出一个数量级。

While I'd decreased the absolute number of lines of code in the system, I had increased the number of dependencies. The context of these dependencies is critical — had they been localized, it may have been justified and had some positive value. When these dependencies aren't held in check, their tendrils entangle the larger concerns of the system even though the code itself looks just fine.

虽然我减少了系统中代码的绝对行数，但却增加了依赖关系的数量。这些依赖关系的上下文至关重要--如果这些依赖关系是本地化的，那么它可能是合理的，并具有一定的积极价值。如果不对这些依赖性加以控制，即使代码本身看起来没有问题，它们的卷须也会纠缠系统中更大的问题。

These mistakes are insidious in that, at their core, they sound like a good idea. When applied in the right context, these techniques are valuable. In the wrong context, they increase cost rather than value. When coming into an existing code base with no knowledge of the context where the various parts will be used, I'm much more careful these days about what is shared.

这些错误很隐蔽，因为它们的核心听起来是个好主意。在正确的情况下，这些技术是有价值的。在错误的情况下，它们增加的是成本而不是价值。当我进入一个现有的代码库，却不知道各个部分的使用环境时，我现在对共享的内容会更加谨慎。

Beware the share. Check your context. Only then, proceed.

当心共享。检查上下文。只有这样，才能继续。

By [Udi Dahan](http://programmer.97things.oreilly.com/wiki/index.php/Udi_Dahan)
