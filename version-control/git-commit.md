# Git 提交规范

每次进行`git`提交时，都需要编写Commit Message，否则是不允许提交的。书写良好的Commit Message能大大提高代码维护的效率，编写Commit Message需要遵循一定的范式，内容应该清晰明了，指明本次提交的目的，便于日后追踪问题。

规范提交说明的好处如下

- 更加结构化的提交历史

- 保证每次信息都有确切的含义

- 方便直接生成`changelog`

- 方便信息搜索和过滤

当前业界应用的比较广泛的是 [Angular Contributing](https://github.com/angular/angular/blob/main/CONTRIBUTING.md)，还有就是[Conventional Commits(约定式提交)](https://www.conventionalcommits.org/zh-hans/v1.0.0/)，后者脱胎于Angular提交信息准则，提供了更加通用、简洁和灵活的提交规范。



## Commit Message 的格式

每次提交，Commit Message 都包括三个部分：`Header`，`Body` 和 `Footer`。

### 提交规范

```
# EN
<type>(<scope>): <subject>
<BLANK LINE>
<body>
<BLANK LINE>
<footer>

# CN
<类型>[可选的作用域]: <描述>
// 空一行
[可选的正文]
// 空一行
[可选的脚注]
```

**Header 是必需的**，Body 和 Footer 可以省略。

### 提交说明

```shell
# 标题行：50个字符以内，描述主要变更内容
#
# 主体内容：更详细的说明文本，建议72个字符以内。 需要描述的信息包括:
#
# * 为什么这个变更是必须的? 它可能是用来修复一个bug，增加一个feature，提升性能、可靠性、稳定性等等
# * 他如何解决这个问题? 具体描述解决问题的步骤
# * 是否存在副作用、风险? 
#
# 尾部：如果需要的化可以添加一个链接到issue地址或者其它文档，或者关闭某个issue。
```

### 提交样例

```shell
fix: correct minor typos in code
see the issue for details
on typos fixed.
Reviewed-by: Z
Refs #133
```



### Header

Header 部分只有一行，包括三个字段：`type`（必需）、`scope`（必需）和`subject`（必需）。

#### Type

type用于说明 commit 的类别，代表某次提交的类型。

英文，小写，可以有如下的一些类型，可以根据实际特殊要求做对应的扩展。

- 主要：

  - **feat**: 新增 feature

  - **fix**: 修复 bug


- 特殊：

  - **docs**: 仅仅修改了文档，比如 README, CHANGELOG, CONTRIBUTE等等

  - **style**: 仅仅修改了空格、格式缩进、逗号等等，不改变代码逻辑

  - **refactor**: 代码重构，没有加新功能或者修复 bug

  - **test**: 测试用例，包括单元测试、集成测试等

  - **chore**: 改变构建流程、或者增加依赖库、工具等


- 扩展：

  - **perf**: 优化相关，比如提升性能、体验

  - **revert**: 回滚到上一个版本

  - **build**：改变构建流程，新增依赖库、工具、构造工具的或者外部依赖的改动，例如webpack，npm

  - **ci**：自动化流程配置修改、与CI（持续集成服务）有关的改动

  - **impr**: improvement，小的代码设计改进

  - **apm**: 仅监控打点、异常日志处理相关

  - **jvm**: 仅JVM参数变更

  - **conf**: 仅配置变化，Spring配置、properties文件

  - **wip**: work in progress，少用，用于开发中的不完整提交，新工程开始时偶尔使用


> 如果type为feat和fix，则该 commit 将肯定出现在 Change log 之中。其他情况（docs、chore、style、refactor、test）由你决定，要不要放入 Change log，建议是不要。



#### Scope

英文，小写。用于说明 commit 影响的范围。

可以表示变更的包或模块范围，可多个组合，若涉及范围较大，可用 * 代替。比如数据层、控制层、视图层等等，视项目而定，例如格式为**项目名/模块名**



#### Subject

`subject`是 commit 目的的简短描述，建议不超过50个字符。

用来简要描述本次改动，概述就好了，因为后面还会在Body里给出具体信息。一般填写要求：

- 以动词开头，使用第一人称现在时，比如change，而不是changed或changes
- 第一个字母小写
- 结尾不加句号（.）



## 相关工具

### Commitizen

[官网](https://github.com/commitizen/cz-cli)

```shell
# 需要已安装 NodeJS
# 全局安装
npm install -g commitizen
```

`Commitizen`支持多种不同的提交规范，可以安装和配置不同的适配器实现。以`Conventional Commit`规范为例

```shell
# 安装 Adapter
$ npm install -g cz-conventional-changelog
# 配置
$ echo '{ "path": "cz-conventional-changelog" }' > ~/.czrc
```

安装完成后，查看是否在`package.json`中已加入`cz-conventional-changelog`信息。

安装完成后，使用`git-cz`替代`git commit`完成提交操作。

```shell
git cz
```



## 其他资料

[Git Guide](https://zj-git-guide.readthedocs.io/zh_CN/latest/message/%E5%BC%95%E8%A8%80/)

[Git-Commit-Log规范（Angular 规范）](https://www.jianshu.com/p/c7e40dab5b05)

[2020你应该知道的git commit规范](https://blog.51cto.com/u_15080031/2589463)

[美团 GIT Commit Log规范](https://cloud.tencent.com/developer/article/1762300)