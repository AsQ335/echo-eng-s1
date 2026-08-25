# 项目协作说明（供支持自动读取项目指令文件的工具使用，如Codex等）

本项目遵循 `docs/agent-workflow-protocol.md` 定义的工作流协议。开始任何任务前，请依次读取：
1. `docs/agent-workflow-protocol.md`
2. `docs/PROGRESS.md`
3. 当前处理的功能目录下的相关文档（如 `docs/<功能名>/01-requirements-v0.1.md`）

然后按协议中对应阶段的Skill行为规范（见 `docs/skills/`）执行，不需要用户每次手动提醒。

若你的工具不自动读取本文件，请在每次会话开始时手动说："先读 AGENTS.md（或 CLAUDE.md），再开始工作"。
