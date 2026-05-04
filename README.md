# Review Skill (复盘 Skill)

An adaptive, intelligent review (retrospective) skill for CodeBuddy IDE. It guides users through structured reflection sessions using multiple proven frameworks (KPT, GRAI, 4F, KISS, STAR, AAR), automatically selecting the best framework based on the user's intent.

## ✨ Features

- **🤖 Adaptive Framework Selection**: Automatically chooses the most suitable review framework based on user input
- **🔠 Choice-Driven Interaction**: Uses A/B/C/D structured choices (inspired by `learn-x` skill) instead of open-ended questions to reduce cognitive load
- **📋 Multiple Frameworks Supported**:
  - **KPT** (Keep / Problem / Try) - For daily quick reviews
  - **GRAI** (Goal / Result / Analysis / Insight) - For project/deep reviews
  - **4F** (Facts / Feelings / Findings / Future) - For learning/exam prep reviews
  - **KISS** (Keep / Improve / Start / Stop) - For weekly/monthly reviews
  - **STAR** (Situation / Task / Action / Result) - For interview/performance reviews
  - **AAR** (After Action Review) - For project milestone/team collaboration reviews
- **📝 Markdown Output**: Automatically saves review records as Markdown files
- **🩺 Diagnostic First**: Asks 3 short diagnostic questions before starting to understand user's context
- **🔄 Periodic Lock-in**: Every 3 turns, provides a recap to ensure understanding
- **😈 Devil's Advocate**: Challenges correct answers to ensure depth, not just surface understanding

## 🚀 Usage

### Triggers

The skill is triggered when the user says any of these:
- "复盘"、"反思"、"总结" (Review, reflect, summarize)
- "今天做了什么"、"项目进展如何" (What did I do today, How's the project going)
- "备考总结"、"学习复盘" (Exam prep review, learning review)
- "帮我复盘"、"我想复盘" (Help me review, I want to review)

### Examples

#### Example 1: Daily Review (KPT)
```
User: "帮我复盘一下今天"

AI: "好的，我们来复盘。先问你 3 个短问题，帮我理解你的情况：
     问题 1/3：你今天复盘，最想达成什么？
     - A. 梳理一下今天做了什么（单纯记录）
     - B. 找出问题，下次做得更好（改进导向）
     - C. 沉淀经验，形成可复用的方法（经验沉淀）
     - D. 以上都不是，其实是：_____"

User: "B"

AI: "问题 2/3：复盘今天，你的情绪基调是？
     - A. 满意/有成就感（进展顺利）
     - B. 焦虑/有压力（遇到阻碍）
     - ..."

(Continues with KPT framework, using choice-driven questions)
```

#### Example 2: Project Review (GRAI)
```
User: "帮我复盘一下 Alpha 项目"

AI: "我们用 GRAI 框架来深度复盘 Alpha 项目。先问 3 个诊断问题..."
```

## 📂 File Structure

```
review-skill/
├── SKILL.md              # Main skill file (adaptive logic + guidance flow)
├── LICENSE               # MIT License
├── README.md             # This file (English)
├── README-zh.md         # Chinese version
└── templates/            # Review templates
    ├── kpt.md            # KPT template (daily review)
    ├── grai.md           # GRAI template (project review)
    ├── 4f.md             # 4F template (learning review)
    ├── kiss.md           # KISS template (weekly/monthly review)
    ├── star.md           # STAR template (interview/performance review)
    └── aar.md            # AAR template (deep project review)
```

## 🎯 Framework Selection Logic

| User Intent | Diagnostic Result | Recommended Framework |
|-------------|-------------------|----------------------|
| "今天做了什么" (What did I do today) | Purpose = A (simple record) | KPT (lightweight) |
| "项目进展" (Project progress) | Purpose = B (improvement-oriented) | GRAI + AAR |
| "备考总结" (Exam prep summary) | Purpose = C (experience crystallization) | 4F |
| "本周/本月总结" (Weekly/monthly summary) | Any purpose | KISS |
| "面试复盘" (Interview review) | Any purpose | STAR |
| Complex emotions | Any purpose | 4F (process emotions first) |

## 🛠️ Installation

1. Copy the `review-skill` directory to your CodeBuddy skills directory:
   ```bash
   cp -r review-skill ~/.codebuddy/skills/
   ```

2. Restart CodeBuddy IDE or reload skills.

3. The skill will be automatically loaded when trigger words are detected.

## 📋 Output

Review records are automatically saved to:
```
output/复盘记录/{date}_{review_type}_{topic}.md
```

Examples:
- `output/复盘记录/2026-05-04_每日复盘_KPT.md`
- `output/复盘记录/2026-Q2_项目Alpha复盘_GRAI.md`
- `output/复盘记录/2026-05_备考复盘_4F.md`

## 💡 Design Philosophy

This skill is inspired by the `learn-x` skill's core philosophy:
> **Use structured choices (A/B/C/D) instead of open-ended questions.**
> Choice-driven questions reduce cognitive load and force users to reason, rather than give vague answers.

### Core Principles

1. **Diagnose First** - Ask 3 short questions to build the user's "starting portrait"
2. **One Dimension at a Time** - Only ask one review dimension per turn, don't pile up questions
3. **Prefer Choice Questions** - Use A/B/C/D whenever possible, not open-ended questions
4. **Leave White Space** - Always leave "None of the above, actually it's D: ..." option
5. **Periodic Lock-in** - Every 3 dimensions, do a recap to ensure aligned understanding
6. **Devil's Advocate** - After user answers correctly, challenge appropriately to ensure depth

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 📧 Contact

- Author: bellchen
- Email: bellchen@tencent.com
- GitHub: [dimayip](https://github.com/dimayip)

---

**Happy Reviewing! 🎉**
