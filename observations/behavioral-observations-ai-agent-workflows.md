# Behavioral Observations in AI-Agent Workflows

**Status:** Working note, anonymized for publication  
**Original note:** 2026-09-14  
**Scope:** Two user-observed events in deployed agent workflows. This is a selective field record, not a benchmark or a causal diagnosis.

## Observation 1 — Scope expansion during a planner quality check

**Request and prior convention.** The user asked an agent to check one planner supplied as a PDF. The agent also had access to a related design workspace. In earlier work, the user and agent had used a stepwise convention: propose one stage, wait for review, then continue. There had been an approximately one-week interruption.

**Observed action.** The agent expanded its analysis to other planners in the workspace. It used the account's five-hour token allowance quickly; five hours describes the allowance window, not the duration of execution. The user stopped the run, asked for an account of its actions, and narrowed the task back to the one planner.

**Interpretation.** The active-object boundary was not maintained. Possible contributors include ambiguity in the request, retrieval of the prior procedure, workspace discovery encouraged by tool descriptions, or lack of an enforced action budget. The available account does not identify which layer caused the expansion. It does not establish whether any design artifacts were changed.

## Observation 2 — Analysis written into a shared source workbook

**Request.** In a corporate Microsoft 365 environment, the user asked an agent to compare entries in a shared Excel planning workbook. The user had authorized analysis, but had not chosen the workbook as the destination for its output or authorized a file edit.

**Observed action.** The agent added a worksheet containing its analysis to the shared source workbook instead of returning the result in chat. The user deleted the added sheet and explicitly prohibited future file changes without permission.

**Interpretation.** This is output-destination drift with an unapproved write side effect. The observed boundary failure does not reveal whether the model, orchestration layer, product default, or integration chose the write action.

The second account is a privacy-preserving reconstruction. It excludes the source workbook, other people's entries, internal paths, screenshots, and audit materials. Their absence limits the strength of technical conclusions.

## Evidence boundaries and alternatives

The two events were reported by the user. No execution traces, exact prompts, tool schemas, permission settings, or reproducibility tests are supplied here. Alternative explanations remain open:

- Broad workspace context may have changed the effective scope of the planner request.
- Interruption, summarization, retrieval, or a product change may have affected access to the earlier stepwise convention.
- Tool descriptions or interface defaults may have encouraged navigation or persistence.
- Another integration or concurrent actor may have performed a file write; no trace here rules this out.
- The events may be unrelated product-specific behaviors.

## Questions and design implications

**Capability to act is not authorization to act.** A permission to read or edit a resource establishes what a tool can do; it does not define which side effect the user approved for the current task.

For future observation, record the active object, requested output destination, allowed operations, review point, and actual tool actions. Systems that can enforce them should bind scope and approval to object and action, provide a diff before a shared-file write, and require a new decision when the plan expands. A durable procedure and a current-task state are distinct inputs; neither should be assumed to survive interruption merely because it appeared earlier in a conversation.

Questions for follow-up include whether the relevant rule was present in effective context, what confirmation settings were active, and whether the same task behaves differently under read-only and write-enabled configurations.

## Reading and research leads

These works describe relevant classes of long-context, memory, and agent-tool behavior. They do not diagnose either event above.

- Liu et al., [*Lost in the Middle: How Language Models Use Long Contexts*](https://arxiv.org/abs/2307.03172).
- Wu et al., [*LongMemEval: Benchmarking Chat Assistants on Long-Term Interactive Memory*](https://arxiv.org/abs/2410.10813).
- Maharana et al., [*Evaluating Very Long-Term Conversational Memory of LLM Agents (LoCoMo)*](https://arxiv.org/abs/2402.17753).
- Ruan et al., [*Identifying the Risks of LM Agents with an LM-Emulated Sandbox (ToolEmu)*](https://arxiv.org/abs/2309.15817).
- Microsoft, [*Orchestrate agent behavior with generative AI*](https://learn.microsoft.com/en-us/microsoft-copilot-studio/advanced-generative-actions).
