# 谨慎选择您的工具

Modern applications are very rarely built from scratch. They are assembled using existing tools — components, libraries, and frameworks — for a number of good reasons:

现代应用程序很少是从头开始构建的。它们是使用现有的工具——组件、库和框架——来组装的，这有很多好处：

- Applications grow in size, complexity, and sophistication, while the time available to develop them grows shorter. It makes better use of developers' time and intelligence if they can concentrate on writing more business-domain code and less infrastructure code.

- 应用程序在大小、复杂度和精细度方面都在增长，而开发它们的时间却越来越短。如果开发者能够专注于编写更多的业务领域代码，而不是基础设施代码，那么他们的时间和智力就能得到更好的利用。

- Widely used components and frameworks are likely to have fewer bugs than the ones developed in-house.

- 广泛使用的组件和框架可能比内部开发的组件和框架有更少的 bug。

- There is a lot of high-quality software available on the web for free, which means lower development costs and greater likelihood of finding developers with the necessary interest and expertise.

- 网上有很多高质量的免费软件，这意味着更低的开发成本和更大的找到有兴趣和专业知识的开发者的可能性。

- Software production and maintenance is human-intensive work, so buying may be cheaper than building.

- 软件生产和维护是人力密集型的工作，所以购买可能比自己构建更便宜。

However, choosing the right mix of tools for your application can be a tricky business requiring some thought. In fact when making a choice, there are a few things you should keep in mind:

然而，为你的应用程序选择合适的工具组合可能是一件需要思考的棘手事情。事实上，在做出选择时，你应该记住以下几点：

- Different tools may rely on different assumptions about their context — e.g., surrounding infrastructure, control model, data model, communication protocols, etc. — which can lead to an architectural mismatch between the application and the tools. Such a mismatch leads to hacks and workarounds that will make the code more complex than necessary.

- 不同的工具可能依赖于不同的关于它们上下文的假设——例如，周围的基础设施、控制模型、数据模型、通信协议等——这可能导致应用程序和工具之间的架构不匹配。这种不匹配会导致一些黑客和变通方法，使得代码比必要的更复杂。

- Different tools have different lifecycles, and upgrading one of them may become an extremely difficult and time-consuming task since the new functionality, design changes, or even bug fixes may cause incompatibilities with the other tools. The greater the number tools the worse the problem can become.

- 不同的工具有不同的生命周期，升级其中一个可能会变成一项非常困难和耗时的任务，因为新功能、设计变化或甚至 bug 修复可能会导致与其他工具不兼容。工具越多，问题就可能越严重。

- Some tools require quite a bit of configuration, often by means of one or more XML files, which can grow out of control very quickly. The application may end up looking as if it was all written in XML plus a few odd lines of code in some programming language. The configurational complexity will make the application difficult to maintain and to extend.

- 一些工具需要相当多的配置，通常是通过一个或多个 XML 文件来实现，这些文件很快就会失控。应用程序可能最终看起来就像是全部用 XML 写的，再加上一些奇怪的代码行在某种编程语言中。配置复杂性会使得应用程序难以维护和扩展。

- Vendor lock-in occurs when code that depends heavily on specific vendor products ends up being constrained by them on several counts: maintainability, performances, ability to evolve, price, etc.

- 供应商锁定发生在严重依赖特定供应商产品的代码最终在几个方面受到它们的限制：可维护性、性能、能力、价格等。

- If you plan to use free software, you may discover that it's not so free after all. You may need to buy commercial support, which is not necessarily going to be cheap.

- 如果你打算使用免费软件，你可能会发现它并不是那么免费。你可能需要购买商业支持，这也不一定会很便宜。

- Licensing terms matter, even for free software. For example, in some companies it is not acceptable to use software licensed under the GNU license terms because of its viral nature — i.e., software developed with it must be distributed along with its source code.

- 许可条款很重要，即使对于免费软件也是如此。例如，在一些公司中，使用 GNU 许可条款授权的软件是不可接受的，因为它具有传染性——即，使用它开发的软件必须连同其源代码一起分发。

My personal strategy to mitigate these problems is to start small by using only the tools that are absolutely necessary. Usually the initial focus is on removing the need to engage in low-level infrastructure programming (and problems), e.g., by using some middleware instead of using raw sockets for distributed applications. And then add more if needed. I also tend to isolate the external tools from my business domain objects by means of interfaces and layering, so that I can change the tool if I have to with just a small amount of pain. A positive side effect of this approach is that I generally end up with a smaller application that uses fewer external tools than originally forecast.

我的个人策略是通过只使用绝对必要的工具来减轻这些问题。通常最初的重点是消除低级基础设施编程（和问题）的需要，例如，通过使用一些中间件来代替原始套接字进行分布式应用程序。然后根据需要添加更多。我也倾向于通过接口和分层来隔离外部工具和我的业务领域对象，这样我就可以在必要时更换工具，只需要承受一点点痛苦。这种方法的一个积极的副作用是，我通常最终会得到一个比最初预测的使用更少的外部工具的更小的应用程序。

By [Giovanni Asproni](http://programmer.97things.oreilly.com/wiki/index.php/Giovanni_Asproni)