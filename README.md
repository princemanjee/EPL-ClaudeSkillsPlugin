# EPL-ClaudeSkillsPlugin

226 context-engineered persona skills for Claude, built from [PromptLibrary 4.0](https://github.com/princemanjee/EngineeredPromptLibrary). Each skill is a Self-Refine / Chain-of-Thought / Plan-and-Solve (strategy varies per persona) prompt with quality dimensions, few-shot examples, and iterative refinement built in.

Install the whole set as one plugin, or enable only the task-scoped plugin you need.

## Install

```
/plugin marketplace add princemanjee/EPL-ClaudeSkillsPlugin
/plugin install prompt-library
```

Or install a single category, e.g.:

```
/plugin install pl-code-authoring
```

## Structure

- `prompt-library-plugin/` — the monolith: all 226 skills, one plugin.
- `plugins/pl-*/` — 23 task-scoped plugins, each a subset of the monolith grouped by domain (code, writing, health, business, etc.).
- `groups.json` — source of truth for which skill belongs to which task-scoped plugin.
- `scripts/split.mjs` — regenerates `plugins/pl-*/` and `.claude-plugin/marketplace.json` from the monolith. Edit `prompt-library-plugin/skills/`, never `plugins/pl-*/skills/` directly.

## Source

This is the published, standalone package. The research repo it's built from — cognitive-tools frameworks, reasoning-strategy library, upgrade methodology, prior versions — lives at [EngineeredPromptLibrary](https://github.com/princemanjee/EngineeredPromptLibrary).
