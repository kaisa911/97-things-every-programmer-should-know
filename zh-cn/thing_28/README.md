# 不要将程序固定在直立位置

I once wrote a spoof C++ quiz, in which I satirically suggested the following strategy for exception handling:

我曾经写过一篇恶搞 C++ 的小测验，其中讽刺性地提出了以下异常处理策略：

> By dint of plentiful `try...catch` constructs throughout our code base, we are sometimes able to prevent our applications from aborting. We think of the resultant state as "nailing the corpse in the upright position."

> 通过在整个代码库中使用大量的 "try...catch "构造，我们有时可以防止应用程序中止。我们将这种结果视为 "将尸体钉在直立位置"。

Despite my levity, I was actually summarizing a lesson I received at the knee of Dame Bitter Experience herself.

尽管我说得很轻松，但实际上我是在总结我在苦难经历女士膝下接受的一堂课。

It was a base application class in our own, homemade C++ library. It had suffered the pokings of many programmers' fingers over the years: Nobody's hands were clean. It contained code to deal with all escaped exceptions from everything else. Taking our lead from Yossarian in Catch-22, we decided, or rather felt (*decided* implies more thought than went into the construction of this monster) that an instance of this class should live forever or die in the attempt.

那是我们自制的 C++ 库中的一个基础应用类。多年来，它饱受了许多程序员的指摘： 没有人的手是干净的。它包含的代码可以处理所有从其他程序中逃逸出来的异常。我们借鉴了《谍影重重》中尤萨里安的做法，决定，或者说感觉（*决定*意味着在构建这个怪物时花费了更多的心思），这个类的实例应该永生，或者在尝试中死亡。

To this end, we intertwined multiple exception handlers. We mixed in Windows' structured exception handling with the native kind (remember `__try...__except` in C++? Me neither). When things threw unexpectedly, we tried calling them again, pressing the parameters harder. Looking back, I like to think that when writing an inner `try...catch` handler within the catch clause of another, some sort of awareness crept over me that I might have accidentally taken a slip road from the motorway of good practice into the aromatic but insalubrious lane of lunacy. However, this is probably retrospective wisdom.

为此，我们将多个异常处理程序交织在一起。我们将 Windows 的结构化异常处理与本地异常处理混合在一起（还记得 C++ 中的 `__try...__except`吗？ 我也不记得）。当出现意外情况时，我们会尝试再次调用它们，并对参数施加更大的压力。现在回想起来，我觉得当我在另一个处理程序的 catch 子句中编写一个内部的 `try...catch` 处理程序时，我突然意识到，我可能不小心从良好实践的高速公路上滑入了芳香四溢但不健康的疯狂车道。不过，这也许是回想起来的智慧。

Needless to say, whenever something went wrong in applications based on this class, they vanished like Mafia victims at the dockside, leaving behind no useful trail of bubbles to indicate what the hell happened, notwithstanding the dump routines that were supposedly called to record the disaster. Eventually — a long eventually — we took stock of what we had done, and experienced shame. We replaced the whole mess with a minimal and robust reporting mechanism. But this was many crashes down the line.

不用说，每当基于该类的应用程序出错时，它们就会像黑手党受害者一样消失在码头边，没有留下任何有用的气泡痕迹来说明到底发生了什么，尽管我们调用了转储例程来记录灾难。最终--漫长的最终--我们总结了自己的所作所为，并感到羞愧。我们用一个最小化的、强大的报告机制取代了整个混乱的局面。不过，这已经是很多次崩溃之后的事情了。

I wouldn't bother you with this — for surely nobody else could ever be as stupid as we were — but for an online argument I had recently with a bloke whose academic job title declared he should know better. We were discussing Java code in a remote transaction. If the code failed, he argued, it should catch and block the exception *in situ*. ("And then do *what* with it?" I asked. "Cook it for supper?")

我不会拿这个来烦你们--因为肯定没有人会像我们一样愚蠢--但是最近我和一个家伙在网上发生了争执，他的学术职称宣称他应该更了解情况。我们讨论的是远程事务中的 Java 代码。他认为，如果代码失败了，就应该*原地*捕获并阻止异常。(我问："然后做什么？""把它煮了当晚饭？"）。

He quoted the UI designers' rule: NEVER LET THE USER SEE AN EXCEPTION REPORT, rather as though this settled the matter, what with it being in caps and everything. I wonder if he was responsible for the code in one of those blue-screened ATMs whose photos decorate the feebler blogs, and had been permanently traumatized.

他引用了用户界面设计师的规则： 他引用了用户界面设计师的原则：永远不要让用户看到异常报告，好像这样就解决了问题，因为报告是大写的。我不知道他是否负责过那些蓝屏自动取款机中的代码，而这些自动取款机的照片就装饰在那些孱弱的博客上，他因此受到了永久性的创伤。

Anyway, if you should meet him, nod and smile and take no notice, as you sidle towards the door.

总之，如果你遇到了他，请点头微笑，不要在意，侧身向门口走去。

By [Verity Stob](http://programmer.97things.oreilly.com/wiki/index.php/Verity_Stob)