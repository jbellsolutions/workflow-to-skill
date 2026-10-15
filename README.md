# Workflow to Skill

Turn a spoken explanation, transcript, screen walkthrough, SOP, or demonstrated workflow into a reusable agent skill.

**[Read the published document](https://supple-vortex-fah6.here.now/)** · **[Download the skill ZIP](https://supple-vortex-fah6.here.now/workflow-to-skill.zip)**

Start with the job: define the outcome, understand the current process, separate stable rules from changing inputs, decide where AI helps, and write instructions another agent can follow and verify.

## Give it to an agent

Copy this prompt into your agent, then attach your transcript or describe your workflow:

> Read https://raw.githubusercontent.com/jbellsolutions/workflow-to-skill/main/SKILL.md and use it to turn the material I provide into a reusable skill. Clarify only missing details that materially affect the result, then create the skill files in my chosen folder.

If your agent cannot open URLs, download [SKILL.md](SKILL.md) and attach it with your material. Agents need their own tools and access for any underlying application work.

## Install as a skill

Copy this repository's `SKILL.md` into a folder named `workflow-to-skill` in your agent's skills directory. For Codex, the standard personal location is `~/.codex/skills/workflow-to-skill/`; you can also include `agents/openai.yaml` for its display metadata. Other agents may use different installation locations.

Once installed, try:

> Use $workflow-to-skill to turn this transcript into a reusable skill.

## Files

- [SKILL.md](SKILL.md): the complete, self-contained workflow instructions.
- [agents/openai.yaml](agents/openai.yaml): optional Codex display metadata.

The skill is based on a narrated approach to teaching agents repeatable work. It does not depend on a particular dictation tool, recording service, CRM, or AI provider. Source transcripts and account credentials are not included.
