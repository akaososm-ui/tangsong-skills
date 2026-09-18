# tangsong-skills

公开的 AI 工作流 Skill 集合，服务于真实的商业、内容、知识库与交付场景。

## 创作者与联系

创作者：唐宋AI商业教练

擅长商业闭环设计，专注于流量变现、产品设计、营销成交与 AI 赋能商业化。

提供线上陪跑、一对一咨询、社群 + 知识库服务。

微信：`tangsong0099`

This repository currently publishes Tang Song workflow skills:

| Skill | Use case | Main outputs |
| --- | --- | --- |
| `student-consultation-content-workflow` | Process a student consultation Feishu minutes link or transcript end to end. | Consultation report archive, material package, Moments draft, WeChat article draft, and short-video scripts. |
| `tangsong-humanize-writing` | Reduce AI traces in drafts and revise them into a more natural Tang Song style. | Short diagnosis, V2 rewrite, targeted replacement snippets, or edited document status. |
| `tangsong-getnote-benchmark-video-transcriber` | Incrementally organize videos from a GetNote benchmark blogger knowledge base. | One Markdown file per video, original transcript, review markers, summary, and source metadata. |
| `tangsong-skill-github-publisher` | Publish local skill folders to a GitHub skills repository. | Public-safety scan, validation, README/VERSION update, push, and npx discovery verification. |
| `tangsong-knowledge-closet-builder` | Build a minimal AI-callable personal knowledge base around real business outputs. | Material inventory, staged classification, minimal folder framework, reusable assets, and a 7-day action plan. |
| `tangsong-ai-collaborative-reading` | Read important books with AI section by section from WeRead, paper books, PDFs, EPUBs, web materials, scans, photos, or voice notes. | Reading task sheet, collaboration records, understanding cards, and whole-book synthesis. |
| `tangsong-viral-content-deconstructor` | Deconstruct benchmark content from Douyin, Xiaohongshu, WeChat, GetNote, Feishu, local files, images, video, audio, or pasted text. | Evidence-grounded teardown card saved to a local content teardown library, with source limits and migration hypotheses. |
| `tangsong-product-pain-solution` | Help creators and entrepreneurs turn a product idea, customer problem, capability, or underperforming offer into one focused product definition. | Core pain, priority customer, product/solution structure, delivery boundary, pain-to-sell-point map, and price reference. |
| `tangsong-personal-ai-manual` | Turn a person's real identity, work, goals, preferences, boundaries, and source locations into a reusable AI collaboration manual. | Practical personal AI manual, copy-ready instruction block, community worksheet, and missing-information checklist. |
| `tangsong-business-content-engine` | Turn one real content mother into a business-driven weekly package for WeChat Moments, WeChat Official Account, and short-video scripts. | Content mother card, 27-unit weekly matrix, three platform drafts, generation rule card, and reviewed weekly package. |
| `ai-course-builder` | Turn real teaching experience, learner problems, and course materials into a reviewable class or curriculum. | Course brief, experience map, outline, teaching package, learner exercises, review gates, and retrospective assets. |
| `tangsong-opc-offline-event-planner` | Design and execute a first or repeat OPC offline event that creates an onsite result and supports a clear backend next step. | Complete event strategy, recruitment and poster copy, registration questions, project schedule, role and material checklists, onsite agenda, follow-up, recap, and public case card. |
| `tangsong-community-operations-agent` | Design and operate a private-domain community or group chat from zero to one, or fix an existing one. | Positioning card, the four core assets (group name, announcement, rules, poster copy), operations plan with layering and effort allocation, and a separate boundary and compliance check. |

## Install

Install all skills in this repository:

```bash
npx -y skills add akaososm-ui/tangsong-skills -g --all
```

List available skills:

```bash
npx -y skills add akaososm-ui/tangsong-skills --list
```

Install one skill:

```bash
npx -y skills add akaososm-ui/tangsong-skills --skill student-consultation-content-workflow -g
npx -y skills add akaososm-ui/tangsong-skills --skill tangsong-humanize-writing -g
npx -y skills add akaososm-ui/tangsong-skills --skill tangsong-getnote-benchmark-video-transcriber -g
npx -y skills add akaososm-ui/tangsong-skills --skill tangsong-skill-github-publisher -g
npx -y skills add akaososm-ui/tangsong-skills --skill tangsong-knowledge-closet-builder -g
npx -y skills add akaososm-ui/tangsong-skills --skill tangsong-ai-collaborative-reading -g
npx -y skills add akaososm-ui/tangsong-skills --skill tangsong-viral-content-deconstructor -g
npx -y skills add akaososm-ui/tangsong-skills --skill tangsong-product-pain-solution -g
npx -y skills add akaososm-ui/tangsong-skills --skill tangsong-personal-ai-manual -g
npx -y skills add akaososm-ui/tangsong-skills --skill tangsong-business-content-engine -g
npx -y skills add akaososm-ui/tangsong-skills --skill ai-course-builder -g
npx -y skills add akaososm-ui/tangsong-skills --skill tangsong-opc-offline-event-planner -g
npx -y skills add akaososm-ui/tangsong-skills --skill tangsong-community-operations-agent -g
```

## Requirements

`student-consultation-content-workflow` is an orchestration workflow. It works best in an environment that has:

- Feishu minutes access when using a Feishu minutes link.
- `lark-cli` configured for the current user when pulling Feishu transcripts.
- Companion skills for the underlying branches:
  - `student-consultation-delivery`
  - `content-material-distiller`
  - `short-video-script-writer`

If those companion skills are not installed, the agent can still follow the written workflow, but results may be less consistent.

`tangsong-humanize-writing` can be used on pasted drafts directly. It works best when the user provides the original draft, target channel, and whether they want a full V2 or only targeted edits.

`tangsong-getnote-benchmark-video-transcriber` works best in an environment that has GetNote MCP tools connected and authorized. It does not create GetNote accounts, knowledge bases, or blogger subscriptions; those should be prepared in GetNote first.

`tangsong-ai-collaborative-reading` accepts user-provided reading material from multiple sources. It does not require WeRead. For paper books, use photos, scans, page references, or voice notes. For electronic books and web materials, provide the relevant legal excerpts or source links. It preserves source boundaries and does not download or reproduce complete copyrighted books.

`tangsong-viral-content-deconstructor` requires three inputs before a formal teardown: complete, reviewable raw content; the user's business context; and the intended content direction. If built-in Browser/Chrome, GetNote, Feishu, or local acquisition cannot obtain the raw material, it stops and asks the user for the original text, file, transcript, screenshots, or media instead of inferring from a title or summary. It preserves the distinction between evidence, observation, inference, and unverified assumptions; it does not generate imitation copy by default. Its default local output is the current Obsidian Vault's `02-处理/爆款内容拆解库/`.

`tangsong-personal-ai-manual` works best when the person provides current, stated information about their identity, work or business, goals, AI experience, channels, workflows, preferences, and boundaries. Missing facts are marked as `待补` rather than invented. It does not require a specific external connector; users can provide answers, notes, profiles, or source paths directly.

`ai-course-builder` works from the instructor's real experience, learner problems, evidence, and authorized course materials. It does not require Obsidian, Feishu, or a specific presentation tool. When essential inputs are missing, it returns an intake brief instead of inventing a finished course. It keeps human review gates before visual production or publishing and includes privacy, copyright, and provenance checks.

`tangsong-skill-github-publisher` works best in an environment that has local `git`, GitHub CLI authentication, and a target GitHub skills repository. It can also prepare a local GitHub-ready package when push permissions are not available.

`tangsong-knowledge-closet-builder` works best when the user can provide a real business or project context, a consistent content or delivery goal, and an initial set of existing materials. It starts with a minimal staged framework and does not invent business facts or build a complex taxonomy before understanding the user's workflow.

`tangsong-business-content-engine` does not require Feishu, Obsidian, a specific model, or an external connector. It works from pasted text or user-provided files. The default workflow is staged: it produces a content mother, matrix, and three platform drafts first, then waits for user edits and confirmation before generating the full weekly package. It does not publish automatically and does not treat reach metrics as proof of sales.

`tangsong-opc-offline-event-planner` is designed for a complete, executable event pack rather than light/standard/advanced variants. It works from the organizer's real business, audience, event constraints, and public or authorized case material. It does not require Obsidian, Feishu, a local folder, or a private writing-style Skill. Missing information is labeled for confirmation; participant privacy, contact details, consent, and unverified results must not be published.

`tangsong-community-operations-agent` works from the operator's real business problem, audience, monetization model, and sustainability. It delivers one complete pack instead of light/standard/advanced variants, and it will not write a group name, announcement, rules, or poster copy before the positioning is clear. It refuses to design planted-member or fake-user tactics, and it will not invent member counts, revenue, testimonials, or conversion results. It runs a separate boundary and compliance pass covering fake demand, fabricated results, undeliverable promises, unattributed third-party material, privacy exposure, and platform risk. It does not require Feishu, Obsidian, or a specific connector.

## Usage

After installation, ask your agent with a consultation source:

```text
Use $student-consultation-content-workflow to process this consultation minutes link end to end.
```

You can also paste a transcript instead of a Feishu minutes link.

For AI-trace reduction:

```text
Use $tangsong-humanize-writing to diagnose and revise this draft into a more natural Tang Song style.
```

For GetNote benchmark video organization:

```text
Use $tangsong-getnote-benchmark-video-transcriber to check my GetNote connection, find the benchmark blogger knowledge base, and test one video transcript into local Markdown.
```

For publishing a local skill:

```text
Use $tangsong-skill-github-publisher to publish this local skill folder to my GitHub skills repository and verify npx discovery.
```

For a complete OPC offline event pack:

```text
Use $tangsong-opc-offline-event-planner to design and execute a complete offline event that can support my backend offer. I have not run an event before, so include owners, deadlines, acceptance checks, materials, onsite flow, follow-up, and public-case/privacy checks.
```

For building a personal knowledge base:

```text
Use $tangsong-knowledge-closet-builder to help me build a minimal AI-callable knowledge base framework from my existing materials.
```

For product pain and solution definition:

```text
Use $tangsong-product-pain-solution to help me define one product's core pain, priority customer, solution, delivery structure, and price range.
```

For a personal AI collaboration manual:

```text
Use $tangsong-personal-ai-manual to help me draft a practical personal AI collaboration manual from my real background and workflows.
```

For a business-driven weekly content package:

```text
Use $tangsong-business-content-engine to turn my real content mother into a weekly private-domain sales content package. Start with input diagnosis and a 7-day matrix; do not batch-generate until I confirm the three platform drafts and the generation rules.
```

For course design:

```text
Use $ai-course-builder to turn my teaching materials into a reviewable, deliverable course plan.
```

For building or fixing a community:

```text
Use $tangsong-community-operations-agent to position my community from zero. Ask me the seven positioning questions first, then produce the group name, announcement, rules, and poster copy, then run the boundary check. Do not write any copy before the positioning is clear.
```

## Privacy

These workflows may process consultation material, private drafts, benchmark research notes, and community member data. Before publishing outputs externally, review all drafts for client privacy, personal details, sensitive business information, transcript accuracy, and claims that require proof.

## License

MIT License. See [LICENSE](LICENSE).
