\# Znu Agentic Build Demo — Build Specification



Status: APPROVED  

Version: 0.2  

Source Requirement: 01\_PRD\_demo.md



\## 1. Architecture Decision



REQ-001 shall be implemented as one custom field on the standard Lead object.



No Apex, Flow, trigger, custom object, or scheduled automation is required.



\## 2. Metadata Specification



\### BUILD-001 — Snapshot Timestamp Field



\*\*Object:\*\*  

Lead



\*\*Label:\*\*  

Znu Last Snapshot At



\*\*API Name:\*\*  

Znu\_Last\_Snapshot\_At\_\_c



\*\*Type:\*\*  

DateTime



\*\*Description:\*\*  

Stores the date and time at which the Znu service most recently captured

snapshot data for this Lead. This value is maintained by the Znu integration.



\*\*Help Text:\*\*  

Last Znu snapshot captured for this Lead.



\*\*Required:\*\*  

No



\### BUILD-002 — Data Classification



The field must contain explicit Salesforce data-classification metadata.



The final classification value requires human confirmation before release.

The agent must not infer a legal or privacy classification.



If the required classification has not been confirmed, the agent shall flag

the item for human review rather than silently selecting a classification.



\### BUILD-003 — Permission Set



Create a permission set.



\*\*Label:\*\*  

Znu Integration Access



\*\*API Name:\*\*  

Znu\_Integration\_Access



The permission set shall provide read and edit access to

Lead.Znu\_Last\_Snapshot\_At\_\_c.



No profile modifications are permitted.



\### BUILD-004 — User-Facing Metadata



Technically valid metadata is not sufficient for acceptance of user-facing

components.



Labels, Help Text, and other user-facing metadata must be understandable to

a Salesforce user without requiring knowledge of package architecture,

Salesforce metadata, or integration implementation.



For inline Help Text:



\- put the information most useful to the user first;

\- target 10–15 words or fewer where practical;

\- use plain business language;

\- avoid API names, metadata terminology, and unnecessary implementation detail;

\- account for the constrained size and legibility of the Salesforce Help Text UI.



The agent must not omit Help Text merely because a field's technical purpose

can be inferred from its label, API name, description, or surrounding metadata.



User-facing labels and Help Text require human review before release.



\## 3. Implementation Constraints



\- Use Salesforce source-format metadata.

\- Prefer declarative metadata.

\- Do not create Apex.

\- Do not modify standard Salesforce behavior.

\- Do not create components that cannot be traced to the approved PRD or an approved addendum.

\- Deploy first to a disposable scratch org.

\- Validate both technical correctness and user-facing metadata.

\- A successful deployment does not constitute product acceptance.



\## 4. Traceability



| Requirement | Build Artifact / Control |

| --- | --- |

| REQ-001 / AC-001 | Lead.Znu\_Last\_Snapshot\_At\_\_c |

| AC-002 | Znu\_Integration\_Access permission set |

| AC-003 | Znu\_Integration\_Access permission set |

| AC-004 | Explicit field data-classification metadata + human confirmation |

| AC-005 | Field is not required |

| CON-001 | No additional personal-data field |

| CON-002 | No automation affecting Lead behavior |

| BUILD-004 | Human review of label and inline Help Text |



\## 5. Validation Standard



Build validation has two distinct dimensions.



\### Machine Correctness



Confirm that:



\- generated metadata is structurally valid;

\- deployment to the designated scratch org succeeds;

\- field type and configuration match this specification;

\- permission-set access matches this specification;

\- prohibited components have not been introduced.



\### Human Usability



Confirm that:



\- the field label communicates its purpose;

\- Help Text is concise and legible in the Salesforce UI;

\- Help Text provides useful context to a user unfamiliar with the implementation;

\- user-facing text does not expose unnecessary technical terminology.



Passing machine validation alone is not sufficient for acceptance.



\## 6. Build Gate



No agent may generate implementation metadata until a human reviewer changes

this document's status from DRAFT to APPROVED.



Approval authorizes implementation of this specification only. It does not

authorize package-version promotion, release, or other irreversible actions.

