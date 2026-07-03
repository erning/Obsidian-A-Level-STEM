# A-Level STEM Study Notes

这是一个给自学用的 Obsidian 笔记库。

它以 CAIE A-Level Physics 9702、Mathematics 9709 和 Further Mathematics
9231 为骨架，但目标不是“刷考试”。这些 syllabus 和教材只是提供一个足够完整、
足够标准的路线。真正想做的事情，是把数学和物理重新学得扎实一点：知道概念从哪
里来，公式什么时候能用，题目背后到底在问什么。

如果只是想快速进入笔记，从这里开始：

| 入口 | 适合什么时候打开 |
|---|---|
| [Physics 9702](<10 Physics/README.md>) | 想学物理，或者想从运动、力、电磁、热学、量子这些主题进入 |
| [Mathematics 9709 and 9231](<20 Mathematics/README.md>) | 想学纯数、力学、统计，或者想把 9709 和 9231 合成一条数学路线 |
| [Terminology Reference](<80 References/Terminology Reference.md>) | 想查 A-Level 标准英文术语和中国大陆常用中文术语 |
| [Project Rules](<AGENTS.md>) | 想知道这个 vault 的写作、命名、公式和生成材料规则 |

## 这个库怎么读

每个正式主题都会被整理成一个小的学习材料包。打开一个主题目录后，一般会看到：

- `00 Overview.md`：这一节学什么、为什么学、和哪些主题相连。
- `10 Lecture Notes.md`：英文主讲义，尽量使用 CAIE syllabus 和教材里的标准说法。
- `10 Lecture Notes.zh-CN.md`：中文快速讲义，用自然中文解释这一节，不做逐句翻译。
- `20 Worked Examples.md`：例题和解题思路。
- `30 Key Practice Problems.md`：重点练习题，不放答案。
- `31 Key Practice Solutions.md`：练习题解析。
- `80 Review Checklist.md`：复习清单，用来检查自己是不是真的能进入下一节。

物理 topic 目前已经补齐英文主讲义和中文快速讲义。数学 topic 也按同样结构推进。

推荐的读法很简单：

1. 先读 `00 Overview.md`，弄清楚这一节的边界。
2. 再读 `10 Lecture Notes.md`，把英文术语和标准表述过一遍。
3. 用 `10 Lecture Notes.zh-CN.md` 快速复述主线。
4. 看 `20 Worked Examples.md`，注意它为什么选这个方法。
5. 做 `30 Key Practice Problems.md`，再用 `31 Key Practice Solutions.md` 对照。
6. 最后过 `80 Review Checklist.md`。卡住的地方回去补。

## 目录结构

```text
A-Level-STEM/
├── 10 Physics/
│   ├── 00 Overview/
│   ├── 01 Topics/
│   ├── 02 Experimental Thinking/
│   └── 04 Reference/
├── 20 Mathematics/
│   ├── 00 Overview/
│   ├── 01 Pure Mathematics/
│   ├── 02 Mechanics/
│   ├── 03 Probability and Statistics/
│   └── 04 Reference/
├── 80 References/
├── assets/
└── AGENTS.md
```

`assets/` 里放 syllabus 和教材 PDF。它们是本地参考资料，当前不提交到仓库。

## 学习路线

物理部分以 [CAIE Physics 9702](<10 Physics/README.md>) 为主线。它从物理量、
测量和运动开始，逐步进入力学、材料、波、电学、电磁场、热学、量子、核物理和
宇宙学。

数学部分把 [CAIE Mathematics 9709 and Further Mathematics
9231](<20 Mathematics/README.md>) 合在一起学。9709 提供基础语言，9231 继续把
同一套语言推向更深的代数、几何、微积分、力学和统计。

这两个目录不是彼此孤立的。物理里的运动学、电路、场、振动会不断用到数学；数学
里的向量、微积分、微分方程、统计也会因为物理问题变得更具体。

## 写作约定

这个库里的主要学科笔记使用英文，原因很现实：CAIE syllabus、coursebook 和题目本
身都是英文，术语最好从源头保持一致。

中文会用在两类地方：

- 中文快速讲义：帮助自己更快地复述和理解。
- 术语对照：把 A-Level 标准英文和中国大陆常用名称对应起来。

数学和物理公式都用 LaTeX 写。行内公式用 `$...$`，展示公式用 `$$...$$`。除非真
的是代码，不把公式放进 code span。

## 本地环境

普通阅读不需要 Python。

如果要生成解题草稿、检查数值、画数学图像，使用项目里的 `.venv/`。这个虚拟环境
不提交。需要处理 PDF 时，也可以使用同一个本地环境。

## 这个 README 之外

真正的内容在笔记里。README 只是门口的地图。

如果一段时间后回来，不知道从哪里继续，就先打开：

- [Physics Learning Checklist](<10 Physics/00 Overview/Learning Checklist.md>)
- [Mathematics Learning Checklist](<20 Mathematics/00 Overview/Learning Checklist.md>)
- [Mathematics Integrated Sequence](<20 Mathematics/00 Overview/Integrated Sequence.md>)
