# 不要害怕打破东西

Everyone with industry experience has undoubtedly worked on a project where the codebase was precarious at best. The system is poorly factored, and changing one thing always manages to break another unrelated feature. Whenever a module is added, the coder's goal is to change as little as possible, and hold their breath during every release. This is the software equivalent of playing Jenga with I-beams in a skyscraper, and is bound for disaster.

每个有行业经验的人无疑都曾参与过一个项目，在这个项目中，代码库充其量也只能算是岌岌可危。系统的要素不完善，改变一件事总会破坏另一个无关的功能。每当添加一个模块时，编码员的目标就是尽可能少改动，并在每次发布时屏住呼吸。这就好比在摩天大楼里用工字钢玩 Jenga 游戏，注定会带来灾难。

The reason that making changes is so nerve wracking is because the system is sick. It needs a doctor, otherwise its condition will only worsen. You already know what is wrong with your system, but you are afraid of breaking the eggs to make your omelet. A skilled surgeon knows that cuts have to be made in order to operate, but the skilled surgeon also knows that the cuts are temporary and will heal. The end result of the operation is worth the initial pain, and the patient should heal to a better state than they were in before the surgery.

进行修改之所以如此令人紧张，是因为系统生病了。它需要医生，否则病情只会恶化。你已经知道你的系统出了什么问题，但你害怕打破鸡蛋做煎蛋卷。技术高超的外科医生知道，为了做手术，必须切开伤口，但技术高超的外科医生也知道，伤口是暂时的，会愈合的。手术的最终结果值得最初的痛苦，病人愈合后的状态应该比手术前更好。

Don't be afraid of your code. Who cares if something gets temporarily broken while you move things around? A paralyzing fear of change is what got your project into this state to begin with. Investing the time to refactor will pay for itself several times over the life cycle of your project. An added benefit is that your team's experience dealing with the sick system makes you all experts in knowing how it _should_ work. Apply this knowledge rather than resent it. Working on a system you hate is not how anybody should have to spend their time.

不要害怕你的代码。谁会在乎在你移动东西的时候，某些东西会暂时损坏呢？对变化的麻痹恐惧是导致你的项目陷入这种状态的罪魁祸首。在项目的生命周期中，投入时间进行重构将为自己带来数倍的回报。还有一个额外的好处是，你的团队在处理病态系统方面的经验让你们都成为了专家，知道它*应该*如何工作。应用这些知识，而不是怨恨它。任何人都不应该在自己讨厌的系统上浪费时间。

Redefine internal interfaces, restructure modules, refactor copy–pasted code, and simplify your design by reducing dependencies. You can significantly reduce code complexity by eliminating corner cases, which often result from improperly coupled features. Slowly transition the old structure into the new one, testing along the way. Trying to accomplish a large refactor in "one big shebang" will cause enough problems to make you consider abandoning the whole effort midway through.

重新定义内部接口、重组模块、重构复制粘贴的代码，并通过减少依赖性来简化设计。通过消除角落情况，你可以大大降低代码的复杂性，而角落情况往往是功能耦合不当造成的。缓慢地将旧结构过渡到新结构，并沿途进行测试。如果试图以 "大包大揽 "的方式完成一次大规模重构，所带来的问题足以让你考虑中途放弃整个工作。

Be the surgeon who isn't afraid to cut out the sick parts to make room for healing. The attitude is contagious and will inspire others to start working on those cleanup projects they've been putting off. Keep a "hygiene" list of tasks that the team feels are worthwhile for the general good of the project. Convince management that even though these tasks may not produce visible results, they will reduce expenses and expedite future releases. Never stop caring about the general "health" of the code.

要像外科医生一样，不怕切除有病的部分，为治疗腾出空间。这种态度是会传染的，会激励其他人开始进行他们一直拖延的清理项目。保存一份 "卫生 "清单，列出团队认为值得为项目的整体利益而完成的任务。让管理层相信，尽管这些任务可能不会产生明显的效果，但它们会减少开支，加快未来版本的发布。永远不要停止关心代码的总体 "健康状况"。

By [Mike Lewis](http://programmer.97things.oreilly.com/wiki/index.php/Mike_Lewis)
