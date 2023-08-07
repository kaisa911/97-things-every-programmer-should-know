# 应用函数式编程原则

Functional programming has recently enjoyed renewed interest from the mainstream programming community. Part of the reason is because _emergent properties_ of the functional paradigm are well positioned to address the challenges posed by our industry's shift toward multi-core. However, while that is certainly an important application, it is not the reason this piece admonishes you to _know thy functional programming_.

函数式编程最近受到主流编程社区的重新关注。函数式范式的*新兴属性*之一是其良好的应对我们行业向多核挑战的位置。然而，虽然这确实是一个重要的应用，但这并不是本文告诫你*了解你的函数式编程*的原因。

Mastery of the functional programming paradigm can greatly improve the quality of the code you write in other contexts. If you deeply understand and apply the functional paradigm, your designs will exhibit a much higher degree of _referential transparency_.

掌握函数式编程范式可以极大地提高你在其他上下文中编写代码的质量。如果你深入理解并应用函数式范式，你的设计将表现出更高程度的*引用透明度*。

Referential transparency is a very desirable property: It implies that functions consistently yield the same results given the same input, irrespective of where and when they are invoked. That is, function evaluation depends less — ideally, not at all — on the side effects of mutable state.

引用透明度是一个非常理想的属性：它意味着函数在给定相同输入的情况下始终产生相同的结果，无论它们何时何地被调用。也就是说，函数求值依赖于可变状态的副作用越少越好，理想情况下根本不依赖。

A leading cause of defects in imperative code is attributable to mutable variables. Everyone reading this will have investigated why some value is not as expected in a particular situation. Visibility semantics can help to mitigate these insidious defects, or at least to drastically narrow down their location, but their true culprit may in fact be the providence of designs that employ inordinate mutability.

命令式代码中缺陷的主要原因之一归因于可变变量。阅读本文的每个人都会调查为什么在特定情况下某个值不如预期。可见性语义可以帮助减轻这些隐蔽缺陷，或者至少大大缩小它们的位置，但它们真正的罪魁祸首可能实际上是采用过多可变性的设计。

And we certainly don't get much help from industry in this regard. Introductions to object orientation tacitly promote such design, because they often show examples composed of graphs of relatively long-lived objects that happily call mutator methods on each other, which can be dangerous. However, with astute test-driven design, particularly when being sure to ["Mock Roles, not Objects"](http://www.jmock.org/oopsla2004.pdf), unnecessary mutability can be designed away.

在这方面，我们当然没有得到行业方面的太多帮助。面向对象导论暗示了这种设计，因为它们经常展示由相对长寿对象组成的图形示例，这些对象愉快地互相调用 mutator 方法，这可能是危险的。然而，通过敏锐的测试驱动设计，特别是在确保["模拟角色而不是对象"](http://www.jmock.org/oopsla2004.pdf)时，可以设计掉不必要的可变性。

The net result is a design that typically has better responsibility allocation with more numerous, smaller functions that act on arguments passed into them, rather than referencing mutable member variables. There will be fewer defects, and furthermore they will often be simpler to debug, because it is easier to locate where a rogue value is introduced in these designs than to otherwise deduce the particular context that results in an erroneous assignment. This adds up to a much higher degree of referential transparency, and positively nothing will get these ideas as deeply into your bones as learning a functional programming language, where this model of computation is the norm.

最终结果是一个设计，通常具有更好的责任分配和更多、更小的函数来处理传递给它们的参数，而不是引用可变成员变量。缺陷将更少，而且它们通常更容易调试，因为在这些设计中定位流氓值的引入位置比推断导致错误赋值的特定上下文要容易得多。这加起来就是更高程度的引用透明度，没有什么比学习函数式编程语言更能让这些思想深入人心了，因为这种计算模型是标准。

Of course, this approach is not optimal in all situations. For example, in object-oriented systems this style often yields better results with domain model development (i.e., where collaborations serve to break down the complexity of business rules) than with user-interface development.

当然，在所有情况下，这种方法都不是最优的。例如，在面向对象系统中，这种风格通常在域模型开发（即协作用于分解业务规则的复杂性）方面比用户界面开发产生更好的结果。

Master the functional programming paradigm so you are able to judiciously apply the lessons learned to other domains. Your object systems (for one) will resonate with referential transparency goodness and be much closer to their functional counterparts than many would have you believe. In fact, some would even assert that the apex of functional programming and object orientation are _merely a reflection of each other_, a form of computational yin and yang.

掌握函数式编程范式，以便能够明智地将所学到的课程应用于其他领域。你的对象系统（其中之一）将共鸣于引用透明度的好处，并且比许多人认为的更接近它们的函数式对应物。事实上，有些人甚至会断言，函数式编程和面向对象编程的顶峰只是彼此的反映，一种计算阴阳。

作者：[Edward Garson](http://programmer.97things.oreilly.com/wiki/index.php/Edward_Garson)
