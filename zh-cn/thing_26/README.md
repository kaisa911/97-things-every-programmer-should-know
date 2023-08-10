# 不要忽视错误！

> _一天晚上，我走在街上，准备去酒吧见几个朋友。我们已经有一段时间没有一起喝啤酒了，我很期待再次见到他们。匆忙中，我没有看清方向。我被路缘绊倒了，结果摔了个四脚朝天。我想，这就是我没注意的报应吧。_

> _我的腿很疼，但我急着去见朋友。于是我爬起来继续往前走。走着走着，疼痛越来越厉害。虽然一开始我以为是受惊了，但很快我就意识到出了问题。_

> _但我还是匆匆赶往酒吧。到达酒吧时，我已经痛苦不堪。我没有度过一个愉快的夜晚，因为我非常心烦意乱。早上我去看了医生，发现我的胫骨骨折了。如果我在感到疼痛时停下来，我就不会因为走在上面而造成更大的伤害。这可能是我一生中最糟糕的一个早晨了。_

Too many programmers write code like my disastrous night out.
太多程序员写的代码就像我的灾难性之夜。

_Error, what error? It won't be serious. Honestly. I can ignore it._ This is not a winning strategy for solid code. In fact, it's just plain laziness. (The wrong sort.) No matter how unlikely you think an error is in your code, you should always check for it, and always handle it. Every time. You're not saving time if you don't: You're storing up potential problems for the future.

*错误，什么错误？不会很严重的，我可以忽略它。*老实说 这不是编写可靠代码的制胜法宝。事实上，这只是一种懒惰。无论你认为代码中出现错误的可能性有多小，你都应该检查并处理它。每次都这样。如果你不这样做，你就不是在节省时间：你是在为将来储存潜在的问题。

We report errors in our code in a number of ways, including:
我们通过多种方式报告代码中的错误，包括

- **Return codes** can be used as the resulting value of a function to mean "it didn't work." Error return codes are far too easy to ignore. You won't see anything in the code to highlight the problem. Indeed, it's become standard practice to ignore some standard C functions' return values. How often do you check the return value from printf?

- 返回代码\*\*可用作函数的结果值，表示 "函数没有工作"。错误返回代码很容易被忽略。你在代码中看不到任何突出问题的地方。事实上，忽略某些标准 C 函数的返回值已经成为一种标准做法。你经常检查 printf 的返回值吗？

- **errno** is a curious C aberration, a separate global variable set to signal error. It's easy to ignore, hard to use, and leads to all sorts of nasty problems — for example, what happens when you have multiple threads calling the same function? Some platforms insulate you from pain here; others do not.
- **errno**是一种奇怪的 C 语言异常，它是一个独立的全局变量，被设置为错误信号。它很容易被忽略，却很难使用，而且会导致各种令人讨厌的问题--例如，当多个线程调用同一个函数时会发生什么？有些平台会让你免受痛苦，有些平台则不会。

- **Exceptions** are a more structured language-supported way of signaling and handling errors. And you can't possibly ignore them. Or can you? I've seen lots of code like this:
- **异常**是一种更有条理的语言支持的错误信号和处理方式。你不可能忽略它们。你能做到吗？我见过很多这样的代码：

```
try {
    // ...do something...
}
catch (...) {} // ignore errors
```

The saving grace of this awful construct is that it highlights the fact you're doing something morally dubious.

这种可怕的结构的好处在于，它突出了你正在做的事情在道德上是可疑的。

If you ignore an error, turn a blind eye, and pretend that nothing has gone wrong, you run great risks. Just as my leg ended up in a worse state than if I'd stopped walking on it immediately, plowing on regardless can lead to very complex failures. Deal with problems at the earliest opportunity. Keep a short account.

如果你无视错误，视而不见，假装什么都没发生，你就会冒很大的风险。就像我的腿最终的状况比我立即停止走路还要糟糕一样，不管不顾地继续前进可能会导致非常复杂的失败。尽早处理问题。做一个简短的记录。

Not handling errors leads to:

不处理错误会导致

- **Brittle code.** Code that's filled with exciting, hard-to-find bugs.
- **脆弱的代码。** 充满令人兴奋、难以发现的错误的代码。

- **Insecure code.** Crackers often exploit poor error handling to break into software systems.
- **不安全的代码。** 破解者经常利用糟糕的错误处理来入侵软件系统。

- **Poor structure.** If there are errors from your code that are tedious to deal with continually, you have probably have a poor interface. Express it so that the errors are less intrusive and the their handling is less onerous.
- **结构不良。** 如果你的代码中存在一些错误，需要不断地处理这些错误，那么很可能是你的界面不良。如果你的代码中出现了令人厌烦的错误，那么你的界面很可能很糟糕。

Just as you should check all potential errors in your code, you need to expose all potentially erroneous conditions in your interfaces. Do not hide them, pretending that your services will always work.

正如你应该检查代码中所有潜在的错误一样，你也需要暴露接口中所有潜在的错误条件。不要把它们隐藏起来，假装你的服务总是能正常工作。

Why don't we check for errors? There are a number of common excuses. Which of these do you agree with? How would you counter each one?

我们为什么不检查错误？有很多常见的借口。你同意其中哪些？你会如何反驳？

- Error handling clutters up the flow of the code, making it harder to read, and harder to spot the "normal" flow of execution.
- 错误处理会扰乱代码的流程，使代码更难阅读，也更难发现 "正常 "的执行流程。

- It's extra work and I have a deadline looming.
- 这是额外的工作，而且我的最后期限快到了。

- I know that this function call will _never_ return an error (printf always works, malloc always returns new memory — if it fails we have bigger problems...).
- 我知道这个函数调用永远不会返回错误（printf 总是有效，malloc 总是返回新内存--如果它失败了，我们就有更大的问题了......）。

- It's only a toy program, and needn't be written to a production-worthy level.
- 这只是一个玩具程序，不需要写到生产级别。

By [Pete Goodliffe](http://programmer.97things.oreilly.com/wiki/index.php/Pete_Goodliffe)
