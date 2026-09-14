---
name: tangsong-opc-offline-event-planner
description: Design and prepare OPC offline events that can support backend conversion. Use when the user wants to plan a salon, workshop, meetup, city event, offline sharing session, co-hosted event, or paid/free offline activity from strategy to execution, including event type, backend product connection, target users, topic, recruitment copy, poster copy, registration questionnaire, project plan, materials, onsite agenda, talk/PPT outline, group operations, follow-up, recap, and AI-assisted execution.
---

# OPC Offline Event Planner

## Core Principle

Design offline events as high-trust conversion fields, not as lively one-off gatherings.

Always clarify what the offline event should do before deciding how AI can help. AI can reduce preparation cost, generate options, analyze questionnaires, and turn the event into reusable assets, but it cannot replace the organizer's judgment about target users, backend offer, trust, delivery ability, or conversion path.

Use this conversion chain:

```text
backend product -> front-end user problem -> offline topic -> onsite result ->承接 action -> follow-up conversion
```

## Workflow Rules

- Work toward one complete, executable event pack. First clarify the strategy, then include all execution assets in the same delivery once the minimum inputs are available. Do not split the user into light, standard, or advanced versions.
- Ask at most 3 questions per round when required inputs are missing.
- Do not start with poster copy, recruitment copy, or materials before the event strategy is clear.
- Do not invent the backend product, pricing, target users, venue, dates, partners, costs, claims, or conversion results.
- If the organizer is running a first event, make the plan beginner-safe: explain the purpose of each key step, assign an owner, set a deadline, define the acceptance check, and include a fallback for the most likely failure.
- When information is missing but a complete plan is still useful, mark it as `【待确认】` and state a clearly labeled working assumption. Never turn an assumption into a fact.
- If the event is not suitable for the current stage, say whether to borrow traffic, co-host, lower the format, or run an online version first.
- If the activity is simple, let one person or AI-assisted workflow cover multiple roles. If complex, split roles clearly.
- Use the user's chosen output environment. If none is specified, return one complete Markdown pack that can be copied into any document tool, with clear module headings that can later be split into separate files.
- If the user wants separate files, use one event folder named `date + location + event name` and one module per file. Do not assume a particular operating system, note app, cloud document, or connector.
- When writing recruitment copy, use the user's own tone if they provide examples. Otherwise use plain, concrete Chinese: real problem first, clear onsite result, suitable and unsuitable audiences, and a natural next step. Do not require a private writing-style Skill.
- You may use the organizer's public event information as reference material. Keep only public or user-authorized facts, label the source or status when relevant, and remove participant privacy. Do not present a reference case's result as a guaranteed outcome.
- Collect only information needed for registration and follow-up. Explain photo, recording, testimonial, and marketing consent separately; never expose private contact details in public outputs.
- Write in Chinese by default when the user writes in Chinese.

## Phase 1. Information Intake

Start by collecting the minimum event card. If the organizer has never run an event, say that the workflow will provide the missing operating details rather than assuming prior experience.

Ask these 3 questions first unless the user has already answered them:

1. What is the backend product or next-step offer this offline event should support?
2. Who exactly should attend, and what problem are they already aware of?
3. What is the event date, city, expected size, and current recruitment source?

Then collect the remaining information as needed:

- Event type: conversion, relationship warming, user research, community activation, delivery, collaboration, brand exposure, or mixed.
- Backend product: name, price range, target user, problem solved, proof, conversion action, unsuitable buyers.
- Audience stage: current ability, urgency, payment awareness, tool/material readiness, offline attendance willingness.
- Topic idea: theme, promise, onsite result, attraction, unsuitable audience.
- Recruitment resources: private domain, community, public content, partner/platform, apartment/community platform, referrals.
- Constraints: date, duration, city, venue, budget, staff, equipment, platform rules, banned words, privacy, photography.
- Output location: chat, Markdown, online document, or separate files. Ask only when the choice affects delivery.
- Deliverables needed: poster, three copy versions, questionnaire, agenda, talk outline, PPT outline, project plan, materials, group operations, follow-up, recap.

If the user only gives a vague activity idea, output an "信息采集简报" and ask the next 3 highest-value questions instead of producing a full pack.

## Phase 2. Complete Event Delivery Pack

Once the minimum event card is clear, output the strategy and the full execution pack together. The strategy is the decision layer; the remaining sections turn it into a real event. If the user explicitly requests a strategy review first, stop after the strategy and wait for confirmation.

Use this structure:

```markdown
# 线下活动整体方案

## 1. 活动类型
- 类型：
- 这场活动在转化链路里的作用：
- 是否适合现在办：
- 如果不适合，建议替代方案：

## 2. 后端承接
- 后端产品/下一步动作：
- 目标用户：
- 解决的问题：
- 用户为什么会从这场活动自然走到下一步：

## 3. 活动主题与吸引力
- 活动主题：
- 一句话钩子：
- 用户为什么愿意来：
- 用户现场能获得什么：
- 不适合谁：

## 4. 招募信息
- 解决的问题：
- 报名门槛：
- 需要提前准备：
- 适合渠道：
- 风险提醒：

## 5. 现场设计
- 现场核心结果：
- 主要环节：
- 必须有的互动/实操：
- 结束前承接动作：

## 6. 活动后承接
- 24小时动作：
- 72小时动作：
- 用户分层：
- 后续转化入口：
```

Use `references/output-templates.md` for the full deliverable structure.

Complete execution pack:

1. Activity strategy sheet.
2. Project landing plan with daily milestones and next actions.
3. Role and responsibility table.
4. Venue, equipment, and material checklist.
5. Poster copy structure.
6. Recruitment copy in 3 versions:
   - 社群分享版
   - 朋友圈营销版
   - 公众号/知识星球长文版
7. Registration questionnaire fields.
8. Group operation timeline and message drafts.
9. Onsite agenda, host script, talk outline, and PPT outline.
10. Feedback questionnaire, user segmentation, follow-up scripts, recap plan, and asset archive checklist.
11. First-event risk checklist, decision assumptions, and items requiring the organizer's final confirmation.

When dates are known, produce a backward schedule from the event day. When dates are unknown, produce a T-minus schedule.

## Delivery And Project Rules

If creating files or splitting deliverables, verify the project container:

```text
date + location + event name
```

Examples:

- `2026-08-31杭州只工作不上班线下实战局`
- `2026-07-25北京CodexAI知识库内容创作实战局`

Use one dedicated folder per event. Inside the folder, use separate documents for separate modules:

- `00-活动整体方案.md`
- `01-项目落地计划.md`
- `02-海报文案.md`
- `03-招募文案.md`
- `04-报名问卷.md`
- `05-社群运营话术.md`
- `06-现场流程与主持稿.md`
- `07-分享大纲与PPT.md`
- `08-活动后跟进.md`
- `09-活动复盘.md`

For online document or list-view tools, inner document titles should stay short and module-first:

- Good: `02-海报文案`
- Good: `07-分享大纲与PPT`
- Avoid: `20260831杭州只工作不上班线下实战局｜02-海报文案`

If the user has no project folder, keep the full pack in one document and provide the suggested module names. Never require the user to have a local folder or a Feishu account.

## Key Judgments

### Event Type

Classify the event before writing copy:

- **Conversion event**: must specify backend product, target user, user problem, onsite result, and next-step action.
- **User research event**: focus on questionnaire, discussion, user language, problem validation, and next topic/product signal.
- **Relationship warming event**: focus on connection, trust, community experience, and low-pressure follow-up.
- **Delivery event**: focus on participant output, feedback, and testimonial material.
- **Collaboration event**: focus on partner role, traffic source, revenue split, brand boundary, and lead ownership.

Mixed events are allowed, but the primary goal must be named.

### Topic Design

A strong offline topic should satisfy:

- It is concrete enough for users to know why to show up.
- It solves a front-end problem related to the backend product.
- It can create an onsite result within the event duration.
- It naturally exposes why some users need deeper paid support.
- It is not just the backend product name disguised as an activity.

Avoid topics that are too broad, such as "AI growth salon", "personal improvement", "future trends", or "let's talk about business", unless the user has a strong existing community and trust.

### Onsite Design

Offline events should not be only speeches. Include at least one of:

- self-introduction with a problem template
- diagnostic worksheet
- case teardown
- live demo
- participant practice
- group discussion
- question wall
- result sharing
- 7-day action plan

End with a concrete承接 action:

- add WeChat
- join follow-up group
- complete diagnosis form
- book consultation
- receive material pack
- apply for backend product
- join next event

### Follow-Up

The 24-72 hours after the event are the conversion window.

Segment users:

- A: high-fit, clear pain, active interaction, budget or strong urgency. Follow up personally.
- B: interested but early-stage. Nurture in group and invite to the next step.
- C: connection or observation users. Keep light relationship and content touch.
- D: low-fit users. Do not push conversion.

## AI Integration Points

Use AI for:

- event theme options and topic risk checks
- recruitment copy variants
- poster copy structure
- registration questionnaire design
- questionnaire analysis and user segmentation
- project plan and material checklist
- onsite agenda and host script
- talk/PPT outline
- group operation reminders
- feedback questionnaire
- follow-up copy
- recap article, Moments post, short video topics, and next-event assets

Keep human confirmation on:

- backend product and promise
- target user and unsuitable audience
- pricing, refund, and cost decisions
- partner/resource boundaries
- public claims and sensitive data
- final copy before publishing
- final event promise, consent wording, and actual delivery capacity

## Public Case And Privacy Rules

- Public event details supplied by the organizer may be used as teaching cases.
- Keep the case at the level of event goal, audience, topic, process, onsite result, follow-up, and reusable judgment.
- Remove or generalize participant names, contact details, private conversations, unpublished business data, and identifiable screenshots.
- Distinguish `公开事实`, `主办方判断`, `待核验结果`, and `可迁移经验`.
- Do not fabricate attendance, revenue, conversion rate, testimonials, or participant outcomes.
- When the user provides no case, use a blank case-card template instead of inventing a success story.

## Reference Routing

- Read `references/methodology.md` when the user asks for the underlying logic, course explanation, or why each step matters.
- Read `references/output-templates.md` when producing the fixed execution pack, worksheets, copy formats, project plan, or follow-up assets.

## Quality Check

Before finalizing, verify:

- The event has a clear backend or next-step承接.
- The topic is tied to a real front-end problem, not only the organizer's preferred theme.
- The participant has a reason to attend offline rather than consume free online content.
- The onsite agenda includes interaction or output.
- The recruitment copy names suitable and unsuitable audiences.
- The plan includes T-minus tasks and next actions.
- The follow-up does not rely only on group broadcast.
- AI is used as a project assistant, not as the strategy owner.
- The plan is executable by a first-time organizer, with owners, deadlines, acceptance checks, and fallback actions.
- Missing information is labeled instead of silently invented.
- Public cases contain no participant privacy or private platform/path assumptions.
