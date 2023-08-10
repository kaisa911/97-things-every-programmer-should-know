# 区分业务例外与技术例外

There are basically two reasons that things go wrong at runtime: technical problems that prevent us from using the application and business logic that prevents us from misusing the application. Most modern languages, such as LISP, Java, Smalltalk, and C#, use exceptions to signal both these situations. However, the two situations are so different that they should be carefully held apart. It is a potential source of confusion to represent them both using the same exception hierarchy, not to mention the same exception class.

运行时出错基本上有两个原因：技术问题导致我们无法使用应用程序；业务逻辑导致我们无法滥用应用程序。大多数现代语言，如 LISP、Java、Smalltalk 和 C#，都使用异常来提示这两种情况。然而，这两种情况是截然不同的，因此应小心区分开来。使用相同的异常层次结构来表示这两种情况可能会造成混乱，更不用说使用相同的异常类了。

An unresolvable technical problem can occur when there is a programming error. For example, if you try to access element 83 from an array of size 17, then the program is clearly off track, and some exception should result. The subtler version is calling some library code with inappropriate arguments, causing the same situation on the inside of the library.

当出现编程错误时，可能会出现无法解决的技术问题。例如，如果你试图从一个大小为 17 的数组中访问元素 83，那么程序显然偏离了轨道，应该会产生一些异常。更微妙的情况是使用不恰当的参数调用某些库代码，从而导致库内部出现同样的情况。

It would be a mistake to attempt to resolve these situations you caused yourself. Instead we let the exception bubble up to the highest architectural level and let some general exception-handling mechanism do what it can to ensure the system is in a safe state, such as rolling back a transaction, logging and alerting administration, and reporting back (politely) to the user.

试图解决这些自己造成的情况是错误的。相反，我们应该让异常上升到最高架构层，让一些通用的异常处理机制尽其所能确保系统处于安全状态，例如回滚事务、记录并警告管理部门，以及（礼貌地）向用户报告。

A variant of this situation is when you are in the "library situation" and a caller has broken the contract of your method, e.g., passing a totally bizarre argument or not having a dependent object set up properly. This is on a par with accessing 83rd element from 17: the caller should have checked; not doing so is a programmer error on the client side. The proper response is to throw a technical exception.

这种情况的一个变种是，当你处于 "库情况 "中，而调用者破坏了你的方法的契约，例如，传递了一个完全奇怪的参数或没有正确设置依赖对象。这种情况与访问第 17 个元素中的第 83 个元素一样：调用者本应进行检查；而没有进行检查则是客户端程序员的错误。正确的应对方法是抛出技术异常。

A different, but still technical, situation is when the program cannot proceed because of a problem in the execution environment, such as an unresponsive database. In this situation you must assume that the infrastructure did what it could to resolve the situation — repairing connections and retrying a reasonable number of times — and failed. Even if the cause is different, the situation for the calling code is similar: there is little it can do about it. So, we signal the situation through an exception that we let bubble up to the general exception handling mechanism.

另一种不同但仍属于技术性的情况是，由于执行环境出现问题（如数据库无响应）而导致程序无法继续执行。在这种情况下，你必须假设基础架构已经尽其所能来解决这种情况--修复连接并重试了合理的次数--但还是失败了。即使原因不同，调用代码的情况也是相似的：它对此无能为力。因此，我们通过一个异常来提示这种情况，并让它上升到一般的异常处理机制。

In contrast to these, we have the situation where you cannot complete the call for a domain-logical reason. In this case we have encountered a situation that is an exception, i.e., unusual and undesirable, but not bizarre or programmatically in error. For example, if I try to withdraw money from an account with insufficient funds. In other words, this kind of situation is a part of the contract, and throwing an exception is just an _alternative return path_ that is part of the model and that the client should be aware of and be prepared to handle. For these situations it is appropriate to create a specific exception or a separate exception hierarchy so that the client can handle the situation on its own terms.

与此相反，我们会遇到由于领域逻辑原因而无法完成调用的情况。在这种情况下，我们遇到的是异常情况，即不寻常、不可取的情况，但并不奇怪，也不是程序上的错误。例如，我试图从一个资金不足的账户中取款。换句话说，这种情况是合同的一部分，而抛出异常只是一种*替代返回路径*，是模型的一部分，客户应该知道并准备处理。对于这些情况，创建一个特定的异常或单独的异常层次结构是合适的，这样客户就可以根据自己的条件来处理这种情况。

Mixing technical exceptions and business exceptions in the same hierarchy blurs the distinction and confuses the caller about what the method contract is, what conditions it is required to ensure before calling, and what situations it is supposed to handle. Separating the cases gives clarity and increases the chances that technical exceptions will be handled by some application framework, while the business domain exceptions actually are considered and handled by the client code.

将技术异常和业务异常混放在同一个层次结构中会模糊两者的区别，使调用者不清楚方法契约是什么，调用前需要确保哪些条件，以及应该处理哪些情况。将两种情况分开会使情况更加清晰，并增加技术异常由某些应用程序框架处理的机会，而业务领域的异常实际上是由客户端代码考虑和处理的。

By [Dan Bergh Johnsson](http://programmer.97things.oreilly.com/wiki/index.php/Dan_Bergh_Johnsson)
