# AI协作工作流套件 v3

## 目录说明
```
agent-workflow-protocol.md   核心协议：九条原则、外部材料隔离机制、文件骨架与触发条件、自检/清算模板
CLAUDE.md / AGENTS.md        项目根目录用，自动读取，也重复了一遍隔离区的强制规则
skills/
  skill-a-需求澄清与定稿.md    含"导入外部材料"特殊入口 + 产品功能地图写入与定位提示
  skill-b-设计探索与定稿.md    含"是否需要探索"前置判断
  skill-c-验收驱动开发.md
templates/
  PROGRESS.md                          必需
  01-requirements-v0.1.md              必需，意图+需求+验收标准合一
  02-exploration-log.md                按需
  03-design-v0.1.md                    必需
  外源信息隔离区-丢弃项模板.md          按需，每次外部材料导入产生三级内容时用
  optional/
    00-环境约束.md                     按需
    decision-log.md                    按需
    产品功能地图.md                     按需
```

## 快速开始（最小路径）
1. 项目根目录建 `docs/`，放入 `agent-workflow-protocol.md`、`CLAUDE.md`（或`AGENTS.md`）、`PROGRESS.md`
2. 开始处理一个具体功能时，若已有《产品功能地图》，AI会先列出已确认模块供你定位；功能子目录**不会被AI默认自动建**——你自己手动建，或明确让AI帮你建，放入 `01-requirements-v0.1.md`、`03-design-v0.1.md` 两个模板
3. 按阶段把对应 `skills/*.md` 贴给对应工具（Claude Code会自动读CLAUDE.md，不用手动贴协议）
4. 真正触发对应条件时，才从 `templates/optional/` 或对应模板复制文件进项目

## 如何导入外部材料
在消息开头明确标注"外源模型信息"，贴上半成品需求文档/对话记录/提示词历史，AI会自动分级处理，不用你自己先筛选。三级丢弃内容存在 `docs/外源信息隔离区/` 下——**写入后，本对话内无论你怎么要求，AI都不会再读它**，只能你自己去看文件，或开一个全新的对话让AI读取。

详细使用步骤见对话中的讲解。
