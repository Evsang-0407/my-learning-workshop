# my-learning-workshop

个人概念学习工作台：一个可复用的**概念学习资料生成 Skill**（`concept-study-materials`），以及由它生成并经本人核查的**学习资料**。本仓库是《统计与数据分析》课程作业 1 的交付物，也是后续课程项目的个人工具基础。

## 仓库用途

- 把"如何学习一个新概念"沉淀成标准化的 Skill，避免每次重复交代资料格式；
- 生成并持续积累高质量的概念学习资料（学习目标、个人解释、机制、场景、辨析、边界、自测、可核查来源）；
- 作为个人作品集：展示 AI 工具链（Agent / 上下文 / Skill）的实际运用能力。

## 目录结构

```
my-learning-workshop/
├── .workbuddy/
│   └── skills/
│       └── concept-study-materials/     # 项目级 Skill
│           ├── SKILL.md                  # Skill 本体：场景/输入/步骤/输出/来源要求/自检要求
│           └── assets/
│               └── material-template.html  # 学习资料 HTML 模板
├── learning-materials/
│   ├── agent.html                       # 概念一：Agent（智能体）
│   ├── llm-context.html                 # 概念二：大模型的上下文
│   ├── skill.html                       # 概念三：Skill（AI 智能体的技能）
│   ├── concept-relationship.html        # 三者关系（含关系图）
│   └── concept-relationship.md          # 同上的 Markdown 版（含 Mermaid 源码）
├── README.md
└── .gitignore
```

## Skill：concept-study-materials

- **存放路径**：`.workbuddy/skills/concept-study-materials/SKILL.md`（项目级，随仓库共享）
- **作用**：接收任意一个概念作为学习主题，按固定的九部分结构生成学习资料——学习目标、核心问题、我的解释（个人化语言）、核心机制与组成、具体应用场景、概念辨析、使用边界、自测问题（答案折叠）、参考资料（逐条核实、注明支撑点与核实日期），输出为 HTML 保存到 `learning-materials/`。
- **内置约束**：至少 3 条来源且含学术/官方文档；每条链接必须实际访问核实；"我的解释"禁止整段照搬来源。

### 如何在 WorkBuddy 中调用

1. 在 WorkBuddy 中打开本仓库（将仓库目录作为工作区）；
2. 直接在对话中说：**"帮我学习 XX 概念"**（如"帮我学习假设检验"）；
3. WorkBuddy 会根据 Skill 的 name/description 自动匹配并加载 `.workbuddy/skills/concept-study-materials/`；
4. 也可以显式触发：`/concept-study-materials 假设检验`；
5. 生成结果保存在 `learning-materials/`，打开 HTML 即可阅读，自测答案点击展开。

## 已生成的学习资料

| 文件 | 概念 | 核查状态 |
|------|------|----------|
| `learning-materials/agent.html` | Agent（智能体）：自主决策循环、四组件（大脑/规划/记忆/工具）、与 workflow/Chatbot/RPA 的辨析 | AI 初稿，待人工核查 |
| `learning-materials/llm-context.html` | 大模型的上下文：token 与自注意力机制、窗口内容构成、"迷失在中间"、应对策略 | AI 初稿，待人工核查 |
| `learning-materials/skill.html` | Skill：SKILL.md 结构、渐进式披露三级机制、用户级与项目级、开放标准 | AI 初稿，待人工核查 |
| `learning-materials/concept-relationship.html` / `.md` | 三者关系：上下文是 Agent 的现场与第一约束；Skill 沉淀可复用知识并拓展 Agent 边界 | AI 初稿，待人工核查 |

## AI 使用与人工核查说明

**AI 参与的部分：**
- 借助 AI（WorkBuddy Agent）完成：仓库创建与克隆、Git 命令、Skill 结构设计、三份学习资料与关系说明的初稿生成、来源链接的逐一访问核实。

**我人工核查的部分（核查通过后更新各资料页顶的"核查状态"徽章）：**
1. **来源核查**：逐条打开所有参考链接，确认内容存在、确实支撑正文论断（生成时已由 AI 逐条访问过一次，2026-09-04）；
2. **内容核查**：逐节阅读"我的解释"部分，确认与自己的理解一致、无事实错误，修改措辞使其真正"像我自己说的话"；
3. **技术细节复核**：如上下文窗口的具体数字均标注了数据时点（IBM 文章截至 2024-10），确认正文没有把它们当作永恒事实；
4. **结构调整**：根据阅读体验增删小节、调整自测题目难度；
5. **敏感信息检查**：确认仓库内无 API Key、密码、个人隐私信息（`.gitignore` 已配置排除规则）。

**AI 使用规范**：概念解释均为个人语言重写，不整段照搬 AI 对话结果；所有来源真实可查，无伪造；AI 生成的初稿在仓库提交记录中可追溯。

## 后续计划

- [ ] 用本 Skill 学习后续课程概念（如假设检验、回归分析），继续扩充 `learning-materials/`；
- [ ] 根据实际使用体验迭代 Skill（如增加"学习路径"小节、间隔复习卡片生成）；
- [ ] 尝试为本仓库新增其他学习类 Skill（如"习题讲解""数据集探索"）。

---

*仓库所有者：[Evsang-0407](https://github.com/Evsang-0407) · 创建于 2026-09-04*
