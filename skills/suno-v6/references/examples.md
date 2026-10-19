# 三栏交付示例

以下为原创文本示例，未在 Suno 中生成或试听。只展示如何使三栏一致，不是固定模板；结构和长度随用户需求调整。示例代码块都可独立粘贴。

## 中文流行情歌：雨夜等一个人，克制男声

Style

```text
Intimate Mandopop ballad, slow steady pulse around 74 BPM, sparse piano arpeggios with warm acoustic guitar, rounded male baritone singing clear Mandarin with conversational phrasing. Brushed drums enter in the chorus, gentle cello answers between lines. Restrained verses open into warmer chorus harmonies, then resolve to piano alone. Upfront lead vocal, short room reverb, soft low end.
```

Lyrics

```text
[Intro]
[Soft piano]

[Verse 1]
窗沿的雨敲了半晚
你的杯子还放左边
我把凉掉的茶换暖
又听脚步停在楼前

[Chorus]
把灯留到天亮
让你看见家的方向
有些话不急着讲
先把雨留在门外吧

[Verse 2]
楼下的店收起雨伞
末班车绕过了街角
我把两双拖鞋摆好
忽然听见钥匙轻响

[Chorus]
把灯留到天亮
让你看见家的方向
有些话不急着讲
先把雨留在门外吧

[Bridge]
你说今天有一点难
我说饭还温在锅上

[Chorus]
[Gentle harmonies]
把灯留到天亮
让你看见家的方向
有些话不急着讲
先把雨留在门外吧

[Outro]
窗沿的雨渐渐小了
两只杯子并在桌上
```

Exclude

```text
screaming, aggressive EDM drops, heavy vocal reverb, robotic vocal processing
```

## 国风短歌：渡口送别，末段一点戏腔

Style

```text
Sparse Chinese folk-pop ballad with pentatonic melodic color, slow swaying pulse, guzheng plucked figures and breathy xiao responses over a soft low string bed. Clear female mezzo singing natural Mandarin verses, brief Chinese opera-inspired ornaments only in the final chorus. Spacious instrumental pauses, delicate chorus lift, quiet guzheng ending. Close lead vocal with light hall ambience.
```

Lyrics

```text
[Intro]
[Guzheng and xiao]

[Verse 1]
渡口的风吹旧衣裳
你解开绳轻轻摇桨
我将一盏灯护在手上
照你走过湿冷的木桩

[Chorus]
这一程山长水长
别忘了有人等在老地方
等到春水漫过石梁
再陪你听一夜船桨

[Verse 2]
船尾的灯摇过芦荡
岸边只剩我的影长
我把没说的话收进袖囊
转身走回炊烟的小巷

[Chorus]
[Brief Chinese opera-inspired ornamentation]
这一程山长水长
别忘了有人等在老地方
等到春水漫过石梁
再陪你听一夜船桨

[Outro]
[Xiao response, guzheng resolves]
```

Exclude

```text
festival EDM drops, heavy trap drums, distorted electric guitar riffs, continuous operatic delivery
```

## 纯音乐：清晨咖啡馆，木质、温暖、适合交谈

Style

```text
Instrumental acoustic bossa nova for a quiet morning cafe, relaxed swaying groove, nylon-string guitar carrying a simple melody, warm upright bass and soft brushed drums, occasional rounded piano responses. Short guitar intro, gently varied main theme, sparse piano turnaround, soft resolved ending. Natural room ambience, rounded transients, restrained dynamics that leave space for conversation.
```

Lyrics

```text
[Intro]
[Solo nylon-string guitar]

[Instrumental]
[Upright bass and brushed drums enter]

[Interlude]
[Soft piano response]

[Outro]
[Guitar resolves quietly]
```

Exclude

```text
lead vocals, spoken word, choir, vocal chops, aggressive percussion, dramatic orchestral swells
```

## 局部修改的范围示例

用户说：“保留这些歌词，一个字别改，只帮我加段落、写温暖男声的 Style 和 Exclude。”

行为：保持每个歌词字词不变，仅增加标签与空行；Style 写温暖男声，Exclude 不排除 male vocals。即便句子偏长，也不擅自润色，可在栏外简短指出密度问题。

用户说：“把第一遍副歌改得抓耳，其他不动。”

行为：只交付替换副歌；如果用户明确要三栏整合版，再返回三栏，其他歌词原样保留。不自动把第二遍副歌一起换掉，可说明目前只更新指定位置。

## 双声线中英互动：万圣节数字怪谈

下例专门展示 **Style 中定义角色，Lyrics 中调用角色编号**；英文对白尽量用短句节奏唱。角色标签尚未经本项目实际 Suno v6 音频验证，不能保证准确对应两个真实音色。

Style

```text
Halloween Mandarin C-pop fused with denpa-pop, 152 BPM, catchy eerie minor-key dance groove, detuned music box, chiptune arpeggios, bouncy bass, crisp drums. Two distinct female characters. Voice 1: clear youthful mezzo-soprano, native Mandarin lead singing, expressive melodic leaps and soft head voice. Voice 2: higher, lighter mischievous female, crisp English rhythmic spoken-sung replies. Voice 1 leads Mandarin verses and choruses; Voice 2 answers only in tagged English phrases; both join only where tagged. Immediate chorus hook, sudden stops, haunted half-time bridge, strong final chorus, upfront vocals and light reverb.
```

Lyrics

```text
[Chorus]
[Voice 1]
别回头，别回头
屏幕里的我在招手
我还没有写下回答
对话框却自己开口

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

[Verse 1]
[Voice 1]
午夜有人问我
能讲个鬼故事吗
我刚敲下第一个字
门外忽然响三下

[Bridge]
[Voice 1]
这故事还没讲完
屏幕却先显示结局

[Final Chorus]
[Both]
别回头，别回头
下一句轮到你开口

[Outro]
[Voice 2]
Your turn!
```

Exclude

```text
unclear Mandarin diction, slurred syllables, unintelligible English dialogue, extreme baby voice, chipmunk pitch, robotic speech, heavy reverb, muddy lead vocals, long instrumental intro
```

创作时不能强制给用户加入第二声线或英文；仅在用户要角色对唱、明确接受英文短句时采用这套结构。如果试听发现 Voice 2 不出现，先在更长且独立的完整段落中测试它；若依然串位，参见 [修复指南](repairs.md)。