---
name: student-consultation-content-workflow
description: "Use when a user gives a student consultation Feishu minutes link or transcript and wants the full default workflow: consultation report archive plus reusable content extraction and channel drafts."
---

# Student Consultation Content Workflow

## Overview

This is the orchestration skill for one-click consultation processing.

When the user provides a consultation minutes link or transcript, run the full workflow by default without asking whether to continue to the next content step.

The workflow has two parallel branches:

1. **Consultation delivery branch**: source note, formal/prospect report, Obsidian archive, Feishu archive, PDF when applicable.
2. **Content production branch**: material package, content angles, Moments drafts, WeChat article topics and selected draft, short-video scripts.

This skill coordinates existing layer-specific skills. It does not replace them.

## Trigger Rules

Use this skill when the request includes a consultation source and any intent like:

- `咨询内容处理`
- `咨询内容工作流`
- `咨询沉淀+内容提炼`
- `学员咨询全流程`
- `咨询链接处理`
- `咨询后内容输出`
- `咨询报告和素材都做`
- `打通咨询工作流`
- "给你咨询链接之后直接跑完"
- "不要再问我下一步，直接生成报告、素材、朋友圈、公众号、短视频"

If the user only asks for a formal report, use `student-consultation-delivery`.

If the user only asks for reusable material extraction, use `content-material-distiller`.

If the user says to run the full workflow, do not stop after either branch.

## Required Inputs

Minimum input:

- Feishu minutes link or pasted consultation transcript.

Infer the rest from the transcript whenever possible:

- nickname
- consultation date
- formal student vs prospect route
- main topic
- best content direction

Only ask the user when a missing decision would create a risky wrong archive route, such as formal student vs prospect being impossible to infer.

## Default Output Package

Every successful full workflow should produce:

### Branch A: Consultation Delivery

Use `student-consultation-delivery` rules.

- cleaned source note
- consultation report
- Feishu sync for report package
- PDF export when formal student route applies

### Branch B: Content Production

Use `content-material-distiller` first, then channel output rules.

Required outputs:

- `1` standard material package
- `3` Moments angles
- `1` full Moments draft for the strongest angle
- `3` WeChat article topic cuts
- `1` full WeChat article draft for the strongest topic
- `3` short-video topic cuts
- `3` full short-video口播 scripts

Do not ask the user which angle to write first. Select the strongest angle using:

1. privacy safety
2. business relevance
3. target-user resonance
4. evidence strength
5. current business rhythm
6. expression freshness

The user will revise later. The first pass should favor useful drafts over perfect selection.

## Recommended Output Files

Use the consultation date in `YYYY-MM-DD`.

### Material Package

Save to:

`02-处理/素材清洗/YYYY-MM-DD｜昵称咨询｜素材包.md`

### Moments

Save `3` angles and `1` full draft together unless the user asks for separate files:

`04-发布库/内容发布/朋友圈/认知朋友圈/YYYY-MM-DD｜昵称咨询｜朋友圈角度与成稿.md`

If the strongest draft is clearly conversion-oriented, use:

`04-发布库/内容发布/朋友圈/营销朋友圈/YYYY-MM-DD｜昵称咨询｜朋友圈角度与成稿.md`

### WeChat Article

Save topics and selected full draft together:

`04-发布库/内容发布/公众号/YYYY-MM-DD｜昵称咨询｜公众号选题与成稿.md`

### Short Video

Save topics and the three scripts together:

`04-发布库/内容发布/短视频/YYYY-MM-DD｜昵称咨询｜短视频选题与口播稿.md`

Create the output directory if it does not exist.

## Writing Standards

### Material Package

Follow `content-material-distiller`:

- keep original quotes separate from paraphrases
- mark fact, judgment, and inference clearly
- anonymize by default
- include public-risk handling

### Moments Angles

Each angle should include:

- angle name
- target purpose: `认知` / `情感` / `行动`
- target reader
- source material
- why it is worth posting
- risk handling

Then write the strongest full draft.

### WeChat Article Topics

Each topic should include:

- title
- core thesis
- reader pain
- evidence from the consultation
- why it is worth writing

Then write the strongest full draft, not only an outline.

Default article draft length: `1800-3000` Chinese characters.

### Short-Video Scripts

For each of the `3` selected cuts, write:

- script setting
- three hook options
- full口播 script
- scoring points
- shooting tips
- optional titles

Follow `short-video-script-writer`.

## Workflow

### 1. Pull and read source

- Extract the minute token.
- Run `lark-cli minutes minutes get --as user --params '{"minute_token":"<token>"}'`.
- Run `lark-cli vc +notes --as user --minute-tokens <token>`.
- Read the transcript before writing.

### 2. Run consultation delivery branch

- Classify formal student vs prospect.
- Generate and save source/report artifacts.
- Sync to the correct Feishu folder.
- Export PDF when required by the delivery route.

### 3. Run material distillation branch

- Generate the material package after reading the actual transcript and report.
- Save it under `02-处理/素材清洗`.
- Do not skip the material package even if channel drafts are requested.

### 4. Run channel output branch

From the material package, generate:

1. Moments angles and strongest full draft.
2. WeChat article topic cuts and strongest full draft.
3. Short-video topic cuts and three full口播 scripts.

Save every output to the recommended directories.

### 5. Final handoff

Return links/paths grouped by branch:

- local source note
- local report
- local PDF if exported
- Feishu source/report links
- material package
- Moments output
- WeChat article output
- short-video output

Also summarize:

- strongest public content angle
- strongest article topic
- strongest short-video script to shoot first

## Failure Handling

If one branch fails, continue the other branch.

Examples:

- If Feishu upload fails, still finish local report, material package, and channel drafts.
- If PDF export fails, still return docx link and local markdown.
- If transcript is unavailable but AI summary exists, mark all outputs as summary-based with lower confidence.
- If privacy risk is high, still create internal drafts but mark them `仅内部参考` and anonymize aggressively.

Do not fabricate missing facts, outcomes, student quotes, payment status, or performance data.
