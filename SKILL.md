---
name: writing-style
description: >
  Apply when writing prose for others — READMEs, design docs, blog posts, public PRs/issues, slides,
  broadcast Slack/email messages, marketing copy, or any user-facing prose that will be read by people
  beyond the immediate author. Covers register matching (chat / commit / README / academic), no-translation-smell
  (欧化中文 and Chinese→English calque), no-marketing/buzzword voice, no-AI-essay register, and structural
  anti-patterns (uniform bullet shapes, unearned comparison tables, problem→solution narrative arcs). Both
  Chinese and English. Triggers: "write a README", "draft a blog post", "polish this doc", "改一下这段文案",
  "把这段写成 README", any time the deliverable is prose meant for an external reader.
  Do NOT use for: chat responses, code comments, internal commit messages, code review notes, or any prose
  staying inside the immediate working session.
---

# Writing style

Both languages share one bar: write like a native writer in the target register, not like a translator and
not like an AI essay generator.

文体定位 for Chinese tech writing: 参照阮一峰、廖雪峰一档，克制、判断显式、术语准确，不戏剧化。

## Register table — match context

| Context | Chinese | English |
|---|---|---|
| Commit / PR / code comment / design doc | 书面语 (移除 / 优化 / 修复) | formal-concise, verb-first (Remove / Optimize / Fix) |
| Paper / lab report | 学术书面语 (本文 / 实验表明) | academic (We propose / Results indicate) |
| README / public docs | 书面语，可有作者判断的语气 | formal but not stiff, authorial judgment OK |
| Chat / IM | 口语 (改完了 / 跑一下看看) | casual (done / try it / lmk) |

Don't mix. Don't equate "native" with "spoken" — a chat reply in 学术书面语 is wrong, but a commit message
in chat register is also wrong. The split is by *context*, not by a formality dial.

## No translation smell

**Chinese-specific markers** (English → Chinese calque):
- 欧化中文: overuse of 的, unnecessary 被 passives, English-style long pre-modifying clauses, abstract "...性"
  nouns where a verb would do, "进行 + 动词" used as filler, reflexively translated connectors like
  "对于...来说" / "在...方面" / "作为一个...".
- Failing to drop subjects where Chinese would naturally drop them.
- Em-dash / en-dash 当装饰 ("可在 A、B 之间切换 —— 生产用 A，开发用 B") usually reads better as separate
  sentences in Chinese; use 冒号、句号 or restructure.
- 翻译腔结构: "在 ... 的同时"、"通过 ... 实现"、"使得 ... 成为可能".

**English-specific markers** (Chinese → English calque):
- "Make use of X" instead of "use X". "Carry out the operation" instead of "do/run the operation".
- Empty heads: "the issue of X", "the problem of X", "the situation of X" used as filler.
- Over-hedging: "may possibly", "could potentially", "it seems that perhaps".
- Topic-fronting that should be re-anchored: "Regarding the issue of latency, we observed..." →
  "On latency: we observed...".

## No marketing / buzzword register

**Chinese**: 赋能、抓手、闭环、对齐、颗粒度、心智、拉齐、复用、抽象一下 — unless the context is explicitly
that register. Also avoid 装腔形容词: 极致、无缝、深度、本质、本质上是、生态.

**English**: leverage, synergize, robust, powerful, comprehensive, seamless, blazing fast, production-ready,
best-in-class — used as marketing filler rather than meaning anything specific.

**Other Chinese anti-patterns:**
- 三段式排比: "不仅 X，而且 Y，更 Z" / "更 X，更 Y，更 Z".
- 反问句开篇 / 引导式提问: "你是否曾经..." / "想象一下...".
- 轻浮 / 口语收尾: "免得返工"、"省时间"、"轻松搞定"、"快速上手"、"跟着 X 走"、"X 也响"、"不漂移"、
  "一把梭". 在 tagline 行可偶尔保留一处口语化修辞，正式段落里换正式表述。

**Fake authorial voice** — these read as marketing voice, not real judgment:
- 兜售式开场: "想象一下..."、"在这个时代..."、"市面上的工具都没解决 X" / "Existing tools all fail at X, so...".
- 物化抽象 / 拟人化记账: "把决策记成一本明账" / "让代码自己说话".
- problem→solution 叙事弧 (设置一个对立面再"破解"它).

## No AI-essay register

**Chinese**: 值得注意的是、综上所述、总的来说、本文将探讨、希望对你有所帮助、如有疑问欢迎讨论.

**English**: "It's important to note that...", "Furthermore,", "In conclusion,", "Let's dive into...",
"Hope this helps!", "Feel free to...".

## Tech terms stay in their canonical form

In Chinese tech writing, English terms stay English where that's how they're actually used: "这个 endpoint"、
"做 fine-tuning"、"改用 virtual scrolling". 不为了"国际化"硬塞英文短句，也不为了"本土化"硬翻已成约定的术语
(QStash、wall-clock、LWW、shadcn/ui). In English, don't over-explain a domain term the audience already knows.

# Structure — for prose meant for others

Sentence-level concerns above. This section is about how a piece is organized at the section/paragraph
level. Applies to text visible to others: READMEs, design docs, blog posts, public issues / PRs, slides,
commits, broadcast Slack/email.

## Avoid the AI-template shape

- Uniform "**Label**: description" bullets across every section.
- A comparison table whether or not the comparison earns its place.
- Predictable, evenly-weighted section sequence regardless of what the content warrants.
- Feature lists placed before any usage example.
- Headers for content that doesn't need to be split out.

## Instead

- Lead with a concrete example or demonstration where possible — show what using or reading this feels
  like before describing it.
- Weight sections asymmetrically. Interesting parts get space; standard parts compress; empty parts get cut.
- Prose where prose carries meaning better than bullets.
- State opinions and tradeoffs when they're load-bearing; skip them when they aren't.

## Allowed and encouraged storytelling

- 设计动机 / design motivation (why this choice).
- 设计取舍 / design tradeoffs (why not the alternative).
- 已知局限 / known limitations (what's out of scope).

This is the "authorial judgment" the register table allows for README. Marketing-voice variants of
storytelling (兜售式开场, problem→solution 叙事弧, 物化抽象) belong above under § No marketing voice, not here.

Technical introductions favor WHY over HOW. README isn't API documentation — avoid large mechanical
breakdowns. HOW belongs in engineering docs (CLAUDE.md / docs/).

## Convention drift across languages

Some structural conventions are English-OSS habits that don't transfer cleanly to Chinese:
- Problem-narrative opener ("X 太繁琐，Y 不兼容，所以我们做了 Z" / "Existing tools are slow, so we built...")
  — Chinese OSS more often opens declaratively with what the project is.
- "We chose X over Y because Z" tradeoff justification — in Chinese, factual description often carries the
  same load.

The reverse applies too: don't make English READMEs sound like Chinese ones for symmetry's sake.
