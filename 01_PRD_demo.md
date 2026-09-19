\# Znu Agentic Build Demo — Product Requirements



Status: APPROVED

Version: 0.1



\## 1. Purpose



Demonstrate a specification-driven Salesforce change in which an AI agent

produces implementation artifacts from an agreed product requirement.



\## 2. Product Requirement



\### REQ-001 — Last Snapshot Timestamp



For a Lead synchronized with the Znu service, Salesforce shall retain the

date and time at which Znu most recently captured snapshot data for that Lead.



\### Acceptance Criteria



\*\*AC-001 — Value\*\*

The system can store a date and time representing the most recent Znu

snapshot for a Lead.



\*\*AC-002 — Integration Access\*\*

An appropriately authorized integration user can update the value.



\*\*AC-003 — User Access\*\*

Access for Salesforce users is granted through an explicit Znu permission

set rather than assumed through profiles.



\*\*AC-004 — Data Classification\*\*

The value shall have an explicit data classification documented before release. The classification must be reflected in the Salesforce field metadata.



\*\*AC-005 — Existing Records\*\*

The requirement does not require a value for Leads that have never been

processed by the Znu service.



\## 3. Constraints



\*\*CON-001 — Personal Data\*\*

This requirement shall not introduce additional personal data.



\*\*CON-002 — Existing Salesforce Behavior\*\*

The change shall not alter Lead ownership, lifecycle, conversion, or deletion

behavior.



\## 4. Out of Scope



\*\*OUT-001\*\*

This requirement does not define how Znu authenticates to Salesforce.



\*\*OUT-002\*\*

This requirement does not define snapshot scheduling or transport.



\*\*OUT-003\*\*

This requirement does not define snapshot-object architecture or retention.



\*\*OUT-004\*\*

This requirement does not require Apex or any other specific implementation.



\## 5. Acceptance Gate



No implementation work may begin until a human reviewer changes this

document's status from DRAFT to APPROVED.

