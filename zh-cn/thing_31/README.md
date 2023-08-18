# 别碰密码

It has happened to everyone of us at some point. Your code was rolled on to the staging server for system testing and the testing manager writes back that she has hit a problem. Your first reaction is "Quick, let me fix that — I know what's wrong."

我们每个人都曾遇到过这种情况。你的代码被传送到暂存服务器进行系统测试，测试经理回信说她遇到了一个问题。你的第一反应是 "快，让我来解决--我知道哪里出了问题"。

In the bigger sense, though, what is wrong is that as a developer you think you should have access to the staging server.

但从更大的意义上说，问题在于作为开发人员，你认为自己应该有访问暂存服务器的权限。

In most web-based development environments the architecture can be broken down like this:

在大多数基于网络的开发环境中，架构可以这样分解：

- Local development and unit testing on the developer's machine
- 在开发人员的机器上进行本地开发和单元测试

- Development server where manual or automated integration testing is done
- 在开发服务器上进行手动或自动集成测试

- Staging server where the QA team and the users do acceptance testing
- 质量保证团队和用户进行验收测试的暂存服务器

- Production server
- 生产服务器

Yes, there are other servers and services sprinkled in there, like source code control and ticketing, but you get the idea. Using this model, a developer — even a senior developer — should never have access beyond the development server. Most development is done on a developer's local machine using their favorite blend of IDEs, virtual machines, and an appropriate amount of black magic sprinkled over it for good luck.

是的，还有其他服务器和服务，如源代码控制和票务，但你已经明白了。使用这种模式，开发人员（即使是高级开发人员）的访问权限绝不能超出开发服务器。大多数开发工作都是在开发人员的本地计算机上完成的，使用的是他们最喜欢的集成开发环境、虚拟机和适量的黑魔法。

Once checked into SCC, whether automatically or manually, it should be rolled over to the development server where it can be tested and tweaked if necessary to make sure everything works together. From this point on, though, the developer is a spectator to the process.

一旦检查到 SCC，无论是自动还是手动，都应将其转到开发服务器，在那里进行测试，并在必要时进行调整，以确保一切正常。但从这一点来看，开发人员只是整个过程的旁观者。

The staging manager should package and roll the code to the staging server for the QA team. Just like developers should have no need to access anything beyond the development server, the QA team and the users have no need to touch anything on the development server. If it's ready for acceptance testing, cut a release and roll, don't ask the user to "Just look at something real quick" on the development server. Remember, unless you are coding the project by yourself, other people have code there and they may not be ready for the user to see it. The release manager is the only person who should have access to both.

暂存管理员应将代码打包并滚动到暂存服务器，供质量保证团队使用。就像开发人员不需要访问开发服务器以外的任何东西一样，质量保证团队和用户也不需要接触开发服务器上的任何东西。如果已经准备好进行验收测试、发布和滚动，就不要要求用户在开发服务器上 "快速查看一些东西"。请记住，除非是你一个人在编写项目代码，否则其他人也有代码在那里，而且他们可能还没准备好让用户查看。发布经理是唯一可以同时访问这两个服务器的人。

Under no circumstances — ever, at all — should a developer have access to a production server. If there is a problem, your support staff should either fix it or request that you fix it. After it's 
checked into SCC they will roll a patch from there. Some of the biggest programming disasters I've been a part of have taken place because someone \**cough*\*me\**cough\** violated this last rule. If it's broke, production is not the place to fix it.

在任何情况下，开发人员都不能访问生产服务器。如果出现问题，您的支持人员应该解决问题或要求您解决问题。在 
他们会从那里推出一个补丁。我参与过的一些最大的编程灾难就是因为有人违反了这最后一条规则。如果它坏了，生产部门不是修复它的地方。

by [Cal Evans](http://programmer.97things.oreilly.com/wiki/index.php/Cal_Evans)