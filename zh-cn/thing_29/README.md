# 不要依赖 "神奇发生在这里"

If you look at any activity, process, or discipline from far enough away it looks simple. Managers with no experience of development think what programmers do is simple and programmers with no experience of management think the same of what managers do.

如果你从足够远的地方观察任何活动、流程或学科，它看起来都很简单。没有开发经验的管理者认为程序员的工作很简单，没有管理经验的程序员也认为管理者的工作很简单。

Programming is something some people do — some of the time. And the hard part — the thinking — is the least visible and least appreciated by the uninitiated. There have been many attempts to remove the need for this skilled thinking over the decades. One of the earliest and most memorable is the effort by Grace Hopper to make programming languages less cryptic — which some accounts predicted would remove the need for specialist programmers. The result (COBOL) has contributed to the income of many specialist programmers over subsequent decades.

编程是某些人在某些时候做的事情。而最难的部分--思考--是最不显眼的，也是最不为外行所欣赏的。几十年来，有许多人试图消除对这种熟练思维的需求。格蕾丝-霍珀（Grace Hopper）为减少编程语言的神秘性所做的努力是最早和最令人难忘的尝试之一，有些人预测这将消除对专业程序员的需求。其结果（COBOL）在随后的几十年里为许多专业程序员带来了收入。

The persistent vision that software development can be simplified by removing programming is, to the programmer who understands what is involved, obviously naïve. But the mental process that leads to this mistake is part of human nature and programmers are just as prone to making it as everyone else.

对于了解其中含义的程序员来说，取消编程就能简化软件开发的顽固想法显然是幼稚的。但导致这种错误的心理过程是人性的一部分，程序员和其他人一样容易犯这种错误。

On any project there are likely many things that an individual programmer doesn't get actively involved in: eliciting requirements from users, getting budgets approved, setting up the build server, deploying the application to QA and production environments, migrating the business from the old processes or programs, etc.

在任何项目中，程序员都可能有很多事情没有积极参与：向用户征询需求、获得预算批准、设置构建服务器、将应用程序部署到 QA 和生产环境、从旧流程或程序中迁移业务等。

When you aren't actively involved in things there is an unconscious tendency to assume that they are simple and happen "by magic." While the magic continues to happen all is well. But when — it is usually "when" and not "if" — the magic stops the project is in trouble.

当你没有积极参与时，就会不自觉地认为这些事情很简单，是 "魔术 "发生的。当魔术继续发生时，一切都很顺利。但是，当魔术停止时，通常是 "当 "而不是 "如果"，项目就会陷入困境。

I've known projects lose weeks of developer time because no one understood how they relied on "the right" version of a DLL being loaded. When things started failing intermittently team members looked everywhere else before someone noticed that "a wrong" version of the DLL was being loaded.

据我所知，由于没有人理解他们是如何依赖于加载 DLL 的 "正确 "版本，项目损失了开发人员数周的时间。当出现断断续续的故障时，团队成员四处寻找，直到有人注意到正在加载的 DLL 版本是 "错误的"。

Another department was running smoothly — projects delivered on time, no late night debugging sessions, no emergency fixes. So smoothly, in fact, that senior management decided that things "ran themselves" and they could do without the project manager. Inside six months the projects in the department looked just like the rest of the organization — late, buggy and continually being patched.

另一个部门运行顺利--项目按时交付，没有深夜调试，没有紧急修复。事实上，这个部门运行得如此顺利，以至于高级管理层决定 "自己管理自己"，可以不用项目经理了。六个月后，该部门的项目看起来就像企业的其他部门一样--延迟交付、漏洞百出、不断打补丁。

You don't have to understand all the magic that makes your project work, but it doesn't hurt to understand some of it — or to appreciate someone who understands the bits you don't.

你不必了解项目运作的所有奥妙，但了解一些也无妨--或者欣赏那些了解你不了解的部分的人。

Most importantly, make sure that when the magic stops it can be started again.

最重要的是，要确保当魔法停止时，它可以再次启动。

By [AlanGriffiths](http://programmer.97things.oreilly.com/wiki/index.php/AlanGriffiths)