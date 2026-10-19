# Style、Lyrics、Exclude 写法

以下是创作启发与待试听方案，不是官方字段解析协议。

## Style：写出可以听见的差异

可参考这个顺序，但不必填满：主曲风 → 律动/速度 → 核心配器与演奏 → 人声 → 段落动态 → 混音空间。

- 以一种主曲风为中心，融合另一种时说明谁管节奏、谁管和声或音色。
- 情绪落到音乐动作：克制可以是 `sparse verse, close vocal`；释怀可以是 `warmer final chorus, open harmonies`，不用堆满 `dreamy, magical, beautiful`。
- 乐器指定角色：`fingerpicked guitar leads the verses, cello answers between phrases` 比仅列乐器名更明确。通常选少数核心音色，编制大小服从目标。
- 人声分声线、唱法、编制：`warm male baritone, conversational verses, restrained chorus harmonies`。双角色时在 Style 中明确 `Voice 1`、`Voice 2` 的**音色差异与各自职责**，再在 Lyrics 中复用相同编号，细节见 [人声与国风](vocals-guofeng.md#v6-双声线style-定义lyrics-调用工作假设)。
- 混音只写目标：`upfront lead, short room reverb, rounded low end`。摇滚可以保留吉他失真，lo-fi 可以保留磁带纹理。
- BPM 是速度目标，不承诺锁定。用户没给拍号/调性就不必凭空补一套理论参数。
- 用段落范围化解冲突：`dry lead in verses, airy backing harmonies in the chorus` 可以共存；全曲同时要求 `dry vocals` 与 `huge vocal reverb` 就需要调整。
- 最重要的特征放前面便于识别，不宣称存在固定权重、截断位置或必定响应。

## Lyrics：区分唱的字与演的方式

常用骨架按歌曲需要删改：`[Intro]`、`[Verse 1]`、`[Pre-Chorus]`、`[Chorus]`、`[Verse 2]`、`[Bridge]`、`[Outro]`。不强制每首歌都有桥段、转调、间奏。

段落标记单独成行；可用下一行的短提示：

```text
[Verse 1]
[Intimate delivery]
窗沿的灯还亮着
你的杯子仍在左侧

[Chorus]
[Warmer harmonies]
把灯留到天亮
等一句平常的晚安
```

这种分行方式是本技能的统一习惯，不宣称其他标签格式无效。`[Final Chorus]`、`[Key Change]`、自由描述提示等都按意图使用，不能保证自动升调或换声。双角色可尝试在段落下另起一行加 `[Voice 1]` / `[Voice 2]`，合唱使用 `[Both]`；它们属于提示词约定，并非官方保证的声轨控制标签。括号内的字也可能被唱出来，少量短提示比长段舞台说明更稳妥。

器乐结构保持简短，例如 `[Intro]`、`[Instrumental]`、`[Outro]`；具体段落演奏可各加一个简短提示。Style 写 `instrumental`，Exclude 可写 `lead vocals, spoken word, choir, vocal chops`。只在需要时提醒用户启用当前界面可用的器乐选项，不保证一句 `There is no vocal present.` 就能消除所有人声。

## Exclude：只排除真实冲突

| 目标 | 可考虑的排除项 | 别误伤 |
| --- | --- | --- |
| 贴耳、清楚的自然主唱 | heavy vocal reverb, robotic vocal processing, excessive melisma | 少量空间感、正常换气 |
| 轻柔钢琴情歌 | screaming, aggressive EDM drops, distorted guitar riffs | 副歌适度打开 |
| 复古 lo-fi | glossy EDM leads, aggressive limiting | tape hiss、轻饱和是目标的一部分 |
| 吉他摇滚 | trap hi-hat rolls, glossy dance-pop synths | distortion 不应默认排除 |
| 古风小编制 | festival drops, heavy trap drums | 现代融合若是用户要求应保留 |

这些是候选词，不是全选清单。避免 `bad music, low quality` 等无法清楚指向声音的泛词；不要通过空泛排除承诺母带质量。
