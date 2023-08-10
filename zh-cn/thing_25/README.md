# 测试数据不要太可爱

> _天色已晚。我扔进了一些占位符数据，以测试我一直在研究的页面布局。_

> _我盗用了 The Clash 乐队成员的名字作为用户名。公司名称？性手枪乐队的歌名就可以。现在我需要一些股票代码--就是一些大写的四字母单词。_

> _我用了**那些**四个字母的单词。_

> _这似乎没什么害处。我只是想在第二天连接真正的数据源之前，自娱自乐一下，也许还能逗逗其他开发人员。_

> \*第二天早上，一位项目经理为演示截图。\*\*

Programming history is littered with these kinds of war stories. Things that developers and designers did "that no one else would see" which unexpectedly became visible.

编程史上充斥着这类战争故事。开发人员和设计人员所做的 "别人不会看到 "的事情，却意外地变得显而易见。

The leak type can vary but, when it happens, it can be deadly to the person, team, or company responsible. Examples include:

泄漏的类型可能各不相同，但一旦发生，就会对责任人、团队或公司造成致命的影响。例子包括

- During a status meeting, a client clicks on an button which is as yet unimplemented. They are told: "Don't click that again, you moron."
- 在一次状态会议上，客户点击了一个尚未执行的按钮。他们被告知 "别再点击了，你个白痴"。

- A programmer maintaining a legacy system has been told to add an error dialog, and decides to use the output of existing behind-the-scenes logging to power it. Users are suddenly faced with messages such as "Holy database commit failure, Batman!" when something breaks.
- 一个维护传统系统的程序员被告知要添加一个错误对话框，并决定使用现有的幕后日志输出为其提供动力。当系统出现故障时，用户会突然看到诸如 "我靠，数据库提交失败，蝙蝠侠！"之类的信息。

- Someone mixes up the test and live administration interfaces, and does some "funny" data entry. Customers spot a $1m "Bill Gates-shaped personal massager" on sale in your online store.
- 有人混淆了测试界面和实时管理界面，并输入了一些 "奇怪 "的数据。客户在你的网店上发现一款价值 100 万美元的 "比尔-盖茨形个人按摩器 "在销售。

To appropriate the old saying that "a lie can travel halfway around the world while the truth is putting on its shoes," in this day and age a screw-up can be Dugg, Twittered, and Flibflarbed before anyone in the developer's timezone is awake to do anything about it.

俗话说："谎言可以传遍半个地球，而真相还在穿鞋。"在这个时代，在开发者所在时区的任何人还没睡醒，对一个错误采取任何措施之前，它就已经被 Dugg、Twitter 和 Flibflarbed 了。

Even your source code isn't necessarily free of scrutiny. In 2004, when a tarball of the Windows 2000 source code made its way onto file sharing networks, some folks merrily grepped through it for profanity, insults, and [other funny content](http://www.kuro5hin.org/story/2004/2/15/71552/7795). (The comment `// TERRIBLE HORRIBLE NO GOOD VERY BAD HACK` has, I will admit, become appropriated by me from time to time since!)

就连你的源代码也不一定能免于审查。2004 年，当 Windows 2000 源代码的压缩包出现在文件共享网络上时，一些人兴高采烈地在其中搜索亵渎、侮辱和[其他有趣的内容](http://www.kuro5hin.org/story/2004/2/15/71552/7795)。(我承认，"TERRIBLE HORRIBLE NO GOOD VERY BAD HACK "这个注释后来不时被我盗用！）。

In summary, when writing any text in your code — whether comments, logging, dialogs, or test data — always ask yourself how it will look if it becomes public. It will save some red faces all round.

总之，在代码中编写任何文本时，无论是注释、日志、对话框还是测试数据，都要问问自己，如果这些文本被公开，会是什么样子。这样做会让你少走很多弯路。

By [Rod Begbie](http://programmer.97things.oreilly.com/wiki/index.php/Rod_Begbie)
