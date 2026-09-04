# Prompt Optimizer Skill

将模糊、口语化或结构松散的需求整理为角色清晰、任务分层、输出明确、约束完整的结构化提示词，适合需要交给 Claude、Codex 或其他智能体执行的复杂任务。

## 优化框架

该 Skill 围绕五个问题重构提示词：

1. **Who**：智能体扮演什么角色，专业边界是什么。
2. **What**：核心目标与子任务是什么。
3. **How**：按什么顺序执行，每步产出什么。
4. **Constraint**：有哪些范围、质量和行为限制。
5. **Interaction**：遇到歧义时如何向用户确认或继续推进。

## 工作流程

- 诊断原提示词中的角色、目标、结构和输出缺口。
- 对会改变主体结构的关键信息逐题确认。
- 按角色定义、核心目标、任务拆解、输出规范和工作约束生成新版提示词。
- 必要时列出不影响主体结构的可选确认项。

## 安装

将本仓库完整放入：

```text
$HOME/.agents/skills/prompt-optimizer/SKILL.md
```

项目级使用时，也可以放入：

```text
<项目目录>/.agents/skills/prompt-optimizer/SKILL.md
```

Codex 通常会自动发现 Skill；如果没有出现，请重启 Codex。

## 使用示例

```text
$prompt-optimizer 帮我优化下面这段提示词：请分析这个项目并给我建议
```

```text
$prompt-optimizer 把这段口语化需求整理成可直接交给 Claude 执行的提示词
```

当用户直接提供一段复杂、模糊的任务描述并要求整理为 prompt 时，Codex 也可以根据 Skill 描述自动选择本 Skill。

## 仓库结构

| 路径 | 说明 |
| --- | --- |
| `SKILL.md` | 完整诊断流程、提问规则、输出模板和质量标准 |

## 输出特点

- 保留用户原始意图，不擅自扩大任务范围。
- 缺少关键输入时一次只询问一个问题。
- 将最终提示词放在独立代码块中，方便直接复制。
- 对未经确认的内容使用占位符，不把假设伪装成事实。

## 相关文档

- [Skill 主说明](./SKILL.md)
- [OpenAI：Build skills](https://developers.openai.com/codex/skills)
