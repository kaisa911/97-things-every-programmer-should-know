# 关于注释的评论

In my first programming class in college, my teacher handed out two BASIC coding sheets. On the board, the assignment read "Write a program to input and average 10 bowling scores." Then the teacher left the room. How hard could this be? I don't remember my final solution but I'm sure it had a `FOR/NEXT` loop in it and couldn't have been more than 15 lines long in total. Coding sheets — for you kids reading this, yes, we used to write code out longhand before actually entering it into a computer — allowed for around 70 lines of code each. I was very confused as to why the teacher would have given us two sheets. Since my handwriting has always been atrocious, I used the second one to recopy my code very neatly, hoping to get a couple extra points for style.

在我大学的第一堂编程课上，老师发给我两张 BASIC 代码表。黑板上的作业写着："编写一个程序，输入并平均 10 个保龄球得分"。然后老师就离开了教室。这能有多难？我不记得我的最终解决方案了，但我肯定其中有一个 "FOR/NEXT "循环，总长不会超过 15 行。编码表--对正在看这篇文章的孩子们来说，是的，我们过去都是先手写代码，然后再输入电脑--每张表大约可以写 70 行代码。我很不明白老师为什么要给我们两张纸。因为我的字一向很糟糕，所以我用第二张纸工工整整地重新抄写了一遍代码，希望能为自己的风格加几分。

Much to my surprise, when I received the assignment back at the start of the next class, I received a barely passing grade. (It was to be an omen to me for the rest of my time in college.) Scrawled across the top of my neatly copied code, "No comments?"

出乎我意料的是，当我在下一堂课开始时收到作业时，我只得到了一个勉强及格的分数。(在我整齐抄写的代码上方，潦草地写着 "没有注释？"（这是我大学余生的一个预兆）。

It was not enough that the teacher and I both knew what the program was supposed to do. Part of the point of the assignment was to teach me that my code should explain itself to the next programmer coming behind me. It's a lesson I've not forgotten.

老师和我都知道程序应该做什么，这还不够。这项作业的部分意义在于让我明白，我的代码应该向我后面的程序员解释自己。这一课我至今难忘。

Comments are not evil. They are as necessary to programming as basic branching or looping constructs. Most modern languages have a tool akin to javadoc that will parse properly formatted comments to automatically build an API document. This is a very good start, but not nearly enough. Inside your code should be explanations about what the code is supposed to be doing. Coding by the old adage, "If it was hard to write, it should be hard to read," does a disservice to your client, your employer, your colleagues, and your future self.

注释并不邪恶。它们与基本的分支或循环结构一样，都是编程所必需的。大多数现代语言都有类似 javadoc 的工具，可以解析格式正确的注释，自动构建 API 文档。这是一个很好的开始，但还远远不够。在你的代码中，应该解释代码应该做什么。按照 "写起来难，读起来也应该难 "的古训来编写代码，对客户、雇主、同事和未来的自己都是一种伤害。

On the other hand, you can go too far in your commenting. Make sure that your comments clarify your code but do not obscure it. Sprinkle your code with relevant comments explaining what the code is supposed to accomplish. Your header comments should give any programmer enough information to use your code without having to read it, while your in-line comments should assist the next developer in fixing or extending it.

另一方面，你也可以在注释方面做得太过分。确保你的注释能阐明你的代码，但不会模糊代码。在代码中加入相关注释，解释代码应该达到的目的。你的标题注释应该为任何程序员提供足够的信息，让他们无需阅读就能使用你的代码，而你的行内注释应该有助于下一个开发人员修复或扩展代码。

At one job, I disagreed with a design decision made by those above me. Feeling rather snarky, as young programmers often do, I pasted the text of the email instructing me to use their design into the header comment block of the file. It turns out that managers at this particular shop actually reviewed the code when it was committed. It was my first introduction to the term *career-limiting move*.

在一份工作中，我不同意上司的一个设计决定。年轻的程序员经常这样，我觉得自己很尖酸刻薄，于是就把指示我使用他们的设计的邮件内容粘贴到文件的头注释块中。事实证明，在提交代码时，这家商店的经理们确实审查了代码。这是我第一次接触到 "限制职业生涯的举动 "这个词。

by [Cal Evans](http://programmer.97things.oreilly.com/wiki/index.php/Cal_Evans)