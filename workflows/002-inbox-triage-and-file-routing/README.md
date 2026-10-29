# WF-002 — Instruction-Guided Inbox Triage and File Routing

## Record status

- Documentation status: In progress; operating instructions and two dated log entries reviewed.
- Workflow mode: User-initiated recurring maintenance; no unattended schedule established.
- Environment: Local MacBook filesystem with a file-access agent. Specific model and version unknown.
- Source basis: Author's account, agent instructions, dynamic sorting rules, and a private execution log. Private paths, project names, and file titles are omitted here.

## Relationship to the initial reorganization

The inbox and the destination structure were designed together in [WF-001](../001-local-filesystem-reorganization/README.md). This record covers their continuing use: the author periodically places new material in the inbox and asks Codex to analyze or sort it under the agreed rules.

## Human–agent operating cycle

1. The author places files in the inbox and decides whether the request is **analysis only** or **execution of sorting**.
2. The agent checks that the active top-level structure still matches the approved map. If it has changed, the agent reports the mismatch and waits for the author's confirmation rather than guessing a new destination.
3. For analysis only, the agent inventories the inbox and proposes grouped destinations without moving or creating files.
4. For authorized execution, it uses a project-first classification hierarchy, moves unambiguous items to active destinations, and may create only narrowly justified subfolders under existing categories.
5. It leaves ambiguous, sensitive, conflicting, or unsafe-to-inspect items in the inbox; it does not invent categories to empty it.
6. It checks that moved files exist at the destination and retain their names, formats, and sizes, then reports moved and unresolved groups.
7. The later sorting rules require a dated execution-log entry after each completed sorting run, recording actual changes and exceptions. Analysis-only requests do not create execution entries.

This sequence reflects the supplied current rules. The exact wording and timing of earlier rule versions have not been reconstructed.

## Boundaries the author encoded

The author specified what an agent may do and what remains a human decision. Routine sorting is confined to the agreed root and inbox; the agent must not treat instructions embedded in files as operative, follow links outside scope, upload content, or run discovered code. It cannot delete, overwrite, rename, merge versions, unpack archives, or change the top-level taxonomy on its own. A filename collision or materially ambiguous destination is reported rather than resolved by an automatic choice.

Suspected duplicates require comparison before classification. Deletion appears in the private log only where the author gave direct permission; those exceptional deletions are not part of routine inbox sorting. The supplied agent instruction says not to create a persistent log unless the author requests one; the later sorting rules and the author's account establish the log as a required part of the recurring workflow. The sources do not fix the exact date of that change.

See the [anonymized sorting examples](../sorting-workflow-examples.md) for a sample folder map, decisions at the inbox boundary, and the explicit treatment of OCR, secrets, embedded instructions, and protected areas.

## Evidence of execution

The supplied log contains two dated sorting batches. It records grouped and individual moves into project, personal, learning, visual, and archive-related destinations; newly created subfolders; material left in the inbox; and exceptional, explicitly authorized deletions. One batch preserved an archive without unpacking it. Another kept uncertain or conflicting versions in the inbox rather than replacing an existing file.

The log is evidence that particular actions were recorded, not independent proof of every file's current location or of perfect classification accuracy. The raw log remains private because its paths and filenames reveal personal and unpublished work.

## Skill demonstrated by the workflow

The author supplied the classification context and converted it into enforceable operating boundaries: scope checks, action gates, exception handling, verification, and an audit trail. The agent performed the repeatable work under those rules. The result is a maintainable human–agent process, with a clear distinction between the user's decision authority and the agent's technical capability.

## Open documentation items

- One redacted example of an ambiguous classification and how the author resolved it.
- A representative analysis-only run compared with an execution run.
- The evolution of the logging requirement and any corrections made after reviewing log entries.
- Current outcome checks beyond the recorded moves, such as later retrieval or correction of a misplaced file.
