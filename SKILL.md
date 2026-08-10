---
name: writing-style
description: >
  Apply when writing prose for others: READMEs, design docs, blog posts, public PRs/issues, slides,
  broadcast Slack/email messages, marketing copy, or any user-facing prose that will be read by people
  beyond the immediate author. Use this skill to match register, write in the target language's own habits,
  keep technical terms in their canonical form, expose reader-useful information hierarchy, and remove
  translation smell, marketing filler, AI-essay filler, process narrative, and defensive storytelling.
  Also covers UI copy and string resources, release notes, repository descriptions, and taglines, and governs
  the register of code comments, commit messages, and code review notes.
  Applies to both Chinese and English. Triggers: "write a README", "draft a blog post", "polish this doc",
  "改一下这段文案", "把这段写成 README", and any text that outlives the conversation.
  Do NOT use for: chat responses and private scratch writing.
---

# Writing style

## Core principle

Reader-facing prose should help the reader understand what the artifact is, what it does, and how to judge or
use it.

Lead with identity: "we are", "this is", "this does". Define the work through its own frame first. Negative
examples and banned phrases are diagnostics, not the organizing principle of the final piece.

Write from the reader's side. Expose the information hierarchy the reader needs; leave out the writer's
working session unless it changes how the reader should use, review, or trust the work.

## Audience and selection

Use the intended reader as a private constraint for selection, emphasis, and order. Write for what that reader
needs to understand, decide, verify, or do next; do not carry every source note into the final prose.

Treat audience, judges, reviewers, rubrics, assignment requirements, and scoring criteria as invisible inputs
unless the requested genre explicitly requires a rubric mapping. Satisfy them through the artifact's framing,
evidence, examples, terminology, and omissions. Do not narrate that the prose is serving them.

## Scope

Use this skill for text that will be read beyond the immediate author or current chat:

- READMEs and public docs.
- Design docs, blog posts, public PRs and issues.
- Slides, broadcast Slack/email messages, and marketing copy.
- Polishing or rewriting prose for external readers.
- UI copy and string resources, release notes, repository descriptions, and taglines.

The register rules also govern text that persists past the session even when this skill is not invoked
explicitly: code comments, commit messages, and code review notes. Their content conventions belong to the
project; their register belongs here.

Do not use it for text that stays inside the conversation: chat replies and private scratch writing.

## Register

Match the situation. "Native" means appropriate to the context, not automatically casual.

| Context | Chinese | English |
|---|---|---|
| Commit / PR / code comment / design doc | 书面语，如“移除”“优化”“修复” | Formal-concise, verb-first, such as Remove / Optimize / Fix |
| Paper / lab report | 学术书面语，如“本文”“实验表明” | Academic, such as We propose / Results indicate |
| README / public docs | 书面语，可以有作者判断 | Formal but not stiff; authorial judgment is allowed |

For Chinese technical writing, aim for a restrained style with explicit judgment and accurate terminology,
roughly in the register of 阮一峰 or 廖雪峰.

Chinese 口语 markers, which read as unserious and run longer than the written form:

- Second-person narration of what the reader experiences: "回到你进来时那一屏" → "返回进入时的页面".
- Colloquial aspect and modal particles: "一直没加载出来" → "未加载"; "就行了"、"其实"、"的话".
- Interaction written as dialogue rather than as behaviour.

Length is the mechanical check: the written form of the same claim is shorter. If a rewrite gets longer,
it has usually added hedging rather than register.

## Language

Write in the target language's own habits. Chinese should use Chinese sentence shape; English should use
English sentence shape.

Keep technical terms in their canonical form. In Chinese technical writing, English terms stay English where
that is how practitioners actually use them: "这个 endpoint", "做 fine-tuning", "改用 virtual scrolling".
Do not force English phrases into Chinese for style, and do not translate established terms such as QStash,
wall-clock, LWW, or shadcn/ui just to localize them.

Keep language consistent. In Chinese prose, reserve English for canonical technical terms, product names,
APIs, commands, file paths, quoted source text, or cases where the audience would recognize the English form
faster than a translation. In English prose, use Chinese only when the target readers are expected to know the
term or when quoting source text.

## Voice

Use concrete judgment and observable claims. The voice should feel like a real author making useful choices,
not like a pitch deck or generated essay.

Avoid fake authorial drama. Do not invent a founding story, pain narrative, or "we realized..." arc from
implementation details. If motivation matters and the source material does not provide it, ask the user how to
frame it; otherwise omit it.

Use direct transitions and real conclusions. Stock connective tissue should earn its place.

## Structure

Use the structure the content earns. Let the central claim, example, or user-visible behavior set the shape;
supporting details follow that frame.

Prefer these shapes:

- Lead with a concrete example or demonstration where possible, so the reader sees what using or reading this
  feels like before the explanation.
- Weight sections asymmetrically. Important parts get space; standard parts compress; empty parts disappear.
- Use prose where prose carries meaning better than bullets.
- State opinions and tradeoffs when they are load-bearing.
- Present the artifact through its own frame before mentioning rejected alternatives, limitations, or
  corrections.

Keep the result-oriented layer: what changed, what matters, what constraints remain, and what the reader
should understand or do next. The purpose is to align the reader's model, not to turn the chat session into
prose.

## Motivation, tradeoffs, and limitations

Motivation, tradeoffs, and limitations are reader tools, not a default storytelling layer.

- Motivation belongs only when the source material or user clearly provides it, or when readers need it to
  understand the artifact.
- Tradeoffs should be compressed by default. Explain rejected alternatives only when the design is unusually
  complex, likely to surprise readers, or needed to prevent misuse.
- Limitations should be concrete and reader-actionable.

Technical introductions can include why when the real why matters. README is not API documentation; large
mechanical breakdowns belong in engineering docs such as CLAUDE.md or docs/.

## Diagnostics

Use these checks while editing. They identify places where the prose has drifted away from the reader-facing
frame.

### Translation smell

Chinese markers:

- Overuse of 的, unnecessary 被 passives, English-style long pre-modifying clauses, and abstract "...性" nouns
  where a verb would do.
- Filler such as "进行 + 动词".
- Reflexively translated connectors such as "对于...来说", "在...方面", and "作为一个...".
- Keeping subjects where Chinese would naturally drop them.
- Decorative em dashes where a colon, period, or rewritten sentence would read more naturally.
- Structures such as "在 ... 的同时", "通过 ... 实现", and "使得 ... 成为可能".

English markers:

- "Make use of X" instead of "use X".
- "Carry out the operation" instead of "do/run the operation".
- Empty heads such as "the issue of X", "the problem of X", and "the situation of X".
- Over-hedging such as "may possibly", "could potentially", and "it seems that perhaps".
- Topic-fronting that should be re-anchored: "Regarding the issue of latency, we observed..." -> "On latency:
  we observed...".

### Marketing and buzzword smell

Chinese warning signs:

- 赋能、抓手、闭环、对齐、颗粒度、心智、拉齐、复用、抽象一下, unless the context explicitly uses that register.
- 装腔形容词 such as 极致、无缝、深度、本质、本质上是、生态.
- 三段式排比: "不仅 X，而且 Y，更 Z" or "更 X，更 Y，更 Z".
- 否定对比句式: "X 是 A，不是 B"、"不是 A，而是 B"、"与其说是 A，不如说是 B"。直接陈述 A 即可；
  B 通常是作者自设的假想对立面，读者并没有那个误解。例："密度档和帧率上限是选项，不是代码里的分叉。"
  → "密度档和帧率上限是选项。" 当 B 是读者真会走错的那条路时保留；判据见 defensive storytelling
  smell 里关于 rejected alternative 的那条。
- 反问句开篇 or 引导式提问: "你是否曾经..." or "想象一下...".
- Light or slogan-like endings such as "免得返工", "省时间", "轻松搞定", "快速上手", "跟着 X 走", "X 也响",
  "不漂移", and "一把梭". Taglines get no exemption: they are short and prominent, which makes a colloquial
  turn there more visible, not less.
- 兜售式开场: "想象一下...", "在这个时代...", "市面上的工具都没解决 X".
- 物化抽象 or 拟人化表达: "把决策记成一本明账", "让代码自己说话".

English warning signs:

- leverage, synergize, robust, powerful, comprehensive, seamless, blazing fast, production-ready,
  best-in-class, when they stand in for specific meaning.
- "Existing tools all fail at X, so..." when it creates an unearned problem-solution arc.

### AI-essay smell

Chinese stock phrases:

- 值得注意的是、综上所述、总的来说、本文将探讨、希望对你有所帮助、如有疑问欢迎讨论。

English stock phrases:

- "It's important to note that...", "Furthermore,", "In conclusion,", "Let's dive into...", "Hope this helps!",
  "Feel free to...".

### Template-shape smell

- Uniform "**Label**: description" bullets across every section.
- A comparison table that has not earned its place.
- Predictable, evenly weighted sections regardless of content.
- Feature lists before any usage example.
- Headers for content that does not need to be split out.

### Writer-side metadata smell

- Internal development codenames, branch names, prompt/session artifacts, or private shorthand that do not help
  readers identify the thing being discussed.
- Process narrative such as "I looked at...", "next I will...", "we decided to...", or "the agent found...".
- Engineering reasoning that does not change how the reader should use, review, or trust the work.
- Meta-explanations of the writing task itself, unless the document is explicitly about that process.
- 项目状态自述与验证自述: "No version has been released yet."、"本机不参与"、
  "哪些接口接受何种参数、哪些会被风控拒绝，该项目均已逐一验证。"

判据: 这句话删掉之后，读者的行动或判断会变吗？不会就删。

### Audience-scaffolding smell

- Visible planning phrases such as "为了让读者理解", "面向 XX 读者", "评委可以看到", "根据 XX 要求",
  "本作品满足 XX 标准", or "the reader should notice".
- Sentences that announce the audience, rubric, or scoring target instead of making the relevant quality
  evident in the artifact itself.
- Source-dump structure: including all provided background, requirements, or implementation notes because they
  were supplied, rather than because the target reader needs them.

### Defensive storytelling smell

- Problem-solution arcs that set up an exaggerated opponent just to defeat it.
- "We chose X over Y because Z" when the rejected alternative is not relevant to the reader.
- Chains like "we did X because Y, but Z, so W" when the chain is not itself the point.

## Cross-language conventions

Some structural conventions from English open-source docs do not transfer cleanly to Chinese. For example,
Chinese open-source docs often open declaratively with what the project is instead of a problem narrative such
as "X is tedious, Y is incompatible, so we built Z".

The reverse applies too. Do not make English READMEs sound like Chinese READMEs for symmetry's sake.
