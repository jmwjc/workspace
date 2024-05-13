---
icon: OcGear16
---
#Group/吴俊超   #Tutorial
# 工作区流
- [x] 添加测试结果  [completion:: 2024-05-10]
- [-] 快速添加测试报告  [cancelled:: 2024-05-10]
- [x] 快速添加周报  [scheduled:: 2024-05-10]  [due:: 2024-05-14]  [completion:: 2024-05-11]
- [ ] 快速添加问题  [scheduled:: 2024-05-11]  [due:: 2024-05-13] #Group/吴俊超 
- [ ] #TODO 自定义工具栏  [scheduled:: 2024-05-11]  [due:: 2024-05-13]
- [ ] 快速添加idea
- [ ] 快速制作汇报ppt
- [ ] 自动添加记录
- [-] 自动添加标签  [cancelled:: 2024-05-10]
- [ ] Dashboard
- [ ] 汇总数据
- [ ] 实用工具
- [ ] 帮助文档
- [ ] Obsidian基本配置说明
# 实现插件
- [ ] 快速插入: Quickadd+buttons+meta bind
- [ ] 测试报告: tasks+tasks bar+quickadd+templater
- [ ] 图片管理: attachment manager
- [ ] 数据汇总: dataview

# 快速输入
主要实现功能
- [ ] 功能栏: Editing Toolbar
- [ ] 快速插入 Excalidraw: 嵌入在 Editing Toolbar
- [ ] 快速插入 Task
- [ ] 快速插入图片

# 工作流
## 周报
### 流程
1. 由老师添加任务，任务类型分为 2 种：有责任人；无责任人。有责任人的在任务中有明确引用学生，如 `[[姓名]]`，反之则任何人都可以认领；
2. 认领的过程在 `Tasks Timeline` 中点击✏️，设置优先级 (Priority)、截止时间 (Due)📅 和计划开始 (Scheduled)⏳。如果是无责任人任务，可在描述(Description)中添加自己的姓名引用 `[[姓名]]`；
3. 每周日填写复盘报告。
### 周报内容
1. 本周规划了哪些事情，完成了哪些事情？
2. 做的好的是什么，怎么保持？
3. 需要停止的事情是什么，怎么改善？
4. 需要开始做的事情是什么，怎么提高行动？
5. 发现了哪些问题，总结出了什么经验？
6. 本周感悟和启发？
7. 下周计划？

# 自定义工具栏

工具栏设置主要遵循就近原则，具体为
1. 新建、排序文档类都放置在文件管理器，位于左侧工具栏上方；
2. 文本操作类放置在 `Editor bar`；
3. 关系图谱放置在左侧工具栏下方；
4. 任务相关工具放置在右侧工具栏下方；
5. 其余工具放置工具栏右上方。

# Tags规则
利用 Tag Wrangle 插件进行多层次标签设置，并利用 Dataview 统计数据、制作帮助文档。
1. Tutorial
2. Group
	1. 姓名
3. Research field
4. Tasks: TODO/FIXME