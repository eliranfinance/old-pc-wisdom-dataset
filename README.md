# Old PC Wisdom Dataset

A small, curated dataset of durable troubleshooting and maintenance principles distilled from a Hebrew home-computing archive from the mid-2000s.

This is a **knowledge dataset**, not an archive of the original articles and not a current hardware compatibility database. It preserves generalizable reasoning patterns while removing passwords, IP addresses, dead links, unsafe attack instructions, and version-specific commands.

## Dataset fields

Each JSONL record contains:

- `id` — stable record identifier
- `topic` — broad subject
- `principle` — reusable lesson
- `safe_modern_form` — how to apply it today
- `verification` — observable check
- `risk_notes` — boundaries and failure modes
- `source_themes` — archive themes, not copied article text
- `status` — `durable`, `contextual`, or `excluded`

## Use

```python
import json

with open("data/old_pc_wisdom.jsonl", encoding="utf-8") as f:
    records = [json.loads(line) for line in f]
```

Good uses include retrieval demos, evaluation sets for documentation assistants, educational examples, and historical computing research. Do not treat the records as a substitute for current vendor documentation, recovery procedures, or security advice.

## Included language-model skill

The `skill/` directory contains `SKILL.md`, a portable skill for Claude, ChatGPT, Grok, and other language models. It tells the model how to retrieve the dataset's principles, modernize them for the user's current environment, cite record IDs, verify each action, and refuse unsafe historical instructions.

- Claude: upload or install `skill/SKILL.md` as a project skill.
- ChatGPT or Grok: paste `skill/portable-prompt.md` into project or system instructions, and provide `data/old_pc_wisdom.jsonl` as context when needed.
- Other models: use the same files as a system prompt plus a local JSONL knowledge source.

## Safety and provenance

The source material included obsolete Windows instructions, piracy-related material, account-compromise attempts, malware, denial-of-service ideas, exposed addresses, and old download links. Those details are intentionally excluded or converted into defensive principles. The records are original synthesis rather than copied source prose.

## License

MIT. The dataset is a new curated synthesis; the source archive is not redistributed here.
