---
name: workflow-to-skill
description: "Create or improve reusable agent skills from spoken explanations, transcripts, screen walkthroughs, SOPs, or demonstrated workflows. Use when the user wants to teach an agent a repeatable job and save how to do it as a skill."
---

# Workflow to Skill

Turn a person's explanation of a job into instructions another agent can use to do it reliably. Start with the work and the desired result. Decide where AI, ordinary automation, or human judgment belongs after the process is understood.

Treat the explanation like onboarding a capable new colleague: capture what they need to accomplish, what information they need, how decisions are made, and how they will know the job is done. Preserve the whole process without requiring a click-by-click account of routine actions.

## Understand the job

Use the material already supplied: a voice transcript, written explanation, screen recording, example output, or existing procedure. A rough spoken explanation is enough to start; do not require a polished SOP or a particular recording tool.

Extract the following where relevant:

- **Outcome and trigger:** What starts the work, and what should exist when it is finished?
- **Inputs and access:** What information, accounts, documents, or examples does the worker need?
- **Current process:** What happens today, in what order, and where is time being spent?
- **Decisions:** What rules determine the next action, and where is judgment needed?
- **Output and quality:** Where does the result go, and what makes it correct or useful?
- **Exceptions:** What happens when information is missing, access fails, or the result cannot be verified?

Remove filler, repetitions, tangents, and irrelevant personal details. Repair obvious transcription errors when context is clear. Preserve uncertainty around ambiguous product names, missing rules, or unclear steps instead of turning guesses into instructions.

When a recording is provided, use the visual evidence if accessible. If only its transcript is accessible, say so when that limits what can be learned; do not claim to have observed screens or actions. Use documentation supplied by the user, and verify current application-specific behavior through available tools or authoritative documentation when needed. Never invent interface labels, API capabilities, or successful executions.

Ask only for missing details that materially change the skill. Prefer a concrete question such as “What makes a lead qualified?” over asking the user to explain the entire workflow again. Continue with independent work while waiting, and make nonblocking assumptions visible.

## Find the reusable process

Separate stable rules from details that change each run. Turn a particular customer, date range, workspace, campaign, or file path into an input unless it is an intentional permanent constraint. Keep credentials out of skill files.

Identify the actual bottleneck before proposing tools. Consider simplifying or removing unnecessary steps. Use deterministic code or ordinary automation for fixed transformations; use AI when interpretation or judgment adds value. Preserve human decisions where the workflow requires them. Do not add an agent, integration, or recurring automation simply because the source mentions one.

Scope the skill around a coherent job with a recognizable trigger and result. A large workflow can become several skills if its parts are independently useful, but do not fragment a simple procedure. Check for an existing relevant skill before creating a duplicate; update or extend it when that fits the request.

If the source says only “make this more efficient” or “use AI,” first identify an actual task. A usable starting point might be “Each morning, review today's calendar and flag meetings missing preparation notes.” Do not pretend an undefined goal is an executable process.

## Learn and demonstrate within scope

If the user authorized doing the underlying job, work through a representative example using available tools. Capture the rules, dependencies, and verification that made it work. If the user requested only skill creation, use the supplied evidence and safe inspection; saving a skill does not authorize sending messages, changing live workflows, or other external actions.

Describe the evidence accurately: documented, inspected, simulated, or executed. A successful demonstration is useful evidence, but one case does not establish every branch. Keep unverified steps and missing access explicit rather than claiming the skill has been proven.

## Write the skill

Create the skill in the user's chosen folder. When no destination is specified, follow the host's normal discoverable skill location. Keep source material unchanged and put new files outside read-only or synced reference directories.

Use a short lowercase hyphenated folder name and a `SKILL.md` containing YAML frontmatter with `name` and `description`. Make the description explain the task and when to invoke it. Use the host's available skill-authoring guidance and validator when applicable.

Write the body as direct instructions to the agent doing the job. Include only what helps it act correctly:

- The expected result and required inputs.
- The process and decision rules learned from the evidence.
- Necessary tools, access, and prerequisites, distinguishing requirements from preferences.
- Observable completion checks and meaningful exception handling.
- Any real limits on actions, retries, or scope.

Keep stable, tool-independent workflow logic separate from environment-specific instructions where useful. Be explicit about required integrations; portability does not mean every agent has the same tools or access. Do not copy the speaker's tool preferences, subscription prices, or casual examples into universal requirements.

Keep short skills self-contained. Add references for substantial conditional details, scripts for repeated operations that benefit from deterministic execution, and assets only when the output needs them. Link supporting files from the skill and explain when to use them. Do not attach the entire transcript when distilled instructions are enough.

## Check and improve

Validate the file structure and frontmatter. Then walk a representative request through the instructions: can a fresh agent identify the inputs, choose the correct branch, produce the output, and tell whether it succeeded? Check a materially different branch when the workflow has one. Run any new scripts with safe sample data and inspect the output.

When evidence reveals a gap, improve the process or ask for the missing rule before adding more automation. Use later real outcomes to refine the skill narrowly; do not turn every one-off exception into a permanent requirement.

Deliver the finished skill with its location, a brief explanation of what it does, and an example invocation. State material verification limits or unresolved dependencies. Creating a skill in a project folder does not by itself establish that it is installed or automatically available in other agents.

## Example: a CRM workflow walkthrough

A user records how they create a follow-up workflow in a CRM and asks for a reusable skill. Extract the enrollment trigger, eligibility filters, timing, exit conditions, and expected outcome. Confirm whether the request covers drafting, saving, or activating the workflow. Verify application-specific mechanics through available evidence. Parameterize the campaign-specific details and preserve the business rules. If activation has not been authorized, skill creation can still finish with instructions that require authorization before activation. Do not infer permission to contact leads from a demonstration.
