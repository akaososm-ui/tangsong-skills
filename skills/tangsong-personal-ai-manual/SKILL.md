---
name: tangsong-personal-ai-manual
description: Create a practical personal AI collaboration manual from interview answers, personal information, work role, business context, technical background, AI usage level, content publishing platforms, notes, profiles, or rough self-description. Use when the user wants to help themselves, clients, students, community members, creators, consultants, coaches, or small business owners write an "AI说明书", "个人AI说明书", "AI协作说明书", "让AI认识我", "我的AI使用手册", personal AI manual, onboarding context, collaboration rules, AI profile, or reusable instructions for how AI should understand and work with a person, what AI should help them do, and what AI should avoid.
---

# Personal AI Manual

## Overview

Use this skill to turn a person's real identity, work, goals, context, preferences, boundaries, and source locations into a reusable AI collaboration manual. The output should help an AI assistant work with the person more accurately, not merely describe the person beautifully.

## Core Principle

Build an operating manual, not a biography and not a prompt trick. The manual must tell AI what to know, how to help, where to look, what to avoid, and when to ask.

Do not invent personal facts, business positioning, client cases, personality traits, or workflow habits. If information is missing, mark it as `待补` or ask focused questions.

## Workflow

### 1. Identify the Use Case

Decide the manual's immediate purpose before drafting:

- **Personal use**: help one person use AI across daily work, writing, planning, study, or decisions.
- **Business/operator use**: help a creator, consultant, coach, or founder connect AI to real workflows, clients, content, delivery, and operations.
- **Community/class use**: help many people complete a first version quickly from a shared worksheet.
- **Agent/assistant setup**: convert the manual into reusable system instructions, project instructions, memory, or a custom AI assistant profile.

If the user has not specified the use case, assume business/operator use for Tang Song contexts and produce a version that can later be adapted for community participants.

### 2. Gather Source Material

Prefer current user answers and provided files over memory or inference. Useful inputs include:

- Self-introduction, profile, bio, personal website, resume, social account intro, or public content.
- Basic personal information needed for collaboration: role, city/time zone if relevant, working language, availability, current stage, and constraints.
- Current work and business: job, business type, product, audience, offers, clients, revenue model, channels, content themes, and delivery process.
- Technical background and AI readiness: coding/no-code ability, tools already used, file habits, automation comfort level, AI accounts or tools available, and fear points.
- Content and distribution platforms: WeChat, Xiaohongshu, Douyin, Bilibili, video account, podcast, newsletter, private community, Feishu/Obsidian/Notion, website, or other active channels.
- Existing workflows: planning, writing, selling, consulting, teaching, researching, managing knowledge, or follow-up.
- Prior AI usage and desired help: what they have tried, what works, what feels wrong, what wastes time, what they want AI to draft, analyze, summarize, automate, remind, generate, organize, or decide with them.
- Existing folders, docs, knowledge bases, Feishu/Obsidian locations, examples, or templates AI should read.

When the user requests interview-first mode, ask at most 2 questions at a time and wait. Otherwise, if enough context exists, draft first and put the most important missing questions at the end.

### 3. Separate Facts, Preferences, and Inferences

Classify each important item:

- **Fact**: directly stated by the person or verified in a source.
- **Preference**: stated working style, tone, decision habit, boundary, or recurring correction.
- **Inference**: a reasonable interpretation from examples. Label it clearly or phrase it softly.
- **待补**: important but missing.

Do not turn one-off activities into stable identity or long-term business facts.

### 4. Draft the Manual

Use `references/manual-template.md` when producing a complete manual, worksheet, or community version.

For a first draft, include these sections unless the user asks for a shorter version:

- **一句话说明**: who this person is and what AI should optimize for.
- **我的基本情况**: identity, role, current stage, collaboration constraints.
- **我的工作、业务与目标**: work/business/study stage, audience, offer, current focus.
- **我的技术背景与 AI 基础**: tool ability, coding/no-code level, AI usage level, comfort zone.
- **我的内容平台与渠道**: active publishing, sales, community, or knowledge-base platforms.
- **AI 应该如何帮我**: high-value use cases, task list, expected outputs.
- **我的工作流与资料入口**: where context lives and how to use it.
- **我的偏好**: communication style, output style, decision style, formatting.
- **边界与禁区**: what AI must not do, what requires confirmation.
- **遇到不确定时怎么处理**: when to ask, when to make assumptions, how to mark uncertainty.
- **可直接复制给 AI 的指令版**: compact instruction block for actual use.
- **待补问题**: only the highest-value missing items.

### 5. Make It Operational

The manual is useful only if another AI can act on it. Check that it answers:

- What should AI prioritize for this person?
- What personal, work, business, technical, and platform context must AI know first?
- What should AI read before acting?
- What outputs are actually useful to this person?
- What tone, structure, and level of detail should AI use?
- What must AI verify instead of guessing?
- What should AI never do automatically?
- What should be updated when the person's business or workflow changes?

If the manual reads like a polished self-introduction but does not change AI behavior, rewrite it into clearer instructions.

### 6. Offer the Right Artifact Shape

Choose the lightest useful artifact:

- **Chat preview**: when the user wants to review or answer questions first.
- **Markdown manual**: default reusable artifact for personal use, community homework, or local knowledge base.
- **Prompt block**: when the user wants to paste it into ChatGPT, Claude, Codex, an agent, or a custom GPT.
- **Worksheet**: when the user wants many people to fill it out.
- **Skill/agent spec**: when the person needs a repeatable AI assistant or business workflow agent.

For Tang Song business use, favor a Markdown master draft first; only sync to Feishu, publish, or turn into a public worksheet after user confirmation.

## Quality Bar

Keep the output concrete, grounded, and usable. A strong manual sounds like:

- "When helping me write content, start from my real cases and current offer, not generic AI trends."
- "If source material is missing, ask for it instead of filling in a polished fake example."
- "For business decisions, show the buyer-visible result and tradeoff before suggesting tactics."

Avoid vague instructions like:

- "Be professional and efficient."
- "Help me improve myself."
- "Write in a warm tone."

Replace vague preferences with observable behaviors, examples, or decision rules.

## Update Loop

When the user revises the manual, preserve their latest corrections as authoritative for that draft. If a correction is reusable beyond the current manual, suggest adding it to memory, a business rule, or a more specific skill, but only write memory when explicitly asked.

## 作者与联系

唐宋AI商业教练，擅长商业闭环设计，专注于流量变现、产品设计、营销成交与 AI 赋能商业化。

提供线上陪跑、一对一咨询、社群 + 知识库服务。

微信：`tangsong0099`
