# 封装行为，而不仅仅是状态

In systems theory, containment is one of the most useful constructs when dealing with large and complex system structures. In the software industry the value of containment or encapsulation is well understood. Containment is supported by programming language constructs such as subroutines and functions, modules and packages, classes, and so on.

在系统理论中，封装是处理大型复杂系统结构时最有用的结构之一。在软件行业，遏制或封装的价值是众所周知的。子程序和函数、模块和包、类等编程语言结构支持封装。

Modules and packages address the larger scale needs for encapsulation, while classes, subroutines, and functions address the more fine-grained aspects of the matter. Over the years I have discovered that classes seem to be one of the hardest encapsulation constructs for developers to get right. It's not uncommon to find a class with a single 3000-line main method, or a class with only *set* and *get* methods for its primitive attributes. These examples demonstrate that the developers involved have not fully understood object-oriented thinking, having failed to take advantage of the power of objects as modeling constructs. For developers familiar with the terms POJO (Plain Old Java Object) and POCO (Plain Old C# Object or Plain Old CLR Object), this was the intent in going back to the basics of OO as a modeling paradigm — the objects are plain and simple, but not dumb.

模块和包可以满足更大规模的封装需求，而类、子程序和函数则可以满足更细粒度的封装需求。多年来，我发现类似乎是开发人员最难掌握的封装结构之一。一个类只有一个 3000 行的主方法，或者一个类的原始属性只有 *set* 和 *get* 方法，这种情况并不少见。这些例子表明，相关的开发人员还没有完全理解面向对象的思想，没有充分利用对象作为建模构造的强大功能。对于熟悉 POJO（Plain Old Java Object）和 POCO（Plain Old C# Object 或 Plain Old CLR Object）这两个术语的开发人员来说，这就是回归 OO 作为建模范例的基本原理--对象简单明了，但并不愚蠢。

An object encapsulates both state and behavior, where the behavior is defined by the actual state. Consider a door object. It has four states: closed, open, closing, opening. It provides two operations: open and close. Depending on the state, the open and close operations will behave differently. This inherent property of an object makes the design process conceptually simple. It boils down to two simple tasks: allocation and delegation of responsibility to the different objects including the inter-object interaction protocols.

对象封装了状态和行为，而行为是由实际状态定义的。请看一个门对象。它有四种状态：关闭、打开、关闭、打开。它提供两种操作：打开和关闭。根据状态的不同，打开和关闭操作的行为也不同。对象的这种固有属性使设计过程在概念上变得简单。它可以归结为两个简单的任务：向不同对象分配和授权责任，包括对象间的交互协议。

How this works in practice is best illustrated with an example. Let's say we have three classes: Customer, Order, and Item. A Customer object is the natural placeholder for the credit limit and credit validation rules. An Order object knows about its associated Customer, and its addItem operation delegates the actual credit check by calling `customer.validateCredit(item.price())`. If the postcondition for the method fails, an exception can be thrown and the purchase aborted.

举个例子最能说明这在实践中是如何运作的。假设我们有三个类： 客户、订单和物品。客户对象是信用额度和信用验证规则的自然占位符。订单对象知道其关联的客户，其 addItem 操作通过调用 `customer.validateCredit(item.price())`委托实际的信用检查。如果该方法的后置条件失败，就会抛出异常并中止购买。

Less experienced object oriented developers might decide to wrap all the business rules into an object very often referred to as `OrderManager` or `OrderService`. In these designs, `Order`, `Customer`, and `Item` are treated as little more than record types. All logic is factored out of the classes and tied together in one large, procedural method with a lot of internal *if-then-else* constructs. These methods are easily broken and are almost impossible to maintain. The reason? The encapsulation is broken.

经验较少的面向对象开发人员可能会决定将所有业务规则封装到一个对象中，通常称为 `OrderManager` 或 `OrderService`。在这些设计中，"订单"、"客户 "和 "项目 "被视为记录类型。所有逻辑都被从类中剥离出来，用一个大型的、带有大量内部*if-then-else*结构的过程式方法捆绑在一起。这些方法很容易被破坏，而且几乎无法维护。原因何在？封装被破坏了。

So in the end, don't break the encapsulation, and use the power of your programming language to maintain it.

因此，最终还是不要破坏封装，利用编程语言的强大功能来维护封装。

By [Einar Landre](http://programmer.97things.oreilly.com/wiki/index.php/Einar_Landre)