# 童子军规则

The Boy Scouts have a rule: "Always leave the campground cleaner than you found it." If you find a mess on the ground, you clean it up regardless of who might have made the mess. You intentionally improve the environment for the next group of campers. Actually the original form of that rule, written by Robert Stephenson Smyth Baden-Powell, the father of scouting, was "Try and leave this world a little better than you found it."

童子军有一个规则：“总是把营地比你发现的时候更干净地留下。”如果你在地上发现一团乱，你就要把它清理干净，不管是谁制造的乱。你有意识地改善了下一批露营者的环境。实际上，这个规则的原始形式，是由童子军之父罗伯特·斯蒂文森·斯密斯·鲍登-鲍威尔写的：“试着把这个世界比你发现的时候留得更好一些。”

What if we followed a similar rule in our code: "Always check a module in cleaner than when you checked it out." No matter who the original author was, what if we always made some effort, no matter how small, to improve the module. What would be the result?

如果我们在我们的代码中遵循类似的规则：“总是把一个模块比你检出的时候更干净地检入。”不管原作者是谁，如果我们总是做一些努力，不管多小，来改进模块。结果会怎样呢？

I think if we all followed that simple rule, we'd see the end of the relentless deterioration of our software systems. Instead, our systems would gradually get better and better as they evolved. We'd also see *teams* caring for the system as a whole, rather than just individuals caring for their own small little part.

我认为，如果我们都遵循这个简单的规则，我们就会看到我们软件系统不断恶化的终结。相反，我们的系统会随着演化而逐渐变得更好。我们也会看到团队关心整个系统，而不仅仅是个人关心自己的一小部分。

I don't think this rule is too much to ask. You don't have to make every module perfect before you check it in. You simply have to make it a *little bit better* than when you checked it out. Of course, this means that any code you *add* to a module must be clean. It also means that you clean up at least one other thing before you check the module back in. You might simply improve the name of one variable, or split one long function into two smaller functions. You might break a circular dependency, or add an interface to decouple policy from detail.

我不认为这个规则要求太多。你不必在检入之前把每个模块都做得完美。你只需要把它比你检出的时候稍微好一点。当然，这意味着你添加到模块中的任何代码都必须是干净的。这也意味着你在检入模块之前至少要清理一件其他的事情。你可能只是改进一个变量的名字，或者把一个长函数分成两个小函数。你可能打破一个循环依赖，或者添加一个接口来解耦策略和细节。

Frankly, this just sounds like common decency to me — like washing your hands after you use the restroom, or putting your trash in the bin instead of dropping it on the floor. Indeed the act of leaving a mess in the code should be as socially unacceptable as *littering*. It should be something that *just isn't done*.

坦白地说，这对我来说只是常识——就像上完厕所后洗手，或者把垃圾放在垃圾桶里而不是扔在地上一样。事实上，在代码中留下一团乱应该和乱扔垃圾一样社会不可接受。它应该是一件不该做的事情。

But it's more than that. Caring for our own code is one thing. Caring for the team's code is quite another. Teams help each other, and clean up after each other. They follow the Boy Scout rule because it's good for everyone, not just good for themselves.

但它不仅仅是这样。关心自己的代码是一回事。关心团队的代码又是另一回事。团队互相帮助，互相清理。他们遵循童子军规则，因为这对每个人都有好处，而不仅仅对自己有好处。

by [Uncle Bob](http://programmer.97things.oreilly.com/wiki/index.php/Uncle_Bob)