# 🏺 Word Quest · 单词远征

> **谷sir说英语** 出品 · 沪教版牛津英语配套单词闯关游戏

[![GitHub Pages](https://img.shields.io/badge/🎮_立即游玩-GitHub_Pages-brightgreen?style=for-the-badge)](https://gumingyu.github.io/word_quest/word_quest_v7.html)

---

## 这是什么

一款专为**沪教版牛津英语**学生设计的课后单词复习游戏。

学生选择本周学习的单元，通过**打怪答题**的方式复习课后单词。答对题目攻击怪物，答错被怪物反击，连续答对触发连击加成。5关打通即为通关，通关后自动生成成绩单发给老师。

**不是死记硬背，是在战斗中检验词汇掌握程度。**

---

## 游戏机制

**三种题型**
- 🟢 基础攻击（normal）— 中英互译，伤害 10
- 🟡 暴击（crit）— 词组搭配 / 语法选择，伤害 25
- 🟣 必杀（ulti）— 长句翻译，伤害 50

**战斗系统**
- 答对打怪，答错被反击（扣15血）
- 连续答对 3 题触发 **1.5x 连击加成**
- 每个单元固定 5 关，第 5 关为 BOSS 战

**成绩单**
通关后一键复制错题报告，包含每道错题的正确答案和考点说明，直接发给老师。

---

## 题库内容（7B 全册）

| 单元 | 主题 | 核心考点 | 题数 |
|---|---|---|---|
| Unit 1 | People & Personality | used to / give up / seldom / be strict about | 60 |
| Unit 2 | Travel & Nature | prefer to / go hiking / stretch for / the number of | 60 |
| Unit 3 | Trees & Environment | be made of / communicate with / according to / spread | 60 |
| Unit 4 | Animals & Services | fall asleep / allow to / apologize for / extinct | 60 |
| Unit 5 | Water & Daily Life | a bit / at once / eventually / leisure | 60 |
| Unit 6 | Electricity & Technology | battery / electricity / switch off / save energy | 60 |
| Unit 7 | Heroes & Contributions | in the field of / contribute to / pioneer / education | 60 |
| Unit 8 | Careers & Talents | career / audience / athlete / curious / extremely | 60 |
| **合计** | | | **480 题** |

---

## 仓库结构

```
word_quest/
├── word_quest_v7.html          # 游戏主文件（学生访问此页面）
├── wq_qr_generator.html        # 二维码生成器（老师用）
├── README.md
└── units/
    ├── index.json              # 单元目录（控制哪些单元显示）
    ├── 7B_Unit1.json
    ├── 7B_Unit2.json
    ├── 7B_Unit3.json
    ├── 7B_Unit4.json
    ├── 7B_Unit5.json
    ├── 7B_Unit6.json
    ├── 7B_Unit7.json
    └── 7B_Unit8.json
```

---

## 老师使用指南

### 发给学生（一次性操作）

把游戏链接发给家长群，告诉家长保存好，以后每周都用这个链接：

```
https://gumingyu.github.io/word_quest/word_quest_v7.html
```

### 每周布置作业

学生学完一个单元后，进游戏选择对应单元，完成 5 关挑战，通关后把成绩单复制发回给老师。**无需老师额外操作。**

### 新学期 / 新册教材（更新题库）

1. 用 DeepSeek 按提示词生成新单元 JSON 文件
2. 发给谷sir（Claude）做质量审查和修复
3. 将修复后的 JSON 上传到 GitHub `units/` 文件夹
4. 同步更新 `units/index.json`，添加新单元条目
5. 学生刷新页面即可看到新单元

---

## 给 DeepSeek 的出题提示词

```
请根据以下词表生成 Word Quest 游戏题库 JSON。

格式要求：
- 5个关卡：stage1 到 stage5，每关12题，共60题
- 每题必须有：type / dmg / prompt / q / options（4个选项）/ correct（0-3的数字）/ learn
- type 只能是 normal（dmg:10）/ crit（dmg:25）/ ulti（dmg:50）
- options 里不能有重复选项
- meaning 字段内部不能使用双引号"，改用单引号'
- correct 答案分布尽量均匀，A/B/C/D 各约25%

词表如下：[粘贴词表]
```

> ⚠️ DeepSeek 生成后需发给谷sir做答案均衡处理，答案分布问题每次都会出现。

---

## index.json 格式

```json
[
  {
    "id": "7B_Unit1",
    "name": "Unit 1 · People & Personality",
    "desc": "人物性格描写 · 形容词 · 词组 · used to / give up / seldom",
    "count": 60
  }
]
```

---

## 常见问题

**Q: 学生说点单元进不去？**
让学生用 Safari 或 Chrome 打开，不要用微信内置浏览器。

**Q: 上传新题库后游戏没更新？**
GitHub Pages 有 2-5 分钟缓存延迟，等一会儿再刷新。

**Q: 点单元报 HTTP 404 错误？**
检查 `units/` 文件夹里对应的 JSON 文件是否上传成功。

---

## 关于谷sir说英语

- 📺 Bilibili：[谷sir说英语](https://space.bilibili.com/3546726482963847)
- 📍 广州·佛山 · 沪教版牛津英语专项辅导 · 十年教学经验

---

*题目内容基于沪教版牛津英语教材词表自主编写，仅供教学用途。*  
*游戏由谷sir与 Claude (Anthropic) 协作开发。*
