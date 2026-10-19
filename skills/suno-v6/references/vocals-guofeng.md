# 人声、国风与戏腔

## 人声三层

| 层次 | 可选词 | 放置方式 |
| --- | --- | --- |
| 声线/音区 | warm baritone, clear tenor, rounded mezzo, airy alto, husky midrange | Style 中选择适合的一组 |
| 演唱动作 | conversational phrasing, restrained vibrato, breathy verse, controlled falsetto, sustained endings | 全曲习惯放 Style，局部变化放对应段落 |
| 编制 | solo lead, male and female duet, subtle doubled chorus, call and response, layered harmonies | 明确主唱与和声谁在何时出现 |

`breathy` 不等于远距离大混响；`airy` 不必牺牲清晰度。和声多时可让 `upfront lead, backing harmonies tucked behind` 明确层次。别把所有女声写成甜美、所有男声写成沙哑；声线由创作需求决定。

对唱或多角色演唱应优先给角色固定身份，再安排段落。性别标签 `[Male Vocal]` / `[Female Vocal]` 可作局部提示；需要明确角色时，可尝试下述编号方案。

## v6 双声线：Style 定义、Lyrics 调用（工作假设）

将**声线身份**、**演唱动作**和**谁在何处唱**分开写。此方案是可试听的社区提示词惯例，`[Voice 1]`、`[Voice 2]`、`[Both]` **不是经官方确认的专用声轨语法**，不能保证准确绑定音色；不应把 `Q-voice`、`少女版` 等内部角色昵称误当作稳定的切换标签。

**Style 里先定义声线与职责（示例，需融入实际曲风，不必原样照抄）：**

```text
Two distinct female vocal characters.
Voice 1: youthful clear mezzo-soprano, expressive native Mandarin pop singing, warm tone, melodic legato and light head-voice lifts.
Voice 2: distinctly higher and lighter bright female voice, mischievous crisp English spoken-sung responses, short rhythmic phrases.
Voice 1 leads Mandarin verses and choruses; Voice 2 handles tagged English replies. Both harmonize only in tagged sections.
```

**Lyrics 再用相同编号调用：**

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
[Voice 1]
Click, click, click!
[Voice 2]
Who's typing?

[Final Chorus]
[Both]
别回头！别回头！
```

- **同一首歌编号保持不变**：不要在某段突然把 Voice 1 写成小助手，或让 Voice 2 接管主唱而不交代。
- **优先按整段或完整短句切换**：同一行内反复插入角色名更容易串位、跳词，且角色说明有机会被唱出来。
- **声线要真正可区分**：指定音域、明亮/温厚程度、音节密度和演唱动作；只写两次 `cute female vocal` 区分度低。
- **唱法另标注**：`[Rhythmic chant]`、`[Soft spoken]`、`[Harmony]` 只说明怎么演，不是 Voice 身份；简短且仅放需要的段落。
- **英文念白只在用户愿意时使用**：用户反馈中文唱歌正常、中文口语含糊，可尝试“中文唱 + 英文 spoken-sung 短句”；不要擅自把所有中文改成英文。
- **可选格式 A/B**：一些创作者使用 `[Verse 1: Voice 1]` 或 `[Verse 1 - Voice 1]`；与独立 `[Voice 1]` 均需试听对照，不要宣称哪个是官方标准。
- **合唱不等于身份锁定**：`[Both]`、`[Duet]`、和声说明可能被模型忽略；先让主唱建立身份，第二声线再回应。
- **篇幅控制**：实际 Style 若有长度限制，先保留角色差异、语言分工和主曲风，删掉重复形容词，不保证仅因标签就能准确切换。

首次测试先用两段声音对比明显的短样例，检查是否真正出现两种声线、语言是否正确、角色是否串位。连续失败时减少切换频率；已有满意成品可尝试局部编辑或分轨重录，不把整首重生成当作唯一方案。参见 [试听后修正](repairs.md) 和 [双声线示例](examples.md#双声线中英互动万圣节数字怪谈)。

## 国风从声音与叙事落地

国风可以是传统、小编制、流行融合或电子融合，不要求每首都同时有五声音阶、民族乐器与戏腔。先确定走向，再选择需要的元素：

| 角色 | 选材 |
| --- | --- |
| 清亮弹拨主线 | guzheng flowing arpeggios、pipa tremolo |
| 克制留白 | sparse guqin plucks、breathy xiao responses |
| 抒情拉弦 | lyrical erhu lead、zhongruan accompaniment |
| 明亮吹管 | dizi melodic phrases、sheng harmonic support |
| 仪式与武戏 | Chinese barrel drums、gongs、wooden clappers |
| 喜庆吹打 | suona lead、Chinese percussion；识别失败再试听替代方案 |

- 主奏与陪衬分工，别把乐器表一次塞满。`guqin and xiao, sparse arrangement` 可以胜过七八件乐器同时争主旋律。
- `Chinese pentatonic melodic color` 是可选旋律倾向，不代表所有中国音乐只有同一种五声音阶，也不保证严格音阶控制。
- 要编钟可写 `bianzhong bronze bells`，锣写 `gong`；太鼓 `taiko` 与中国大鼓不是同一乐器。尺八和呼麦也不作为所有中国传统音乐的通用代称。
- 原手册对 `suona` 无效的结论缺少 v6 复现实验，先保留用户要的真实乐器。`dizi + trumpet` 只可作为经用户接受的近似替代，不能称为唢呐等价音色。

## 戏腔局部安排

先区分戏曲风格、戏腔点缀与高音假声，它们不能互相替代。用户仅要古风，不默认加戏腔；用户点名昆曲、京剧等时，使用对应唱腔和配器描述，不一律写成 `Beijing opera`。

一种可试的对比：Style 写 `natural Mandarin verses, brief Chinese opera-inspired ornaments in the final chorus, clear diction`；末段副歌加 `[Chinese opera-inspired ornamentation]`。戏腔不限女声，也不必全程高音；少量旋律装饰通常更符合“点缀”的要求。

古风歌词半文半白可以，但保持语法与故事清楚。韵脚按实际读音核对，例如“远”不是普通话 `an` 韵的直接等价项；不要照字形凑韵。江湖、故乡、离别都应落到人物动作，别每首重复“明月、霜、千年”。
