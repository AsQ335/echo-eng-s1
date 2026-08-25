# AI协作工作流套件 Lite v0.1

比完整版精简的地方：意图还原并入需求定稿（少一个文件）；探索循环加了前置判断，大部分MVP功能会跳过分支/清算机制；环境约束、需求池、决策日志三个项目级文件改成按需创建，不再预先搭建空文件；新增CLAUDE.md/AGENTS.md指针文件，省去每次手动提醒工具"先读协议"。

## 目录说明
```
agent-workflow-protocol.md   核心协议：八条原则、文件骨架与按需创建触发条件、自检/清算模板（唯一定义处）
CLAUDE.md                    项目根目录用，Claude Code自动读取，指向协议文件
AGENTS.md                    项目根目录用，供支持同类约定的工具自动读取
skills/
  skill-a-需求澄清与定稿.md    用于 Claude网页端 或 Claude Code
  skill-b-设计探索与定稿.md    用于 Claude Code，含"是否需要探索"前置判断
  skill-c-验收驱动开发.md      用于任意编码agent
templates/
  PROGRESS.md                 项目根目录，跨工具公共状态文件（必需）
  01-requirements-v0.1.md     复制到每个功能子目录，意图+需求+验收标准合一（必需）
  02-exploration-log.md       复制到功能子目录，仅Skill B判断需要探索时才用（按需）
  03-design-v0.1.md           复制到每个功能子目录（必需）
  optional/
    00-环境约束.md             按需创建，触发条件见协议第三节
    需求池.md                  按需创建，触发条件见协议第三节
    decision-log.md            按需创建，触发条件见协议第三节
```

## 快速开始（最小路径）
1. 项目根目录建 `docs/`，把 `agent-workflow-protocol.md`、`CLAUDE.md`（或`AGENTS.md`）、`PROGRESS.md` 放进去
2. 每次做新功能，在 `docs/` 下建一个功能子目录（如 `docs/会员积分/`），把 `01-requirements-v0.1.md`、`03-design-v0.1.md` 复制进去——这两个文件是唯一必需的功能级文件
3. 按阶段顺序，把对应 `skills/*.md` 的内容贴给对应工具使用（若用Claude Code，CLAUDE.md会自动被读取，不需要手动贴协议内容）
4. 只有真正触发对应条件时，才从 `templates/optional/` 或 `templates/02-exploration-log.md` 复制对应文件进项目——不要提前建好占位

详细使用步骤见对话中的讲解。
