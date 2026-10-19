# 来源、版本与证据

## 个人资料

创建日期：2026-10-19。原始资料位于用户提供的 docs-guide 文件夹；本技能仅含精选词表与重写指导，运行不依赖原目录。保留原手册不作修改。

| 原资料 | 本技能吸收位置 |
| --- | --- |
| manual-1-prompt-writing.md | field-guide.md 的三栏分工、结构与排除项 |
| manual-2-style-reference.md | palette.md 的流派与配器定位 |
| manual-3-keyword-library.md | palette.md 的演奏、情绪、律动和制作词 |
| manual-4-style-presets.md | palette.md 的套餐起点 |
| manual-5-scene-library.md | scenes.md 的 20 类场景选材 |
| manual-6-vocals.md | vocals-guofeng.md 的声线、唱法与编制 |
| manual-7-guofeng.md | vocals-guofeng.md 的民族乐器与局部戏腔 |
| manual-8-reference.md | 艺人参考转成可听见的特征；palette.md 的术语补充 |

## 社区 cookbook 归属

本技能参考并改编 MJorgin and the Suno v6 Cookbook contributors 的 [suno-v6-cookbook](https://github.com/MJorgin/suno-v6-cookbook)，快照提交 c8e40ff0b10636a7719cbc88bc5f58443ad19907，获取于 2026-10-19。

原文本许可为 [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)，原归属：Copyright (c) 2026 MJorgin and the Suno v6 Cookbook contributors。改编包括中文重写、个人词库融合、三栏输出、人声与国风补充、去除默认七段输出和强制模型/实验建议；不表示作者或 Suno 对本技能背书。来自该仓库的改编部分继续遵循 CC BY 4.0；此说明不替用户原始资料作额外授权。

重点参考（均在该提交下可追溯）：

- [Prompt Anatomy](https://github.com/MJorgin/suno-v6-cookbook/blob/c8e40ff0b10636a7719cbc88bc5f58443ad19907/docs/prompt-anatomy.md)：音乐、演唱与制作分工。
- [Chinese Lyrics](https://github.com/MJorgin/suno-v6-cookbook/blob/c8e40ff0b10636a7719cbc88bc5f58443ad19907/docs/chinese-lyrics.md)：自然断句、画面和双语呼吸。
- [Lyric and Section Tags](https://github.com/MJorgin/suno-v6-cookbook/blob/c8e40ff0b10636a7719cbc88bc5f58443ad19907/docs/lyric-and-section-tags.md)：结构与局部表演提示。
- [V5 to v6 Migration](https://github.com/MJorgin/suno-v6-cookbook/blob/c8e40ff0b10636a7719cbc88bc5f58443ad19907/docs/v5-to-v6-migration.md)：旧参数与通用音乐词的区别。
- [Failure Notes](https://github.com/MJorgin/suno-v6-cookbook/tree/c8e40ff0b10636a7719cbc88bc5f58443ad19907/library/failure-notes)：曲风漂移、hook 弱和咬字模糊的修正思路。

## 官方基线与不确定性

2026-10-19 核对的 [Suno 官方 v6 公告](https://suno.com/blog/introducing-v6) 发布于 2026-09-09，说明三款模型 v6、v6-wild、v6-mini，并介绍自然语言局部编辑、单句改词与多模态输入。该公告支持这些能力的存在，不证明本技能的具体提示词必定有效，也不是所有界面参数、字数限制的依据。套餐和当前开放情况需要另行核对。

用户询问模型时，可基于该公告作起点：目标明确优先考虑 v6；探索音色或意外方向可考虑 v6-wild；快速草拟可考虑 v6-mini。不要每次写歌都强制选择或声称某模型保证更准确咬字。

证据用法：

- `official`：官方明确说明的能力。
- `official-informed`：依据能力推导的编辑用法，效果仍需验证。
- `community-tested`：有输入、模型、日期、结果及可复现实验记录时才使用。
- `working-hypothesis`：本技能的写法、词表、示例与未经试听的修正建议。
- `legacy-v5`：明确来自旧版的规则。原个人资料版本不明时标“版本未注明”，不要凭空断定全部是 V5。

原手册中以下内容不作为 v6 硬规则：固定风格影响百分比、多样性数值、Max Mode 费用翻倍、所有标签必定识别、最多五类标签、拼音总是最有效、suona 基本无效、戏腔必须女声假声、国风必须三件套。保留音乐意图，具体响应以实际试听为准。

## 双声线标签的证据边界（2026-10-19）

- **官方已说明**：[Introducing v6](https://about.suno.com/blog/introducing-v6) 与 [What's new in v6?](https://help.suno.com/en/articles/13924801) 提及更强的音乐语言理解、局部自然语言编辑及 Replace Section；**未提供** `[Voice 1]`、`[Voice 2]`、`[Both]` 必定正确指派不同音色的正式解析规范。
- **社区可观察写法**：公开的 [v6 双人对白歌曲示例](https://suno.com/song/5945c3a2-41ea-4040-9cb2-aa11e4249af1) 使用 `Voice 1:` / `Voice 2:` 等标记；[2026-09-26 对唱讨论](https://www.reddit.com/r/SunoAI/comments/1wqhsbu/duets_alternate_voices_are_hard/) 有创作者反馈采用歌词分段标记，但也报告串位问题。这些不是本仓库的复现实验。
- **本技能的工作假设**：Style 声线定义 + Lyrics 独立 `[Voice 1]` / `[Voice 2]` / `[Both]` 是更易维护和试听的组织方式；采用短句英语节奏唱代替失真的中文念白，是针对用户需求的备选策略，**不代表**普通话说话或双声线能力有官方质量保证。
- 来源性质：官方功能称 `official`；未经试听的角色标签方案称 `working-hypothesis`，不得标作 `community-tested` 或声称 `100%` 成功。未来如果获得同一 Suno 版本下的输入、输出与试听记录，再更新判断。

## 原始文件指纹

用于确认本次整理依据，SHA-256：

- `manual-1-prompt-writing.md`：`35c793c8a5c0862f814de3c3612f63385e7b895d86ca252cfa4b45383f8da74e`
- `manual-2-style-reference.md`：`00de261312c821d5146b68bb599d3b19c494f4f4b939e62bd6036af856f1f7ec`
- `manual-3-keyword-library.md`：`a0a8cf90a5cf84b6d4434c310dc18e80143da3edc2e75a70a8f564b3d44e8d08`
- `manual-4-style-presets.md`：`83d445e932d53ed04b46ed962183177079706d1c53c0935cbcead52b35891e21`
- `manual-5-scene-library.md`：`b5d354d10affea8cd2ecf697eef45fbcdb15501943e7df91b68c69e5b6a63a0b`
- `manual-6-vocals.md`：`1f7f0ddec8ee78ec65f82fcff62ed22089e599f2ab61896d371142c19e045756`
- `manual-7-guofeng.md`：`d93996feefe8455f65d430896737175e9dadb4275198596677c86c79619fdf10`
- `manual-8-reference.md`：`eba5cdfbfa42dee2a2d008c6038ce11551625528e64bce118628d91e69c88302`
