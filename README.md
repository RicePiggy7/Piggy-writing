# Piggy-writing

一份帮助 AI 生成平实、准确、结构完整、易于阅读的中文和英文文案 Skill。

Piggy-writing 适用于博客、演讲稿、PPT 文案、网站与产品介绍、个人简介、公众号和社交媒体内容。它会根据材料和使用场景调整表达方式，减少空泛总结、刻意转折、含糊动作和模板化文案。

## 快速使用

安装 Skill 后，在写作任务中加入：
```
使用 $piggy-writing，把这份产品介绍改成可以直接发布的中文成稿。
```

也可以用于检查现有内容：
```
使用 $piggy-writing，检查这份 PPT 文案，保留技术细节，删除空泛标题和总结。
```

根据已有材料写作：
```
使用 $piggy-writing，按照我的材料写一篇博客，不要编造个人经历。
```

## 它解决什么问题

Piggy-writing 重点处理以下问题：

- 材料不足时虚构事实、经历、案例或来源。
- 第一人称、第二人称和群体称呼使用混乱。
- 动作与对象不匹配，句子缺少明确主语或处理过程。
- 标题为了制造节奏，添加材料没有支持的判断。
- 段落重复相同的数字、事实或结论。
- 使用“赋能”“闭环”“未来可期”等宣传化表达。
- 使用“搞顺”“跑起来”“承接需求”等含义不明确的动作。
- 添加没有信息的开场、转折、升华和结尾。
- 中文表达过度压缩，影响朗读和自然节奏。

## 核心规则

### 事实准确

- 只根据已有材料表达事实。
- 不编造个人经历、用户反馈、研究来源或情绪。
- 保留姓名、日期、数字、引用、链接、代码和产品名。
- 对来源中的数字和计算结果保持原有口径。
- 公开内容涉及第三方产品的负面评价时，先确认是否需要点名。

### 叙述身份

- 介绍 RicePiggy 自己的项目、做法和判断时使用“我”。
- 只有材料明确说明 RicePiggy 开发、制作、设计、新增或开源某个对象时，才使用“我做了”“我开发了”“我开源了”等所有权表达。
- 面向读者讨论一般情况时，根据语境使用“我们”或“大家”。
- 只有在明确指导某位读者，或原文已经使用第二人称时，才使用“你”。

### 语言表达

- 直接说明对象、事实、过程和判断。
- 优先使用准确的动词和清楚的对象。
- 保证主语、指代、因果关系和操作过程完整。
- 保留有助于口语节奏的必要虚词。
- 删除不影响原意的语气词、重复表达和填充句。
- 中文与英文、数字之间保留半角空格。

### 结构和标题

- 根据主题、过程和内容边界自然分段。
- 并列概念、操作步骤和检查项目适合使用列表。
- 标题直接说明内容，不额外添加口号、对仗或没有依据的判断。
- 内容说明完成后直接结束，不强行添加感悟或价值总结。
- 不为了排版制造固定段数、对称标题或连续短句。

## 安装

仓库中的 Skill 位于：
```
skills/Piggy-writing/
```

在 Codex 中，可以使用安装脚本：
```sql
python3 ~/.codex/skills/.system/skill-installer/scripts/install-skill-from-github.py \
  --repo <你的 GitHub 用户名>/Piggy-writing \
  --path skills/Piggy-writing
```

也可以手动安装：
```bash
git clone https://github.com/<你的 GitHub 用户名>/Piggy-writing.git
cp -R Piggy-writing/skills/Piggy-writing ~/.codex/skills/piggy-writing
```

安装完成后，使用 $piggy-writing 调用。

## 文本检查

Skill 附带一个只使用 Python 标准库的检查脚本：
```
python3 skills/Piggy-writing/scripts/tone_lint.py draft.md
```

运行自测：
```swift
python3 skills/Piggy-writing/scripts/tone_lint.py --self-test
```

检查结果分为两类：

- `FAIL`：已经确认的问题，脚本会返回失败。
- `WARN`：需要结合上下文判断的表达，不会单独导致检查失败。

脚本只能识别已经配置的表达模式，无法判断事实是否真实，也不能替代完整通读。

## 自定义

可以根据自己的写作习惯调整：
```swift
skills/Piggy-writing/SKILL.md
```

适合个性化的内容包括：

- 第一人称和读者称呼。
- 主要内容渠道。
- 语气、句子长度和口语程度。
- 标题和结尾习惯。
- 个人常用词和禁用表达。
- lint 脚本中的检查规则和测试样例。

## 仓库结构
```bash
Piggy-writing/
├── assets/readme/hero.svg
├── skills/Piggy-writing/
│   ├── agents/openai.yaml
│   ├── scripts/tone_lint.py
│   └── SKILL.md
├── LICENSE
└── README.md
```

## 许可证

本项目使用 MIT License，详见 LICENSE。
