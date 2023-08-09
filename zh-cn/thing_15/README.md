# 理性编码

Trying to reason about software correctness by hand results in a formal proof that is longer than the code and is more likely to contain errors than the code. Automated tools are preferable, but not always possible. What follows describes a middle path: reasoning semi-formally about correctness.

手工推理软件的正确性会导致形式化证明比代码更长，而且比代码更容易出错。自动化工具是可取的，但并非总是可行。下面介绍的是一条中间道路：对正确性进行半形式化推理。

The underlying approach is to divide all the code under consideration into short sections — from a single line, such as a function call, to blocks of less than ten lines — and arguing about their correctness. The arguments need only be strong enough to convince your devil's advocate peer programmer.

其基本方法是将所有正在考虑的代码分成短小的部分--从单行（如函数调用）到少于十行的代码块--并对其正确性进行论证。论据只需足够有力，足以说服你的魔鬼代言人同行程序员即可。

A section should be chosen so that at each endpoint the *state of the program* (namely, the program counter and the values of all "living" objects) satisfies an easily described property, and that the functionality of that section (state transformation) is easy to describe as a single task — these will make reasoning simpler. Such endpoint properties generalize concepts like *precondition* and *postcondition* for functions, and *invariant* for loops and classes (with respect to their instances). Striving for sections to be as independent of one another as possible simplifies reasoning and is indispensable when these sections are to be modified.

应该选择这样一个部分：在每个端点，*程序的状态*（即程序计数器和所有 "活 "对象的值）都满足一个易于描述的属性，并且该部分的功能（状态转换）易于描述为一个任务--这些都会使推理变得更简单。这种端点属性概括了函数的*前条件*和*后条件*，以及循环和类的*不变*（相对于它们的实例）等概念。力求各部分尽可能相互独立，可以简化推理，在修改这些部分时也是不可或缺的。

Many of the coding practices that are well known (although perhaps less well followed) and considered 'good' make reasoning easier. Hence, just by intending to reason about your code, you already start thinking toward a better style and structure. Unsurprisingly, most of these practices can be checked by static code analyzers:

许多众所周知（尽管可能不太被遵守）并被认为是 "好 "的编码实践都能使推理变得更容易。因此，只要打算对代码进行推理，您就已经开始考虑采用更好的风格和结构。不出所料，静态代码分析器可以检查这些做法中的大多数：

- Avoid using goto statements, as they make remote sections highly interdependent.

- 避免使用 goto 语句，因为它们会使远程部分高度相互依赖。

- Avoid using modifiable global variables, as they make all sections that use them dependent.

- 避免使用可修改的全局变量，因为它们会使使用这些变量的所有部分相互依赖。

- Each variable should have the smallest possible scope. For example, a local object can be declared right before its first usage.

- 每个变量的作用域应尽可能小。例如，可以在首次使用前声明本地对象。

- Make objects *immutable* whenever relevant.

- 在相关情况下，使对象*不可变*。

- Make the code readable by using spacing, both horizontal and vertical. For example, aligning related structures and using an empty line to separate two sections.

- 通过使用横向和纵向间距来提高代码的可读性。例如，对齐相关结构，使用空行分隔两个部分。

- Make the code self-documenting by choosing descriptive (but relatively short) names for objects, types, functions, etc.

- 为对象、类型、函数等选择描述性（但相对简短）的名称，使代码具有自文档性。

- If you need a nested section, make it a function.

- 如果需要嵌套部分，就将其作为一个函数。

- Make your functions short and focused on a single task. The old *24-line limit* still applies. Although screen size and resolution have changed, nothing has changed in human cognition since the 1960s.

- 让你的函数简短并专注于一项任务。过去的*24 行限制*仍然适用。虽然屏幕尺寸和分辨率已经发生了变化，但自 20 世纪 60 年代以来，人类的认知能力并没有发生任何变化。

- Functions should have few parameters (four is a good upper bound). This does not restrict the data communicated to functions: Grouping related parameters into a single object benefits from *object invariants* and saves reasoning, such as their coherence and consistency.

- 函数的参数应该很少（4 个参数是一个很好的上限）。这并不限制与函数通信的数据： 将相关参数归类到一个对象中，可以从*对象不变式*中获益，并节省推理时间，例如它们的一致性和连贯性。

- More generally, each unit of code, from a block to a library, should have a *narrow interface*. Less communication reduces the reasoning required. This means that *getters* that return internal state are a liability — don't ask an object for information to work with. Instead, ask the object to do the work with the information it already has. In other words, *encapsulation* is all — and only — about *narrow interfaces*.

- 更一般地说，从代码块到库，每个代码单元都应该有一个*窄的接口*。减少交流可以减少推理。这意味着，返回内部状态的*getters*是一种负担--不要向对象索取信息来处理。相反，可以要求对象利用已有的信息来完成工作。换句话说，*封装*是*窄接口*的全部，也是唯一。

- In order to preserve class *invariants*, usage of *setters* should be discouraged, as *setters* tend to allow invariants that govern an object's state to be broken.

- 为了保持类的*不变性*，应避免使用*setters*，因为*setters*往往会破坏支配对象状态的不变性。

As well as reasoning about its correctness, arguing about your code gives you understanding of it. Communicate the insights you gain for everyone's benefit.

除了对代码的正确性进行推理外，对代码的争论还能加深对代码的理解。为了每个人的利益，请交流您的见解。

By [Yechiel Kimchi](http://programmer.97things.oreilly.com/wiki/index.php/Yechiel_Kimchi)
