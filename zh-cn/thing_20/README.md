# 尽早部署，经常部署

Debugging the deployment and installation processes is often put off until close to the end of a project. In some projects writing installation tools is delegated to a release engineer who take on the task as a "necessary evil." Reviews and demonstrations are done from a hand-crafted environment to ensure that everything works. The result is that the team gets no experience with the deployment process or the deployed environment until it may be too late to make changes.

部署和安装过程的调试工作往往被推迟到项目接近尾声时才进行。在某些项目中，编写安装工具的工作被委托给发布工程师，他们把这项任务当作 "必要之恶"。审查和演示都是在手工制作的环境中进行的，以确保一切正常。这样做的结果是，团队对部署流程或部署环境毫无经验可言，直到做出更改时可能为时已晚。

The installation/deployment process is the first thing that the customer sees, and a simple installation/deployment process is the first step to having a reliable (or, at least, easy to debug) production environment. The deployed software is what the customer will use. By not ensuring that the deployment sets up the application correctly, you'll raise questions with your customer before they get to use your software thoroughly.

客户首先看到的是安装/部署过程，而简单的安装/部署过程是拥有可靠（或至少易于调试）生产环境的第一步。部署的软件是客户将要使用的。如果不能确保部署时正确设置应用程序，客户在彻底使用软件之前就会产生疑问。

Starting your project with an installation process will give you time to evolve the process as you move through the product development cycle, and the chance to make changes to the application code to make the installation easier. Running and testing the installation process on a clean environment periodically also provides a check that you have not made assumptions in the code that rely on the development or test environments.

以安装流程启动项目，可以让您有时间在产品开发周期中不断改进流程，并有机会修改应用程序代码，使安装更加简便。定期在干净的环境中运行和测试安装过程，还可以检查代码中是否存在依赖开发或测试环境的假设。

Putting deployment last means that the deployment process may need to be more complicated to work around assumptions in the code. What seemed a great idea in an IDE, where you have full control over an environment, might make for a much more complicated deployment process. It is better to know all the trade-offs sooner rather than later.

将部署放在最后，意味着部署过程可能需要更加复杂，以绕过代码中的假设。在集成开发环境中，您可以完全控制环境，而在集成开发环境中，这似乎是个好主意，但在部署过程中可能会变得复杂得多。最好是尽早了解所有的利弊得失。

While "being able to deploy" doesn't seem to have a lot of business value early on as compared to seeing an application run on a developer's laptop, the simple truth is that until you can demonstrate you application on the target environment, there is a lot of work to do before you can deliver business value. If your rationale for putting off a deployment process is that it is trivial, then do it anyway since it is low cost. If it's too complicated, or if there are too many uncertainties, do what you would do with application code: experiment, evaluate, and refactor the deployment process as you go.

虽然与看到应用程序在开发人员的笔记本电脑上运行相比，"能够部署 "在早期似乎并没有太大的商业价值，但一个简单的事实是，在你能够在目标环境中演示你的应用程序之前，你还有很多工作要做，然后才能实现商业价值。如果你推迟部署流程的理由是它微不足道，那么无论如何都要做，因为它成本低。如果过于复杂，或者存在太多不确定因素，那就像处理应用程序代码一样：边实验、边评估、边重构部署流程。

The installation/deployment process is essential to the productivity of your customers or your professional services team, so you should be testing and refactoring this process as you go. We test and refactor the source code throughout a project. The deployment deserves no less.

安装/部署流程对客户或专业服务团队的工作效率至关重要，因此您应该在进行过程中测试和重构这一流程。我们在整个项目中都会对源代码进行测试和重构。部署工作也不例外。

By [Steve Berczuk](http://programmer.97things.oreilly.com/wiki/index.php/Steve_Berczuk)
