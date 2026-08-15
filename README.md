# tangsong-skills

Public skill experiments from Tang Song's AI business workflow system.

This repository currently publishes Tang Song workflow skills:

| Skill | Use case | Main outputs |
| --- | --- | --- |
| `student-consultation-content-workflow` | Process a student consultation Feishu minutes link or transcript end to end. | Consultation report archive, material package, Moments draft, WeChat article draft, and short-video scripts. |
| `tangsong-humanize-writing` | Reduce AI traces in drafts and revise them into a more natural Tang Song style. | Short diagnosis, V2 rewrite, targeted replacement snippets, or edited document status. |
| `tangsong-getnote-benchmark-video-transcriber` | Incrementally organize videos from a GetNote benchmark blogger knowledge base. | One Markdown file per video, original transcript, review markers, summary, and source metadata. |
| `tangsong-skill-github-publisher` | Publish local skill folders to a GitHub skills repository. | Public-safety scan, validation, README/VERSION update, push, and npx discovery verification. |
| `tangsong-ai-collaborative-reading` | Read important books with AI section by section from WeRead, paper books, PDFs, EPUBs, web materials, scans, photos, or voice notes. | Reading task sheet, collaboration records, understanding cards, and whole-book synthesis. |
| `tangsong-viral-content-deconstructor` | Deconstruct benchmark content from Douyin, Xiaohongshu, WeChat, GetNote, Feishu, local files, images, video, audio, or pasted text. | Evidence-grounded teardown card saved to a local content teardown library, with source limits and migration hypotheses. |

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
npx -y skills add akaososm-ui/tangsong-skills --skill tangsong-ai-collaborative-reading -g
npx -y skills add akaososm-ui/tangsong-skills --skill tangsong-viral-content-deconstructor -g
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

`tangsong-skill-github-publisher` works best in an environment that has local `git`, GitHub CLI authentication, and a target GitHub skills repository. It can also prepare a local GitHub-ready package when push permissions are not available.

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

## Privacy

These workflows may process consultation material, private drafts, and benchmark research notes. Before publishing outputs externally, review all drafts for client privacy, personal details, sensitive business information, transcript accuracy, and claims that require proof.

## License

MIT License. See [LICENSE](LICENSE).
