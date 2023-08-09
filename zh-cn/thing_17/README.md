# 只注释代码不能说的内容

The difference between theory and practice is greater in practice than it is in theory — an observation that certainly applies to comments. In theory, the general idea of commenting code sounds like a worthy one: Offer the reader detail, an explanation of what's going on. What could be more helpful than being helpful? In practice, however, comments often become a blight. As with any other form of writing, there is a skill to writing good comments. Much of the skill is in knowing when not to write them.

理论与实践的差异在实践中比在理论中更大--这一观点当然也适用于注释。从理论上讲，注释代码的总体思路听起来很有价值： 为读者提供细节，解释发生了什么。还有什么比提供帮助更有用的呢？然而，在实践中，注释往往成为一种缺陷。与任何其他形式的写作一样，写好注释也是有技巧的。其中很大一部分技巧在于知道何时不写注释。

When code is ill-formed, compilers, interpreters, and other tools will be sure to object. If the code is in some way functionally incorrect, reviews, static analysis, tests, and day-to-day use in a production environment will flush most bugs out. But what about comments? In The *Elements of Programming Style* Kernighan and Plauger noted that "a comment is of zero (or negative) value if it is wrong." And yet such comments often litter and survive in a code base in a way that coding errors never could. They provide a constant source of distraction and misinformation, a subtle but constant drag on a programmer's thinking.

如果代码不规范，编译器、解释器和其他工具肯定会反对。如果代码在某些方面存在功能错误，审查、静态分析、测试以及在生产环境中的日常使用将清除大部分错误。那么注释呢？Kernighan 和 Plauger 在《编程风格要素》（The *Elements of Programming Style* ）一书中指出，"如果注释是错误的，那么它的价值就是零（或负）"。然而，这些注释却常常在代码库中随处可见，并以一种编码错误永远无法企及的方式存活下来。它们不断地分散程序员的注意力，提供错误信息，潜移默化地拖累程序员的思维。

What of comments that are not technically wrong, but add no value to the code? Such comments are noise. Comments that parrot the code offer nothing extra to the reader — stating something once in code and again in natural language does not make it any truer or more real. Commented-out code is not executable code, so it has no useful effect for either reader or runtime. It also becomes stale very quickly. Version-related comments and commented-out code try to address questions of versioning and history. These questions have already been answered (far more effectively) by version control tools.

那么，那些技术上没有错误，但对代码没有任何价值的注释呢？这些注释就是噪音。照搬代码的注释不会给读者带来任何额外的东西--用代码和自然语言各说一遍并不会让代码变得更真实或更现实。注释代码不是可执行代码，因此对读者和运行时都没有任何作用。它也会很快变得陈旧。版本相关注释和注释代码试图解决版本和历史问题。版本控制工具已经回答了这些问题（更有效）。

A prevalence of noisy comments and incorrect comments in a code base encourage programmers to ignore all comments, either by skipping past them or by taking active measures to hide them. Programmers are resourceful and will route around anything perceived to be damage: folding comments up; switching coloring scheme so that comments and the background are the same color; scripting to filter out comments. To save a code base from such misapplications of programmer ingenuity, and to reduce the risk of overlooking any comments of genuine value, comments should be treated as if they were code. Each comment should add some value for the reader, otherwise it is waste that should be removed or rewritten.

代码库中普遍存在的嘈杂注释和错误注释会鼓励程序员忽略所有注释，要么跳过它们，要么采取积极措施隐藏它们。程序员是机智的，他们会绕过任何被认为是破坏的东西：将注释折叠起来；切换着色方案，使注释和背景颜色相同；用脚本过滤掉注释。为了使代码库免受程序员聪明才智的误用，并降低忽略任何真正有价值注释的风险，应将注释当作代码来处理。每条注释都应为读者增加一些价值，否则就是废物，应予以删除或重写。

What then qualifies as value? Comments should say something code does not and cannot say. A comment explaining what a piece of code should already say is an invitation to change code structure or coding conventions so the code speaks for itself. Instead of compensating for poor method or class names, rename them. Instead of commenting sections in long functions, extract smaller functions whose names capture the former sections' intent. Try to express as much as possible through code. Any shortfall between what you can express in code and what you would like to express in total becomes a plausible candidate for a useful comment. Comment what the code cannot say, not simply what it does not say.

那么怎样才算有价值呢？注释应该说出代码没有也无法说出的东西。注释解释了一段代码本应表达的内容，这就要求改变代码结构或编码习惯，让代码自己说话。与其为糟糕的方法或类名做补偿，不如重新命名它们。与其注释长函数中的部分，不如提取更小的函数，这些函数的名称可以捕捉到前部分的意图。尽量通过代码来表达。你能用代码表达的内容与你想表达的内容之间的任何不足，都有可能成为有用注释的候选对象。注释代码不能表达的内容，而不仅仅是代码没有表达的内容。

By [Kevlin Henney](http://programmer.97things.oreilly.com/wiki/index.php/Kevlin_Henney)