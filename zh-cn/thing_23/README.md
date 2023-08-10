# 特定领域语言

Whenever you listen to a discussion by experts in any domain, be it chess players, kindergarten teachers, or insurance agents, you'll notice that their vocabulary is quite different from everyday language. That's part of what domain-specific languages (DSLs) are about: A specific domain has a specialized vocabulary to describe the things that are particular to that domain.

每当你聆听任何领域的专家讨论时，无论是国际象棋选手、幼儿园教师还是保险代理人，你都会注意到他们的词汇与日常用语大相径庭。这就是特定领域语言（DSL）的部分意义所在： 特定领域有专门的词汇来描述该领域特有的事物。

In the world of software, DSLs are about executable expressions in a language specific to a domain with limited vocabulary and grammar that is readable, understandable, and — hopefully — writable by domain experts. DSLs targeted at software developers or scientists have been around for a long time. For example, the Unix 'little languages' found in configuration files and the languages created with the power of LISP macros are some of the older examples.

在软件世界中，DSL 是指使用特定领域语言的可执行表达式，这种语言具有有限的词汇和语法，可读、可理解，而且--希望--可由领域专家编写。针对软件开发人员或科学家的 DSL 由来已久。例如，配置文件中的 Unix "小语言 "和利用 LISP 宏的强大功能创建的语言就是一些较早的例子。

DSLs are commonly classified as either _internal_ or _external_:

DSL 通常分为*内部*和*外部*两种：

- **Internal DSLs** are written in a general purpose programming language whose syntax has been bent to look much more like natural language. This is easier for languages that offer more syntactic sugar and formatting possibilities (e.g., Ruby and Scala) than it is for others that do not (e.g., Java). Most internal DSLs wrap existing APIs, libraries, or business code and provide a wrapper for less mind-bending access to the functionality. They are directly executable by just running them. Depending on the implementation and the domain, they are used to build data structures, define dependencies, run processes or tasks, communicate with other systems, or validate user input. The syntax of an internal DSL is constrained by the host language. There are many patterns — e.g., expression builder, method chaining, and annotation — that can help you to bend the host language to your DSL. If the host language doesn't require recompilation, an internal DSL can be developed quite quickly working side by side with a domain expert.

- **内部 DSL**是用一种通用编程语言编写的，其语法经过修改，看起来更像自然语言。对于提供更多语法糖和格式化可能性的语言（如 Ruby 和 Scala）来说，这比其他不提供语法糖和格式化可能性的语言（如 Java）更容易。大多数内部 DSL 都对现有的 API、库或业务代码进行了封装，并提供了一个封装器，使用户能够以较低的难度访问这些功能。它们只需运行即可直接执行。根据实现和领域的不同，它们可用于构建数据结构、定义依赖关系、运行进程或任务、与其他系统通信或验证用户输入。内部 DSL 的语法受到宿主语言的限制。有许多模式（如表达式生成器、方法链和注解）可以帮助您使宿主语言适应您的 DSL。如果宿主语言不需要重新编译，就可以与领域专家并肩工作，很快开发出内部 DSL。

- **External DSLs** are textual or graphical expressions of the language — although textual DSLs tend to be more common than graphical ones. Textual expressions can be processed by a tool chain that includes lexer, parser, model transformer, generators, and any other type of post-processing. External DSLs are mostly read into internal models which form the basis for further processing. It is helpful to define a grammar (e.g., in EBNF). A grammar provides the starting point for generating parts of the tool chain (e.g., editor, visualizer, parser generator). For simple DSLs, a handmade parser may be sufficient — using, for instance, regular expressions. Custom parsers can become unwieldy if too much is asked of them, so it makes sense to look at tools designed specifically for working with language grammars and DSLs — e.g., openArchitectureWare, ANTlr, SableCC, AndroMDA. Defining external DSLs as XML dialects is also quite common, although readability is often an issue — especially for non-technical readers.

- **外部 DSL** 是语言的文本或图形表达方式，不过文本 DSL 往往比图形 DSL 更为常见。文本表达式可以通过工具链进行处理，其中包括词法、解析器、模型转换器、生成器和任何其他类型的后处理。外部 DSL 大多被读入内部模型，而内部模型是进一步处理的基础。定义语法（如 EBNF）是很有帮助的。语法为生成工具链的各个部分（如编辑器、可视化器、解析器生成器）提供了起点。对于简单的 DSL，使用正则表达式等手工制作的解析器可能就足够了。如果对自定义解析器的要求过高，它们就会变得臃肿不堪，因此，使用专门为处理语言语法和 DSL 而设计的工具（如 openArchitectureWare、ANTlr、SableCC、AndroMDA）是明智之举。将外部 DSL 定义为 XML 方言也很常见，不过可读性往往是个问题，尤其是对于非技术读者而言。

You must always take the target audience of your DSL into account. Are they developers, managers, business customers, or end users? You have to adapt the technical level of the language, the available tools, syntax help (e.g., intellisense), early validation, visualization, and representation to the intended audience. By hiding technical details, DSLs can empower users by giving them the ability to adapt systems to their needs without requiring the help of developers. It can also speed up development because of the potential distribution of work after the initial language framework is in place. The language can be evolved gradually. There are also different migration paths for existing expressions and grammars available.

您必须始终考虑 DSL 的目标受众。他们是开发人员、管理人员、企业客户还是最终用户？您必须使语言的技术水平、可用工具、语法帮助（如智能感知）、早期验证、可视化和表现形式与目标受众相适应。通过隐藏技术细节，DSL 可以增强用户的能力，让他们能够根据自己的需要调整系统，而无需开发人员的帮助。它还可以加快开发速度，因为在初始语言框架就位后，工作可能会被分配。语言可以逐步发展。现有的表达式和语法也有不同的迁移路径。

By [Michael Hunger](http://programmer.97things.oreilly.com/wiki/index.php/Michael_Hunger)
