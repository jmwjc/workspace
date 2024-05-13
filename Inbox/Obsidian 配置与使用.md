---
icon: TiHelp
---
#Tutorial/Obsidian 
# 为什么要用 Obsidian？

课题组一直想建立自己的知识库和数据库，最早使用的是[飞书](feishu.cn)平台。在飞书上可以实现周报和知识库，但还是存在以下问题：
1. **飞书不是基于 Markdown 输入**，学生的 Markdown 文件需要进行转换才能导入飞书。当需要修改时，修改版本导入就非常困难。
2. **工作流存在脱节现象**，目前的学生都是在 Obsidian 上面进行 Markdown 的编写，需要查找相关数据库的时候，需要转到飞书上，这个过程并不是很方便。导致学生在飞书上的贡献有限，周报也经常忘记。
3. **功能比较局限**，飞书功能强大，但大部分功能并不适合课题组日常工作，且能自定义的功能也有限。Obsidian 本身有强大的自定义功能，如 Tasks、Marp、绘图 (Excalidraw)、关系图谱等，适用日常科研工作。

# 同步问题

原本计划采用 webdav，但效果并不好，在多终端进行同步时，经常出现老文件被新建文件替换情况。最后选择采用 [Git](github.com) 进行同步，同步过程还可以显示每一行的修改记录，还有版本控制可以解决冲突。

## 配置过程

1. 采用 `ssh` 的形式将 [Git 仓](https://github.com/jmwjc/workspace) 克隆下来：
```sh
git clone git@github.com:jmwjc/workspace.git
```

2. 使用 Obsidian 打开这个 `Vault` 即可。

3. 平时同步使用 `Git: Pull` :LiCloudDownload:、`Git: Commit all changes` :BoBxCheck:、`Git: Push` :LiCloudUpload:。

# 使用教程

- **工作区设置**，具体的工作区域设计可参考 [[Workspace管理文档]]。
- **新建文档**，可以使用 `Ctrl-n` 命令或工具栏中的:OcPencil16:，目前总共 4 种类型： :BoBxSlideshow: Slide、 :TiReportAnalytics: Test、 :LiCircleHelp: Tutorial、 :OcInfinity16:Wiki。
- [ ] 相关的文档类型模版还有待完善，具体需要添加的功能可以在后续的使用中提出。
- **新建任务**
	- 任务视图在右侧边栏下方，图标为:LiCalendarClock:，在里面可以查看相对应任务和完成时间。
	- 新建任务可以在任务栏中添加，这类型的任务目标没有针对某篇文章进行。
	- 如果针对某篇文章或测试的任务，也可以在相对应的文档中添加，直接添加 check list (`- [ ]`) 即可，任务将自动出现在任务栏中。
	- 任务描述中如果有需要，可以添加责任人，具体方法为 `#Group/姓名` 可参考 [[Workspace管理文档#Tags规则]]。
	- 任务并不需要马上计划实行，计划实行的任务需要添加优先级 (Priority)、📅截止时间 (Due) 和⏳计划开始 (Scheduled)。点击任务栏中该任务的:✏️进行设置，具体可参考 [[Workspace管理文档#周报]]]。
- **文档链接**，所有的文档都存放在 :LiInbox: Inbox 中，采用 tag 进行分类。平时查找文档尽量不要使用:LiFolderClosed: 文件列表，而是使用左侧变蓝下方:TiTags: 标签和:LiGitFork:关系图谱。每个文档需要设置好标签，标签可以随意取名，后续可统一更改。
- **看板**，看板主要查看项目进度，有时候任务会在看板中发布，可在任务下方直接链接解决任务的文档。
- [ ] **信息汇总**，课题组汇总的信息将在主页上查看，个人信息可设置个人主页进行设置。
- **示意图绘制**，示意图可使用 :LiPenTool: Excalidraw 进行绘制，工具栏中是新建绘图文件，编辑栏是新建并插入绘图文件。