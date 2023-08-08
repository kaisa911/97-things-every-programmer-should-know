# 用领域的语言来编写代码

Picture two codebases. In one you come across:
想象两个代码库。在其中一个你遇到了：

```
if (portfolioIdsByTraderId.get(trader.getId())
  .containsKey(portfolio.getId())) {...}
```
  
You scratch your head, wondering what this code might be for. It seems to be getting an ID from a trader object, using that to get a map out of a, well, map-of-maps apparently, and then seeing if another ID from a portfolio object exists in the inner map. You scratch your head some more. You look for the declaration of portfolioIdsByTraderId and discover this:

你挠挠头，想知道这段代码是用来做什么的。它似乎是从一个交易员对象中获取一个 ID，然后用它从一个，嗯，显然是一个映射的映射中获取一个映射，然后看看另一个来自投资组合对象的 ID 是否存在于内部映射中。你再挠挠头。你寻找 portfolioIdsByTraderId 的声明，发现了这个：

```
Map<int, Map<int, int>> portfolioIdsByTraderId;
```

Gradually you realise it might be something to do with whether a trader has access to a particular portfolio. And of course you will find the same lookup fragment — or more likely a similar-but-subtly-different code fragment — whenever something cares whether a trader has access to a particular portfolio.

渐渐地，你意识到这可能与交易员是否有权访问某个特定的投资组合有关。当然，每当有什么东西关心交易员是否有权访问某个特定的投资组合时，你都会发现相同的查找片段——或者更可能是类似但微妙不同的代码片段。

In the other codebase you come across this:

在另一个代码库中，你遇到了这个：

```
if (trader.canView(portfolio)) {...}
```

No head scratching. You don't need to know how a trader knows. Perhaps there is one of these maps-of-maps tucked away somewhere inside. But that's the trader's business, not yours.

不用挠头了。你不需要知道交易员是怎么知道的。也许有一个这样的映射的映射藏在某个地方里面。但那是交易员的事，不关你的事。

Now which of those codebases would you rather be working in?

现在你更愿意在哪个代码库中工作呢？

Once upon a time we only had very basic data structures: bits and bytes and characters (really just bytes but we would pretend they were letters and punctuation). Decimals were a bit tricky because our base 10 numbers don't work very well in binary, so we had several sizes of floating-point types. Then came arrays and strings (really just different arrays). Then we had stacks and queues and hashes and linked lists and skip lists and lots of other exciting data structures *that don't exist in the real world*. "Computer science" was about spending lots of effort mapping the real world into our restrictive data structures. The real gurus could even remember how they had done it.

从前，我们只有非常基本的数据结构：位和字节和字符（其实就是字节，但我们会假装它们是字母和标点符号）。十进制有点棘手，因为我们的十进制数在二进制中不太好用，所以我们有几种大小的浮点类型。然后出现了数组和字符串（其实就是不同的数组）。然后我们有了栈和队列和哈希和链表和跳表和许多其他令人兴奋的数据结构**，它们在现实世界中并不存在**。“计算机科学”就是花费大量的努力把现实世界映射到我们限制性的数据结构中。真正的大师甚至能记住他们是怎么做到的。

Then we got user-defined types! OK, this isn't news, but it does change the game somewhat. If your domain contains concepts like traders and portfolios, you can model them with types called, say, Trader and Portfolio. But, more importantly than this, you can model *relationships between them* using domain terms too.

然后我们得到了用户定义的类型！好吧，这不是什么新闻，但它确实改变了游戏规则。如果你的领域包含了像交易员和投资组合这样的概念，你可以用叫做，比如说，Trader 和 Portfolio 的类型来建模它们。但是，比这更重要的是，你也可以用领域的术语来建模它们之间的关系。

If you don't code using domain terms you are creating a tacit (read: secret) understanding that *this* int over here means the way to identify a trader, whereas *that* int over there means the way to identify a portfolio. (Best not to get them mixed up!) And if you represent a business concept ("Some traders are not allowed to view some portfolios — it's illegal") with an algorithmic snippet, say an existence relationship in a map of keys, you aren't doing the audit and compliance guys any favors.

如果你不用领域的术语来编码，你就是在创建一个隐含的（也就是说：秘密的）理解，即这个 int 在这里意味着识别一个交易员的方式，而那个 int 在那里意味着识别一个投资组合的方式。（最好不要把它们混淆！）而且，如果你用一个算法片段来表示一个业务概念（“有些交易员不允许查看某些投资组合——这是非法的”），比如说一个映射中键的存在关系，你就没有给审计和合规的人员带来任何好处。

The next programmer along might not be in on the secret, so why not make it explicit? Using a key as a lookup to another key that performs an existence check is not terribly obvious. How is someone supposed to intuit that's where the business rules preventing conflict of interest are implemented?

沿着代码走的下一个程序员可能不知道这个秘密，所以为什么不把它明确呢？用一个键作为另一个键的查找，然后执行一个存在检查，这并不是很明显。有人怎么能直觉到这就是实现防止利益冲突的业务规则的地方呢？

Making domain concepts explicit in your code means other programmers can gather the *intent* of the code much more easily than by trying to retrofit an algorithm into what they understand about a domain. It also means that when the domain model evolves — which it will as your understanding of the domain grows — you are in a good position to evolve the code. Coupled with good encapsulation, the chances are good that the rule will exist in only one place, and that you can change it without any of the dependent code being any the wiser.

在你的代码中明确领域概念意味着其他程序员可以更容易地获取代码的意图，而不是试图把一个算法适配到他们对领域的理解中。这也意味着当领域模型演化时——随着你对领域的理解增长，它会演化——你处于一个很好的位置来演化代码。结合良好的封装，很有可能规则只存在于一个地方，而且你可以改变它而不让任何依赖的代码知道。

The programmer who comes along a few months later to work on the code will thank you. The programmer who comes along a few months later might be you.

几个月后来工作在代码上的程序员会感谢你。几个月后来工作在代码上的程序员可能就是你。

By [Dan North](http://programmer.97things.oreilly.com/wiki/index.php/Dan_North)