---
name: tangsong-humanize-writing
description: Tang Song AI trace reduction and natural rewrite workflow. Use when the user asks to 去AI味, 降低AI痕迹, 拟人化文本, 改得更像真人/唐宋, or revise AI-looking drafts for社群日课、公众号、朋友圈、课程/工具说明、咨询交付文案 while preserving meaning, facts, and user intent.
---

# Tang Song Humanize Writing

## Positioning

Revise text so it reads less like a polished AI answer and more like Tang Song's live, grounded expression.

Do not "fake humanity" by randomly adding slang, typos, jokes, or unnecessary personal confession. Preserve the original meaning, facts, audience, and use case. Remove template patterns, loosen over-perfect structure, add concrete judgment, and keep the user's own style.

## Default Workflow

1. Identify the text type: 社群日课, 公众号, 朋友圈, 短视频脚本, 产品/工具说明, 咨询交付, or formal document.
2. Read `references/ai-writing-patterns.md` when the draft has obvious AI template language or the user explicitly says 去AI味, AI痕迹, or 拟人化.
3. For Tang Song public/private content, prefer the user's local writing style and business positioning. If `tangsong-writing-style` is available and the task is positioning-sensitive, use it too.
4. Do a short diagnosis first unless the user explicitly says "直接改".
5. Rewrite only the parts that create AI smell. Do not rewrite the whole draft when 3-5 local edits are enough.
6. Preserve original facts, examples, headings, calls to action, and document structure unless structure itself is the problem.
7. Return either:
   - full revised text, when the user asks for a new version;
   - targeted replacement snippets, when the user wants comparison or wants to preserve the original;
   - a changed file/doc status, when editing a local file or online document.

## Editing Rules

Prefer these moves:

- replace polished conclusions with plain observations or concrete consequences;
- break uniform lists and "三点式" into uneven, natural explanation;
- turn vague systems language into a specific action;
- add first-person judgment only where the user's material supports it;
- keep small hesitations, local examples, and "I just did this" context;
- shorten abstract endings instead of adding a bigger moral.

Avoid these moves:

- do not add fake stories, fake data, fake client details, or invented "真实感";
- do not overuse "说实话", "我越来越觉得", or "坦白讲" as a new template;
- do not turn every paragraph into short single-line punchlines;
- do not delete technical terms that are actually necessary;
- do not remove all structure from tutorials; readers still need to scan steps.

## Tang Song-Specific Target

For Tang Song public/private content, make the text feel like:

- 刚做完一次真实工作后的复盘;
- 一边讲给社群听, 一边把可复制动作拆出来;
- 有判断、有现场感、有业务动作, but not a motivational essay.

Good signs:

- starts from a recent action or real reader problem;
- explains why the problem appears in work;
- gives a concrete "今天可以做什么";
- leaves some natural roughness.

Bad signs:

- too complete, too evenly structured;
- every section ends with a polished slogan;
- too many "不是 X, 而是 Y" reversals;
- "建立系统", "形成闭环", or "提升效率" appears without a concrete action.

## Use The Real Example

Read `references/knowledge-base-daily-lesson-example.md` when revising a social lesson, tool tutorial, knowledge-base article, or Tang Song-style educational content. It contains the real V1 -> V2 -> targeted edit pattern from the knowledge-base daily lesson.

## Output Format

When creating a new version:

```markdown
## V2

{revised text}

## 改动说明
- {only the meaningful changes}
```

When doing targeted edits:

```markdown
**第 1 处**
原文：...
改法：...
理由：...
```

When editing a local or online document:

- preserve the original unless the user asks to overwrite;
- create a V2 copy or apply targeted edits to the named version;
- verify by rereading the changed document.
