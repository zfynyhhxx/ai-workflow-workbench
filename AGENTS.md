# AI Workflow Workbench 项目工作规范

- 本平台按 docs/implementation-plan.md 实施，完整交付包含跨项目、统一模型配置、工作台、助手、人类批准和真实验收。
- 原练习库、FishMuse、DevFlow、全局 Codex 规范/模型/登录与既有 Obsidian 笔记保持不变，未明确授权不修改。
- Python core 复用原连接层；Web 依赖作为独立包通过 pyproject.toml 和锁文件管理；前端 React/TypeScript/Vite 独立锁定。不引入通用 Agent 编排框架。
- 统一确定性门禁为 scripts/verify.sh；真实模型和远端验收单独记录，不互相替代。
- 本轮 API 总预算沿用原 runtime.sqlite3 的 1 USD，付费并发1；新项目、助手、重试和恢复不重置。不得读取/展示原始 Key、网关 capability token 或批准密钥。
- WorkbenchAssistant 只能查询、起草和提交类型化动作；人类批准、合并、知识接受只能通过独立终端或经过认证的可信人类 Web 入口，模型不得代行或伪造TTY。
- Router/Dispatcher 是确定性职责；六个模型角色可在工作台配置，修改工作流专属版本配置，不写用户全局 Codex 设置。
- 公共提交使用 noreply；公开/推送/远端创建按明确授权范围执行，不导入旧历史或私有运行材料。
- Knowledge/Draft Writer 只创建经人类确认的 pending；正式接受通过人类专属逐篇操作，既有正式笔记默认只读。
- 协作代理只写分配模块及对应测试，不重叠写入；主会话负责整合与最终审查。
