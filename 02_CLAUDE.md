\# Znu Salesforce Agent Rules



Version: 0.2



\## 1. Authority



The approved PRD defines what the product must do.



The approved BUILD specification defines how the approved requirements are

implemented in Salesforce.



The agent may implement approved specifications. It may not silently change,

reinterpret, expand, or remove requirements.



If the specifications are ambiguous, contradictory, incomplete, or require

a decision reserved for a human, stop and report the issue.



\## 2. Source of Truth



Before modifying Salesforce source, read:



1\. 01\_PRD\_demo.md

2\. 03\_BUILD\_demo.md

3\. 04\_GATES\_demo.md

4\. 05\_ADDENDA\_demo.md



Only APPROVED requirements, build specifications, and addenda authorize

implementation work.



\## 3. Salesforce Rules



\- Use Salesforce source-format metadata.

\- Prefer declarative components.

\- Do not create Apex unless explicitly authorized.

\- Do not modify profiles.

\- Use permission sets for field access.

\- Do not introduce components without specification traceability.

\- Preserve descriptions and user-facing Help Text required by the BUILD specification.

\- Treat successful deployment as technical evidence, not product acceptance.



\## 4. Human-Facing Design



Technical validity does not establish usability.



For user-facing metadata:



\- use plain business language;

\- prioritize information useful to the user;

\- keep inline Help Text concise;

\- avoid exposing unnecessary implementation terminology;

\- follow the user-facing standards in the approved BUILD specification.



Do not replace specified user-facing text with agent-generated alternatives

unless explicitly authorized.



\## 5. Privacy and Data Classification



Do not infer legal, privacy, GDPR, or data-classification decisions.



Where classification requires human confirmation, stop at the applicable

gate and report the unresolved decision.



Do not introduce additional personal-data storage unless explicitly authorized.



\## 6. Validation



After generation:



\- inspect generated source;

\- deploy to the designated disposable scratch org;

\- report deployment success or failure;

\- verify implemented artifacts against their specification;

\- report deviations rather than silently correcting requirements.



A failed acceptance criterion remains failed until resolved.



Absence of an error does not establish that an acceptance criterion passed.



\## 7. Observability and Completion Evidence



Successful execution must be observable. Silent success is not sufficient

evidence of completion.



For each build or validation run, report:



\- what actions were attempted;

\- which target org or environment was used;

\- whether each action succeeded or failed;

\- which acceptance criteria were evaluated;

\- evidence supporting each evaluated result;

\- unresolved warnings, assumptions, or blocked decisions;

\- the next applicable human gate.



Do not terminate a successful run without producing a completion summary.



For each applicable requirement or acceptance criterion, use exactly one of

the following states:



\- \*\*PASS\*\* — evaluated, with evidence supporting acceptance;

\- \*\*FAIL\*\* — evaluated, with evidence showing that acceptance was not achieved;

\- \*\*BLOCKED\*\* — evaluation or implementation cannot proceed without a dependency

&#x20; or human decision;

\- \*\*NOT TESTED\*\* — not evaluated during this run.



Do not report PASS solely because no error occurred.



Do not omit BLOCKED, FAIL, or NOT TESTED items from the completion summary.



A successful Salesforce deployment establishes only that the deployment

succeeded. It does not establish that all requirements passed.



\## 8. Human-Only Actions



The agent must never independently:



\- promote a Salesforce package version;

\- approve its own PRD or BUILD specification;

\- approve unresolved privacy or data-classification decisions;

\- declare a release accepted;

\- bypass a failed human gate.



Package promotion is always an explicit human decision.



\## 9. Change Control



Discoveries that require requirements or architecture changes must be

recorded in 05\_ADDENDA\_demo.md and approved before implementation.



Do not silently convert discoveries into implementation decisions.

