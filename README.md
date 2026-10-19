# Suno v6 Prompt Studio

把一个主题、一段画面或已有歌词，变成可直接粘贴到 Suno 的 **Style、Lyrics、Exclude**。

面向中文创作者的 Agent Skill，融合个人提示词资料与 [Suno v6 Cookbook](https://github.com/MJorgin/suno-v6-cookbook)，支持中文原创、英文与双语歌词、国风戏腔、纯音乐，以及试听后的提示词修正。

> 这是帮助 AI 助手写提示词与歌词的技能，生成的是文本；实际音频需要在 Suno 中生成。本项目为独立个人项目，与 Suno 无官方关联。

## 安装

需要本机可用的 Node.js 与 `npx`。通过 [Vercel Skills CLI](https://github.com/vercel-labs/skills) 安装，无需发布 npm 包。

### 一条命令安装

```bash
npx skills add Inupedia/suno-v6-prompt-studio --skill suno-v6
```

按提示选择目标 AI 助手和安装范围。默认安装到当前项目；加 `-g` 可安装到用户目录。

### 全局安装到 Codex

```bash
npx skills add Inupedia/suno-v6-prompt-studio --skill suno-v6 -a codex -g
```

### 安装到 Claude Code

```bash
npx skills add Inupedia/suno-v6-prompt-studio --skill suno-v6 -a claude-code -g
```

需要跳过交互确认时，在安装命令末尾加 `-y`。安装后在目标助手的新会话中使用技能；不同助手的显式调用方式可能不同。

### 先查看技能

```bash
npx skills add Inupedia/suno-v6-prompt-studio --list
```

仓库名是 `suno-v6-prompt-studio`，实际安装与调用的技能名是 **`suno-v6`**。

## 使用

在 Codex 中可以显式调用：

```text
$suno-v6 写一首雨夜告别的中文歌，克制男声，钢琴为主，副歌抓耳，不要说唱。
```

也可以给出已有歌词、场景、配器、人声方向或生成结果的问题。说明越具体，结果越贴合；没想好曲风时，给一个主题也能开始。

| 想做什么 | 示例请求 |
| --- | --- |
| 中文原创 | 写一首毕业后回到老街的歌，温暖但不煽情，木吉他与轻鼓，完整三栏。 |
| 保留已有歌词 | 以下歌词一个字别改，只加段落标签，配温暖男声的 Style 和 Exclude。 |
| 国风点缀戏腔 | 渡口送别，古筝与箫，主歌自然演唱，只在末段副歌加一点戏腔。 |
| 双语歌曲 | 中文主歌、英文短句副歌，深夜城市 R&B，避免在一句中频繁切换语言。 |
| 双声线角色对唱 | Style 分别定义 Voice 1 / Voice 2，Lyrics 按段落分配，中文主唱与英文短句互动。 |
| 纯音乐 | 清晨咖啡馆，木质温暖的 bossa nova，不要人声与哼唱，给器乐结构。 |
| 试听后修正 | 人声太远、副歌太平，保留歌词，修改 Style 和 Exclude。 |
| 局部改词 | 只重写第一遍副歌，让核心句更好记，其他部分保持原样。 |

## 输出长什么样

默认按以下顺序给出三个独立代码块，可以分别复制到 Suno 对应字段。Style 与 Exclude 默认使用英文，Lyrics 默认中文，也可指定其他语言。

**Style**

```text
Intimate Mandopop ballad, slow steady pulse around 74 BPM, sparse piano arpeggios with warm acoustic guitar, rounded male baritone singing clear Mandarin with conversational phrasing. Brushed drums enter in the chorus, gentle cello answers between lines. Restrained verses open into warmer chorus harmonies, then resolve to piano alone. Upfront lead vocal, short room reverb, soft low end.
```

**Lyrics**

```text
[Verse]
窗沿的雨敲了半晚
你的杯子还放左边
我把凉掉的茶换暖
又听脚步停在楼前

[Chorus]
把灯留到天亮
让你看见家的方向
有些话不急着讲
先把雨留在门外吧
```

**Exclude**

```text
screaming, aggressive EDM drops, heavy vocal reverb, robotic vocal processing
```

这里展示一个主歌与副歌片段。完整情歌、国风与纯音乐示例见 [examples.md](skills/suno-v6/references/examples.md)。如果只要某一栏或一句改词指令，技能会按请求缩小输出范围。

## 双声线：定义音色，再分配演唱

想让少女主唱和俏皮的第二个角色轮流唱，不建议只在 Lyrics 写 `[Q-voice]`。可以试用成对的角色标签：

**Style** 中写角色音色和语言职责：

```text
Voice 1: youthful clear female mezzo-soprano, expressive native Mandarin pop singing.
Voice 2: lighter higher bright female voice, crisp English rhythmic spoken-sung responses.
Voice 1 leads Chinese verses and choruses; Voice 2 handles English call-and-response.
```

**Lyrics** 里复用相同编号：

```text
[Chorus]
[Voice 1]
别回头！别回头！
屏幕里的我在招手

[Post-Chorus]
[Call and Response]
[Voice 1]
Knock, knock, knock!
[Voice 2]
Wasn't me!

[Final Chorus]
[Both]
别回头！别回头！
```

`[Voice 1]` / `[Voice 2]` / `[Both]` 是**待试听的社区提示词习惯**，不是 Suno 已公开保证的精确声轨分配语法。音色若混淆，减少切换次数并先试听短段；中文念白如果失真，在用户同意下可试英文短句节奏唱，保留效果良好的中文旋律。完整规则见 [人声与国风](skills/suno-v6/references/vocals-guofeng.md#v6-双声线style-定义lyrics-调用工作假设)，也有 [可复制的三栏示例](skills/suno-v6/references/examples.md#双声线中英互动万圣节数字怪谈)。

## 创作方式

- **三栏互相配合**：Style 定整首声音方向，Lyrics 写歌词与局部段落变化，Exclude 排除真正冲突的元素。
- **先可唱，再堆氛围**：中文歌词关注自然语序、换气、叙事推进和副歌记忆点；不会默认给整曲加拼音。
- **尊重已有歌词**：只要求编排时保留原文字词，获得改写要求后再润色或续写。
- **按需读取资料**：入口简短，曲风词库、人声、国风、场景配乐与修正方法分开存放。
- **区分经验与能力**：提示词、标签、BPM、音色及局部保留均需试听验证；不把旧界面参数或社区经验当作官方保证。

技能可以直接处理普通创作请求，不需要 Suno API key、账号密码或音频生成依赖。当前产品功能与套餐问题应另查官方资料。

## 仓库结构

```text
skills/suno-v6/
├── SKILL.md                    # 技能入口与三栏交付规则
├── agents/openai.yaml          # Codex 展示信息
└── references/
    ├── field-guide.md          # Style / Lyrics / Exclude 写法
    ├── lyrics-guide.md         # 中文、英文与双语可唱性
    ├── palette.md              # 曲风、配器、情绪、制作词库
    ├── vocals-guofeng.md       # 声线、演唱、国风与戏腔
    ├── scenes.md               # 20 类场景的精选声音素材
    ├── repairs.md              # 试听后修正与局部编辑
    ├── examples.md             # 三栏完整示例
    └── sources.md              # 来源、改编说明与证据边界
```

这是 Markdown 技能仓库，不需要 `npm install` 或构建。`npx skills` 从 GitHub 发现并安装 `skills/suno-v6/SKILL.md` 及同目录资源。

## 来源与署名

本项目综合了个人提供的 8 份提示词手册，并参考、改编：

- [MJorgin/suno-v6-cookbook](https://github.com/MJorgin/suno-v6-cookbook)，作者为 MJorgin and the Suno v6 Cookbook contributors，原文本采用 [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)。
- [Suno 官方 Introducing v6 公告](https://suno.com/blog/introducing-v6)，用于核对版本能力，不作为具体提示词必定有效的证明。

主要改编为中文重写、个人词库融合、三栏输出、国风与人声补充，以及将经验建议与官方能力区分。来源提交、改编范围和原资料指纹见 [sources.md](skills/suno-v6/references/sources.md)。来自 cookbook 的改编部分遵循其 CC BY 4.0 要求；本说明不对其他来源材料额外授予许可。

示例歌词为本项目整理过程中原创；尚未在 Suno 中进行音频生成或试听验证。创作时使用原创或有权使用的内容，不将提示词效果描述为真实人物音色复刻。
