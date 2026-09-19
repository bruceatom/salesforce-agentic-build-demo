\# Znu Agentic Build Demo — Acceptance Gates



Version: 0.1



\## GATE-01 — Product Requirements



Required:



\- 01\_PRD\_demo.md exists.

\- Status is APPROVED.

\- Requirements and acceptance criteria are defined.

\- Implementation architecture is not embedded in the PRD.



Decision authority: HUMAN



\## GATE-02 — Build Specification



Required:



\- 03\_BUILD\_demo.md exists.

\- Status is APPROVED.

\- Build artifacts trace to approved requirements.

\- User-facing metadata standards are defined.

\- Human-only decisions are identified.



Decision authority: HUMAN



\## GATE-03 — Agent Build Authorization



The agent may generate only metadata authorized by the approved

specifications.



Expected output:



\- Lead.Znu\_Last\_Snapshot\_At\_\_c

\- Znu\_Integration\_Access permission set

\- specified field description

\- specified inline Help Text

\- required data-classification metadata, or an explicit BLOCKED result if

&#x20; human confirmation is still required



The agent must not resolve a BLOCKED human decision by inference.



Decision authority: AGENT EXECUTION / HUMAN EXCEPTION HANDLING



\## GATE-04 — Scratch Org Validation



Required:



\- source deploys successfully to the designated scratch org;

\- required components exist after deployment;

\- field configuration matches the approved BUILD specification;

\- permission-set access matches the approved BUILD specification;

\- prohibited components were not introduced;

\- implementation artifacts trace to approved specifications.



Deployment success alone does not pass this gate.



Validation results must use:



PASS | FAIL | BLOCKED | NOT TESTED



Evidence must accompany each PASS.



Decision authority: EVIDENCE + HUMAN REVIEW



\## GATE-05 — Human Usability Review



Review user-facing metadata as a Salesforce user would encounter it.



Required:



\- field label communicates its purpose;

\- Help Text is concise and legible in the Salesforce UI;

\- Help Text communicates useful business meaning;

\- unnecessary implementation terminology is absent.



Machine correctness does not substitute for this review.



Decision authority: HUMAN



\## GATE-06 — Completion Report



Before terminating the run, the agent must provide a completion summary

showing:



\- actions attempted;

\- target environment;

\- deployment result;

\- status of each applicable acceptance criterion;

\- evidence for PASS results;

\- all FAIL, BLOCKED, and NOT TESTED items;

\- unresolved warnings or assumptions;

\- next required human gate.



Silent success is not acceptable completion evidence.



Decision authority: AGENT REPORTING / HUMAN REVIEW



\## GATE-07 — Release and Promotion



Package creation, package-version promotion, release, and customer

distribution are outside the scope of this demo.



In a production workflow, package promotion requires explicit human

authorization.



The agent must never execute package promotion autonomously.



Decision authority: HUMAN ONLY

