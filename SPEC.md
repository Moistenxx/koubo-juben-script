# Spec: 口播剧本 Skill

## Objective

给定用户提供的一个 Skill，先识别它的主题、用途、输入、输出和限制，再完成 Deep Research 中文调研，最后生成约 2 分钟、只含口播文字的中文 Skill 教学稿。

## Required behavior

- 调研顺序固定为 `research-zh/research`、`research-deep`、`research-report`。
- 叙事顺序固定为：直接痛点、Skill 方案、成品展示、以“首先”开始的安装/调用/提供材料/确定生成四步、注意事项、价值回扣和开源 CTA。
- 第一段禁止以成品、工具、模型或提问式话术开场。
- 不讲 AI 原理、智能体互打或内部协作；教程保持短而完整。
- 默认约 2 分钟，建议 320—450 个中文汉字，可按语速微调。
- 只输出口播文字，不输出分镜、拍摄、剪辑、字幕、发布方案或研究报告。
- 事实、判断和待核实信息必须分开；不得编造结果、数字或来源。
- Skill 名称、主题和成品必须从当前输入动态替换。

## Verification

使用 `skill-creator/scripts/quick_validate.py` 检查 frontmatter、命名和未完成占位符；再用静态检查确认文件包含 Skill 识别、Deep Research 前置、约 2 分钟、痛点优先、四步教程和“只输出口播文字”等约束。
