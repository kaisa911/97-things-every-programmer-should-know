# 代码即设计

Imagine waking up tomorrow and learning the construction industry has made the breakthrough of the century. Millions of cheap, incredibly fast robots can fabricate materials out of thin air, have a near-zero power cost, and can repair themselves. And it gets better: Given an unambiguous blueprint for a construction project, the robots can build it without human intervention, all at negligible cost.

想象一下，明天一觉醒来，建筑业已经取得了世纪性的突破。数百万廉价、速度惊人的机器人可以凭空制造材料，动力成本几乎为零，还能自我修复。还有更好的： 只要有一个明确的建筑项目蓝图，机器人就能在没有人工干预的情况下建造它，而所有成本都可以忽略不计。

One can imagine the impact on the construction industry, but what would happen upstream? How would the behavior of architects and designers change if construction costs were negligible? Today, physical and computer models are built and rigorously tested before investing in construction. Would we bother if the construction was essentially free? If a design collapses, no big deal — just find out what went wrong and have our magical robots build another one. There are further implications. With models obsolete, unfinished designs evolve by repeatedly building and improving upon an approximation of the end goal. A casual observer may have trouble distinguishing an unfinished design from a finished product.

我们可以想象这对建筑业的影响，但上游会发生什么呢？如果建筑成本可以忽略不计，建筑师和设计师的行为会发生怎样的变化？如今，在投资建设之前，我们都会建立物理和计算机模型，并对其进行严格测试。如果建筑基本上是免费的，我们还会这么做吗？如果设计失败了，没什么大不了的，只要找出问题所在，让我们神奇的机器人再造一个就可以了。还有更多的影响。由于模型已经过时，未完成的设计会通过反复建造和改进最终目标的近似值而不断发展。旁观者可能很难区分未完成的设计和已完成的产品。

Our ability to predict time lines will fade away. Construction costs are more easily calculated than design costs — we know the approximate cost of installing a girder, and how many girders we need. As predictable tasks shrink toward zero, the less predictable design time starts to dominate. Results are produced more quickly, but reliable time lines slip away.

我们预测时间线的能力将逐渐消失。施工成本比设计成本更容易计算--我们知道安装一根大梁的大致成本，也知道我们需要多少根大梁。随着可预测的任务逐渐趋于零，可预测性较低的设计时间开始占据主导地位。结果是更快地产生了，但可靠的时间线却在缩短。

Of course, the pressures of a competitive economy still apply. With construction costs eliminated, a company that can quickly complete a design gains an edge in the market. Getting design done fast becomes the central push of engineering firms. Inevitably, someone not deeply familiar with the design will see an unvalidated version, see the market advantage of releasing early, and say "This looks good enough."

当然，经济竞争的压力依然存在。随着建筑成本的降低，能够快速完成设计的公司将在市场上获得优势。快速完成设计成为工程公司的核心推动力。不可避免的是，不熟悉设计的人会看到未经验证的版本，看到提前发布的市场优势，然后说："这看起来足够好了"。

Some life-or-death projects will be more diligent, but in many cases consumers learn to suffer through the incomplete design. Companies can always send out our magic robots to 'patch' the broken buildings and vehicles they sell. All of this points to a startlingly counterintuitive conclusion: Our sole premise was a dramatic reduction in construction costs, with the result that _quality got worse_.

有些生死攸关的项目会更用心，但在很多情况下，消费者要学会忍受不完整的设计。公司可以随时派出我们的神奇机器人来 "修补 "他们出售的破损建筑和车辆。所有这些都指向一个惊人的反直觉结论： 我们唯一的前提是大幅降低建筑成本，结果是*质量变差了*。

It shouldn't surprise us the above story has played out in software. If we accept that code is design — a creative process rather than a mechanical one — the _software crisis_ is explained. We now have a _design crisis_: The demand for quality, validated designs exceeds our capacity to create them. The pressure to use incomplete design is strong.

上述故事在软件领域的上演并不让我们感到意外。如果我们承认代码就是设计--一个创造性的过程，而不是一个机械的过程，那么*软件危机*就可以解释了。我们现在面临的是一场*设计危机*： 对高质量、经过验证的设计的需求超过了我们的创造能力。使用不完整设计的压力很大。

Fortunately, this model also offers clues on how we can get better. Physical simulations equate to automated testing; software design isn't complete until it is validated with a brutal battery of tests. To make such tests more effective we are finding ways to rein in the huge state space of large systems. Improved languages and design practices give us hope. Finally, there is one inescapable fact: Great designs are produced by great designers dedicating themselves to the mastery of their craft. Code is no different.

幸运的是，这个模型也为我们如何改进提供了线索。物理模拟等同于自动测试；软件设计在通过一系列严酷的测试验证后才算完成。为了使这些测试更加有效，我们正在想方设法控制大型系统的巨大状态空间。语言和设计实践的改进给我们带来了希望。最后，还有一个无法回避的事实：伟大的设计都是由伟大的设计师通过精湛的技艺创造出来的。代码也不例外。

By [Ryan Brush](http://programmer.97things.oreilly.com/wiki/index.php/Ryan_Brush)
