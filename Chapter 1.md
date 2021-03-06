# 第一章： 为什么要持续部署

持续部署是一种对于将软件的修改快速、安全、自动部署到生产环境的一种事件。

在持续部署的世界里，发布一个功能函数并不是那种极其重要的，需要全公司的人停下手中的工作几个星期，在各种监控图表前面焦虑地等待部署的这种重大的时刻。相反，发布新的代码给用户应该是一种有规律的，乏味的，简单到每天可以重复很多次的那种工作。

在这一章中，我们将会介绍可以支持持续部署落地所需要的组织结构和技术实践。我们希望你能够从中受益，缩短你的发布流程，帮助你理解Netflix和其他类似的公司的持续部署文化和实践。

## 长发布流程所带来的问题
  
依赖在不断发生变化。需要部署的代码变得越来越多，他们所依赖的类库或者所依赖的其他服务也在变化之中。当代码真正被发布的时候，一些未曾预见的问题就出现了，比如说上游依赖版本的变更、需要调用的服务接口变更等等。

开发人员也在流动。当一个特性开发完成以后，开发人员通常自然而然的转到其他的项目中，或者继续开发其他新的特性。当出现问题的时候，通常开发人员需要回想一个月、六个月、甚至一年以前他所做的工作。更糟糕的是，在这段时间当中，代码通常还会有持续的变更，这就使得找到问题的根因更加困难。

所以，我们如何让代码发布变得更简单呢？

## 持续部署所带来的好处

持续部署简化了繁琐的代码发布流程。它将带来以下好处：

### 持续创新

持续部署可以缩短新功能、配置变更、故障修复上线的时间。

### 快速的反馈

频繁的部署相似的变更使得查找问题变得更加容易。通过将类似于chaos这种测试技术和自动化金丝雀分析技术加入到发布流程中，使得查找定位问题更加迅速，修复问题更加有效率。

### 增加可靠性和可用性
为了让发布更快，持续部署工具中的自动化部署流程代替了容易出错的手动部署。精心制作的持续部署Pipeline可以在特定的时间里在不同的云服务中逐渐发布变更。可以将安全部署的实践逐步固化到常规发布流程中。

### 更加有效率地开发
更频繁的发布节奏可以帮助减少类似于上游依赖变更带来的问题。缩短从代码提交到部署上线的时间可以帮助开发人员更快的发现并修复问题。开发人员负责维护他们部署的服务，可以增强他们对于这个服务的责任感，这有助于在服务发生问题的时候，减少部门间的相互推脱。持续部署能够提高开发人员的效率。

## 有效的实践
当系统变更被发布的时候，它所引入的bug或者兼容性问题会影响到整个系统的可用性。只有引入更好的工具，正确的实践和良好的工程师文化才能有效的支持系统频繁的变更。

这里我们介绍一些，我们在实践中总结的有用的技术性的规范：

### 自己动手丰衣足食
让代码的开发人员自己动手部署他们的代码，而不是让专门的团队做这件事。通过提供便捷的工具给开发工程师，提高他们对代码的自信，让他们能够在他们认为合适的时候部署代码。

### 让一切自动进行
在编译、测试、发布各个阶段全面的拥抱自动化技术。

### 让一切可见
无法看到它，就无法改进它。我们认为通过将不同账号、不同地域、不同云厂商的服务放在同一个界面上，有助于简化基础设置问题的定位。通过Pipeline进行部署有利于让用户更直观的了解到部署的内容在每个阶段发生了什么事情。

### 让一切变得简单
进行一次云服务的部署不应该是一种专业的技能。我们认为让任何人都可以来改进他们自己的部署流程是持续部署中的一个重要环节。
### 做好准备
当你的做好了模板式的工具以后，任何一个团队都会很愿意接受持续部署的流程。我们定义了所谓的做好准备（Paved road）即将团队希望的部署流程做好完善的封装。随着越来越多的团队开始使用你的工具，我们对于系统的任何改善，都将使所有使用工具的团队受益。最佳实践是慢慢积累而来的。

## 总结
在迁移至持续部署平台以后，我们发现由不良的部署方式所带来的问题出现的越来越少。如今，我们已经将业务全部迁移到spinnaker上，部署所带来的的问题显著减少，这些经验让我们将spinnaker作为部署的最佳实践推广出去变得更加有意义。