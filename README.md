# Prompt-Kit

Prompt Kit 是一套精心整理的实用提示词与可复用 Skill 模板套件，按使用场景归类。
汇集经过验证、开箱即用的大模型片段，帮助团队省去重复编写提示词的工作，快速获得稳定的 AI 输出。

## 目录结构

```
Prompt-Kit/
├── README.md
├── backend-evolution/         # 后端渐进式改造 Skill 与阶段提示词
│   ├── README.md
│   ├── SKILL.md
│   ├── STATUS.md
│   └── 阶段1~5 提示词.md
└── backend-frontend-sync/     # 前端先行、后端快速适配 Skill 与阶段提示词
    ├── README.md
    ├── SKILL.md
    ├── Example/README.md      # 填写示例与使用说明
    └── 主/阶段1~4 提示词.md
```

## 包含的 Skill

### 1. backend-evolution

适用于已有后端项目适配新页面、新接口、新业务流程的渐进式改造。特别适合微服务、新旧客户端并存、旧接口需要兼容的场景。

覆盖阶段：现状分析 → 需求映射 → 接口兼容与技术设计 → 实施计划 → 分批实施 → 回归验证。

使用方式：将 `backend-evolution/SKILL.md` 复制到后端项目的 `.cursor/skills/backend-evolution/SKILL.md`，按 `README.md` 中的步骤依次执行阶段提示词。

### 2. backend-frontend-sync

适用于前端先行、后端快速适配。前端项目只读，后端按任务范围定向修改，完成联调与回归。

覆盖阶段：环境识别与需求分析 → 接口映射与实施计划 → 定向实现 → 联调排错 → 交付与回归。

使用方式：将 `backend-frontend-sync/SKILL.md` 复制到后端项目的 `.cursor/skills/backend-frontend-sync/SKILL.md`，配合主提示词与分阶段提示词使用，填写示例见 `backend-frontend-sync/Example/README.md`。

## 快速开始

1. 选择与场景匹配的 Skill 目录。
2. 将对应 `SKILL.md` 放入后端项目的 `.cursor/skills/<skill-name>/SKILL.md`。
3. 阅读该 Skill 目录下的 `README.md`，按推荐顺序执行提示词。
4. 将生成的文档放入 `docs/` 下对应目录，持续增量更新接口映射与联调记录。

## 约定

- 提示词中的路径、接口、字段均需以真实代码为准，不得臆测。
- 前端项目默认只读，后端按确认范围修改。
- 分析阶段不修改业务代码，实施阶段需先确认方案。
- 测试结果必须真实记录，无法验证时明确说明阻塞点。
- 旧接口默认需要兼容，除非调用方与迁移计划已确认。

## 贡献

欢迎按使用场景新增 Skill 目录，每个目录建议包含：

- `README.md`：使用说明与推荐流程。
- `SKILL.md`：长期约束规则。
- 分阶段提示词文件。
- `Example/`：填写示例与使用说明（可选）。
- `STATUS.md`：任务跟踪模板（可选）。
