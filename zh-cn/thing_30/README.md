# 不要重复自己

Of all the principles of programming, Don't Repeat Yourself (DRY) is perhaps one of the most fundamental. The principle was formulated by Andy Hunt and Dave Thomas in *The Pragmatic Programmer*, and underlies many other well-known software development best practices and design patterns. The developer who learns to recognize duplication, and understands how to eliminate it through appropriate practice and proper abstraction, can produce much cleaner code than one who continuously infects the application with unnecessary repetition.

在所有编程原则中，"不要重复自己"（DRY）可能是最基本的原则之一。安迪-亨特（Andy Hunt）和戴夫-托马斯（Dave Thomas）在《务实的程序员》（*The Pragmatic Programmer*）一书中提出了这一原则，它也是许多其他著名软件开发最佳实践和设计模式的基础。开发人员如果学会识别重复，并了解如何通过适当的实践和适当的抽象来消除重复，就能比那些不断用不必要的重复来感染应用程序的人编写出更简洁的代码。

Duplication is waste
重复就是浪费
---

Every line of code that goes into an application must be maintained, and is a potential source of future bugs. Duplication needlessly bloats the codebase, resulting in more opportunities for bugs and adding accidental complexity to the system. The bloat that duplication adds to the system also makes it more difficult for developers working with the system to fully understand the entire system, or to be certain that changes made in one location do not also need to be made in other places that duplicate the logic they are working on. DRY requires that "every piece of knowledge must have a single, unambiguous, authoritative representation within a system."

应用程序中的每一行代码都必须得到维护，这也是未来出现错误的潜在根源。不必要的重复会使代码库变得臃肿，从而增加出现错误的机会，并意外增加系统的复杂性。重复给系统带来的臃肿也会让开发人员更难完全理解整个系统，或者无法确定在一个地方做出的更改是否也需要在其他地方做出，从而重复了他们正在处理的逻辑。DRY 要求 "每一项知识在系统中都必须有一个单一、明确、权威的表示"。

Repetition in process calls for automation
流程中的重复需要自动化
---

Many processes in software development are repetitive and easily automated. The DRY principle applies in these contexts as well as in the source code of the application. Manual testing is slow, error-prone, and difficult to repeat, so automated test suites should be used, if possible. Integrating software can be time consuming and error-prone if done manually, so a build process should be run as frequently as possible, ideally with every check-in. Wherever painful manual processes exist that can be automated, they should be automated and standardized. The goal is to ensure there is only one way of accomplishing the task, and it is as painless as possible.

软件开发中的许多流程都是重复的，很容易实现自动化。DRY 原则适用于这些情况以及应用程序的源代码。手动测试速度慢、易出错且难以重复，因此应尽可能使用自动测试套件。手动集成软件既耗时又容易出错，因此应尽可能频繁地运行构建流程，最好是每次签入时都运行。只要存在可以自动化的痛苦手动流程，就应将其自动化和标准化。这样做的目的是确保只有一种方法可以完成任务，而且尽可能无痛。

Repetition in logic calls for abstraction
逻辑重复需要抽象
---

Repetition in logic can take many forms. Copy-and-paste *if-then* or *switch-case* logic is among the easiest to detect and correct. Many design patterns have the explicit goal of reducing or eliminating duplication in logic within an application. If an object typically requires several things to happen before it can be used, this can be accomplished with an Abstract Factory or a Factory Method. If an object has many possible variations in its behavior, these behaviors can be injected using the Strategy pattern rather than large *if-then* structures. In fact, the formulation of design patterns themselves is an attempt to reduce the duplication of effort required to solve common problems and discuss such solutions. In addition, DRY can be applied to structures, such as database schema, resulting in normalization.

逻辑中的重复有多种形式。复制粘贴*if-then*或*switch-case*逻辑是最容易发现和纠正的。许多设计模式的明确目标就是减少或消除应用程序中逻辑的重复。如果一个对象在使用前通常需要做几件事，那么可以通过抽象工厂或工厂方法来实现。如果一个对象的行为有许多可能的变化，则可以使用策略模式来注入这些行为，而不是使用大型的 *if-then* 结构。事实上，设计模式的制定本身就是为了减少解决常见问题和讨论这些解决方案所需的重复劳动。此外，DRY 还可应用于数据库模式等结构，从而实现规范化。

A Matter of principle
原则问题
---

Other software principles are also related to DRY. The Once and Only Once principle, which applies only to the functional behavior of code, can be thought of as a subset of DRY. The Open/Closed Principle, which states that "software entities should be open for extension, but closed for modification," only works in practice when DRY is followed. Likewise, the well-known Single Responsibility Principle requires that a class have "only one reason to change," relies on DRY.

其他软件原则也与 DRY 有关。仅适用于代码功能行为的 "一次且仅一次 "原则可视为 DRY 的一个子集。开放/封闭原则指出 "软件实体应开放用于扩展，但封闭用于修改"，只有在遵循 DRY 原则的情况下，该原则才能在实践中发挥作用。同样，众所周知的 "单一责任原则"（Single Responsibility Principle）要求一个类 "只有一个改变的理由"，这也依赖于 DRY。

When followed with regard to structure, logic, process, and function, the DRY principle provides fundamental guidance to software developers and aids the creation of simpler, more maintainable, higher-quality applications. While there are scenarios where repetition can be necessary to meet performance or other requirements (e.g., data denormalization in a database), it should be used only where it directly addresses an actual rather than an imagined problem.

在结构、逻辑、流程和功能方面遵循 DRY 原则，可为软件开发人员提供基本指导，有助于创建更简单、可维护性更强、质量更高的应用程序。虽然在某些情况下，为了满足性能或其他要求，重复是必要的（例如，数据库中的数据去规范化），但只有在直接解决实际问题而不是想象中的问题时，才应使用重复。

By [Steve Smith](http://programmer.97things.oreilly.com/wiki/index.php/Steve_Smith)