# 代码审查

You should do code reviews. Why? Because they *increase code quality* and *reduce defect rate*. But not necessarily for the reasons you might think.

您应该进行代码审查。为什么？因为它们能*提高代码质量*和*降低缺陷率*。但原因未必如你所想。

Because they may previously have had some bad experiences with reviews, many programmers tend to dislike code reviews. I have seen organizations that require that all code pass a formal review before being deployed to production. Often it is the architect or a lead developer doing this review, a practice that can be described as *architect reviews everything*. This is stated in their software development process manual, so therefore the programmers must comply. There may be some organizations that need such a rigid and formal process, but most do not. In most organizations such an approach is counterproductive. Reviewees can feel like they are being judged by a parole board. Reviewers need both the time to read the code and the time to keep up to date with all the details of the system. The reviewers can rapidly become the bottleneck in this process, and the process soon degenerates.

由于以前可能有过一些不愉快的审查经历，很多程序员往往不喜欢代码审查。我见过一些组织要求所有代码在部署到生产前都要通过正式审查。通常是由架构师或首席开发人员进行审核，这种做法可以被描述为 "架构师审核一切"。这在他们的软件开发流程手册中有所规定，因此程序员必须遵守。可能有些组织需要这样一个严格而正式的流程，但大多数组织并不需要。在大多数组织中，这种方法会适得其反。受审者会觉得自己是在接受假释委员会的审判。审核人员既需要时间阅读代码，也需要时间了解系统的所有细节。在这个过程中，审核人员可能会迅速成为瓶颈，流程很快就会退化。

Instead of simply correcting mistakes in code, the purpose of code reviews should be to *share knowledge* and establish common coding guidelines. Sharing your code with other programmers enables collective code ownership. Let a random team member *walk through the code* with the rest of the team. Instead of looking for errors you should review the code by trying to learn it and understand it.

代码审查的目的不应只是纠正代码中的错误，而应是*分享知识*和建立共同的编码准则。与其他程序员共享代码可以实现集体代码所有权。让随机的团队成员与团队其他成员一起*演练代码*。在审查代码时，与其寻找错误，不如努力学习和理解代码。

Be gentle during code reviews. Ensure that comments are *constructive, not caustic*. Introduce different *review roles* for the review meeting, to avoid having organizational seniority among team members affect the code review. Examples of roles could include having one reviewer focus on documentation, another on exceptions, and a third to look at the functionality. This approach helps to spread the review burden across the team members.

代码审查时要温和。确保评论是*建设性的，而不是苛刻的*。在审查会上引入不同的*审查角色*，以避免团队成员的组织资历影响代码审查。举例来说，可以让一名审查员专注于文档，另一名审查员专注于异常，第三名审查员专注于功能。这种方法有助于分散团队成员的审查负担。

Have a regular *code review* day each week. Spend a couple of hours in a review meeting. Rotate the reviewee every meeting in a simple round-robin pattern. Remember to switch roles among team members every review meeting too. *Involve newbies* in code reviews. They may be inexperienced, but their fresh university knowledge can provide a different perspective. *Involve experts* for their experience and knowledge. They will identify error-prone code faster and with more accuracy. Code reviews will flow more easily if the team has *coding conventions* that are checked by tools. That way, code formatting will never be discussed during the code review meeting.

每周有固定的代码审查日。花几个小时召开评审会议。每次会议以简单的循环模式轮流审查受审人。记得在每次评审会议上，团队成员之间也要互换角色。*让新手*参与代码审查。他们可能缺乏经验，但他们新鲜的大学知识可以提供不同的视角。*让专家*参与进来，因为他们经验丰富、知识渊博。他们会更快、更准确地找出容易出错的代码。如果团队有*编码规范*，并通过工具进行检查，那么代码审查就会更容易进行。这样，在代码评审会议上就不会讨论代码格式问题了。

*Making code reviews fun* is perhaps the most important contributor to success. Reviews are about the people reviewing. If the review meeting is painful or dull it will be hard to motivate anyone. Make it an *informal code review* whose prime purpose is sharing knowledge between team members. Leave sarcastic comments outside and bring a cake or brown bag lunch instead.

*让代码评审充满乐趣*可能是成功的最重要因素。审查是关于审查的人。如果评审会议是痛苦或沉闷的，就很难调动任何人的积极性。让代码评审成为*非正式的评审*，其主要目的是在团队成员之间分享知识。把讽刺性的评论留在会场外，带上蛋糕或棕色袋装午餐。

by [Mattias Karlsson](http://programmer.97things.oreilly.com/wiki/index.php/Mattias_Karlsson)