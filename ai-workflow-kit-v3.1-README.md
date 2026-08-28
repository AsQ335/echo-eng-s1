# AI协作工作流套件 v3

## 目录说明

```
agent-workflow-protocol.md   核心协议
CLAUDE.md / AGENTS.md        项目根目录用，自动读取
skills/
  skill-a-需求澄清与定稿.md    含外部材料导入（两文件隔离+索引核对）、产品功能地图定位提示
  skill-b-设计探索与定稿.md
  skill-c-验收驱动开发.md
templates/
  PROGRESS.md                          必需
  01-requirements-v0.1.md              必需
  02-exploration-log.md                按需
  03-design-v0.1.md                    必需
  外源信息隔离区-采信说明模板.md        按需，不禁读
  外源信息隔离区-丢弃项模板.md          按需，禁读
  外源信息隔离区-索引模板.md            按需
  optional/
    00-环境约束.md
    decision-log.md
    产品功能地图.md
```

## 如何导入外部材料

在消息开头明确标注"外源模型信息"，AI会自动分级。若产生三级内容，会在 `docs/外源信息隔离区/` 下生成一对文件：`采信记录/`里的文件随时可查，`丢弃项-禁止读取/`里的文件本对话内AI不会再读，无论用户怎么要求，只能用户自己查阅或开新对话。

详细使用步骤见对话中的讲解。
