# tangsong-skills

Public skill experiments from Tang Song's AI business workflow system.

This repository currently publishes one workflow skill:

| Skill | Use case | Main outputs |
| --- | --- | --- |
| `student-consultation-content-workflow` | Process a student consultation Feishu minutes link or transcript end to end. | Consultation report archive, material package, Moments draft, WeChat article draft, and short-video scripts. |

## Install

Install all skills in this repository:

```bash
npx -y skills add akaososm-ui/tangsong-skills -g --all
```

List available skills:

```bash
npx -y skills add akaososm-ui/tangsong-skills --list
```

Install only this skill:

```bash
npx -y skills add akaososm-ui/tangsong-skills --skill student-consultation-content-workflow -g
```

## Requirements

This skill is an orchestration workflow. It works best in an environment that has:

- Feishu minutes access when using a Feishu minutes link.
- `lark-cli` configured for the current user when pulling Feishu transcripts.
- Companion skills for the underlying branches:
  - `student-consultation-delivery`
  - `content-material-distiller`
  - `short-video-script-writer`

If those companion skills are not installed, the agent can still follow the written workflow, but results may be less consistent.

## Usage

After installation, ask your agent with a consultation source:

```text
Use $student-consultation-content-workflow to process this consultation minutes link end to end.
```

You can also paste a transcript instead of a Feishu minutes link.

## Privacy

This workflow is designed for consultation material. Before publishing outputs externally, review all drafts for client privacy, personal details, sensitive business information, and claims that require proof.

## License

MIT License. See [LICENSE](LICENSE).
