# 便捷不是能力

Much has been said about the importance and challenges of designing good API's. It's difficult to get right the first time and it's even more difficult to change later. Sort of like raising children. Most experienced programmers have learned that a good API follows a consistent level of abstraction, exhibits consistency and symmetry, and forms the vocabulary for an expressive language. Alas, being aware of the guiding principles does not automatically translate into appropriate behavior. Eating sweets is bad for you.

关于设计良好的应用程序接口的重要性和挑战，人们已经说了很多。第一次很难做对，以后更难改变。有点像养孩子。大多数经验丰富的程序员都知道，一个好的应用程序接口要遵循一致的抽象层次，表现出一致性和对称性，并形成表达语言的词汇表。可惜，对指导原则的了解并不能自动转化为适当的行为。吃甜食对身体不好。

Instead of preaching from on high, I want to pick on a particular API design 'strategy,' one that I encounter time and again: the argument of convenience. It typically begins with one of the following 'insights:'

我不想高高在上地说教，而是想挑出一种特殊的应用程序接口设计 "策略"，一种我屡次遇到的 "策略"：便利性论证。它通常以以下 "见解 "之一开始："我不希望其他类也能使用我的 API。

- I don't want other classes to have to make two separate calls to do this one thing.
- 我不希望其他类必须分别调用两个方法才能完成这一件事。

- Why should I make another method if it's almost the same as this method? I'll just add a simple switch.
- 如果和这个方法几乎一样，我为什么要再做一个方法呢？我只需添加一个简单的开关。

- See, it's very easy: If the second string parameter ends with ".txt", the method automatically assumes that the first parameter is a file name, so I really don't need two methods.
- 瞧，这很简单：如果第二个字符串参数以".txt "结尾，该方法就会自动假定第一个参数是一个文件名，所以我真的不需要两个方法。

While well intended, such arguments are prone to decrease the readability of code using the API. A method invocation like
虽然出发点是好的，但这样的参数容易降低使用 API 的代码的可读性。像这样的方法调用

```
parser.processNodes(text, false);
```

is virtually meaningless without knowing the implementation or at least consulting the documentation. This method was likely designed for the convenience of the implementer as opposed to the convenience of the caller — "I don't want the caller to have to make two separate calls" translated into "I didn't want to code up two separate methods." There's nothing fundamentally wrong with convenience if it's intended to be the antidote to tediousness, clunkiness, or awkwardness. However, if we think a bit more carefully about it, the antidote to those symptoms is efficiency, consistency, and elegance, not necessarily convenience. APIs are supposed to hide underlying complexity, so we can realistically expect good API design to require some effort. A single large method could certainly be more convenient to write than a well thought-out set of operations, but would it be easier to use?

在不了解实现方法或至少不查阅文档的情况下，这种方法几乎毫无意义。这种方法很可能是为了实现者的方便而设计的，而不是为了调用者的方便--"我不想让调用者进行两次单独的调用 "变成了 "我不想编写两个单独的方法"。如果方便是为了解决繁琐、笨拙或笨拙的问题，那么从根本上说，方便并没有错。但是，如果我们仔细思考一下，这些症状的解药是效率、一致性和优雅，而不一定是便捷。应用程序接口本应隐藏底层的复杂性，因此我们可以期望良好的应用程序接口设计需要付出一些努力。一个单一的大型方法在编写时肯定会比一组经过深思熟虑的操作更方便，但它会更容易使用吗？

The metaphor of API as a language can guide us towards better design decisions in these situations. An API should provide an expressive language, which gives the next layer above sufficient vocabulary to ask and answer useful questions. This does not imply it should provide exactly one method, or verb, for each question that may be worth asking. A diverse vocabulary allows us to express subtleties in meaning. For example, we prefer to say run instead of walk(true), even though it could be viewed as essentially the same operation, just executed at different speeds. A consistent and well thought out API vocabulary makes for expressive and easy to understand code in the next layer up. More importantly, a composable vocabulary allows other programmers to use the API in ways you may not have anticipated — a great convenience indeed for the users of the API! Next time you are tempted to lump a few things together into one API method, remember that the English language does not have one word for `MakeUpYourRoomBeQuietAndDoYourHomeWork`, even though it would seem really convenient for such a frequently requested operation.

在这种情况下，将应用程序接口比喻为一种语言可以引导我们做出更好的设计决策。应用程序接口（API）应该提供一种具有表现力的语言，为上一层提供足够的词汇来提出和回答有用的问题。这并不意味着它应该为每个可能值得提出的问题提供完全相同的方法或动词。多样化的词汇可以让我们表达微妙的含义。例如，我们更喜欢说 run 而不是 walk(true)，尽管这可以被视为本质上相同的操作，只是执行速度不同而已。一致且经过深思熟虑的应用程序接口词汇能让下一层的代码更有表现力，也更容易理解。更重要的是，一个可组合的词汇表允许其他程序员以你可能没有预料到的方式使用 API，这对 API 的用户来说确实是一个极大的便利！下一次，当您想把几件事情合并到一个 API 方法中时，请记住英语中并没有一个词来表达 "MakeUpYourRoomBeQuietAndDoYourHomeWork"（让您的房间更安静，让您做您的家务），尽管对于这样一个经常被请求的操作来说，这个词似乎真的很方便。

By [Gregor Hohpe](http://programmer.97things.oreilly.com/wiki/index.php/Gregor_Hohpe)
