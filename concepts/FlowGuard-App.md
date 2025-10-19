<!--
This Source Code Form is subject to the terms of the Mozilla Public License, v. 2.0.
If a copy of the MPL was not distributed with this file, you can obtain one at:
https://mozilla.org/MPL/2.0/.
-->
# FlowGuard-App  
**Modular Trust and Security for FlowScripts and Suites**

---

## Purpose

**FlowGuard-App** is the integrated trust enforcement, validation, and security monitoring layer within the FlowDirector.  
It governs FlowScripts and Blocks to ensure execution integrity and prevent malicious behavior across modular systems.  

This subsystem now includes optional support for **Suite-level enforcement**, allowing security policies and anomaly detection to be applied to entire **FlowSuites** in addition to individual scripts.

---

## Core Functions

### FlowScript Trust Validation
- Verifies signatures, authorship, and origin of every FlowScript before execution.  
- Uses a policy engine to determine execution eligibility (e.g., allow, warn, quarantine).  
- Works in conjunction with the FlowLog-App for detailed reporting.  

---

### Runtime Behavior Monitoring
- Observes memory use, CPU cycles, external calls, and ActionBlock usage.  
- Detects suspicious actions (e.g., unexpected outbound data, memory tampering).  
- Can halt execution, raise alerts, or re-route the script to a secure context.  

---

### Block-Level Isolation and Guardrails
- Enforces ActionTags related to trust boundaries (e.g., `untrusted`, `encrypted-only`).  
- Coordinates with CommBlocks to block data exfiltration or unauthorized network calls.  

---

### Suite-Level Security with SuiteGuard Logic
Provides an optional overlay to monitor FlowSuites as a cohesive unit:

- Validates all member scripts listed in a SuiteScript manifest.  
- Detects privilege mismatches, execution anomalies, and unexpected member additions.  
- Can define behavioral baselines and flag deviations across the suite.  
- May throttle, quarantine, or rollback the entire suite if violations occur.  
- Works with FlowLog-App to correlate execution steps and generate unified logs.  

---

### Quarantine and Trust Feedback Loop
- FlowScripts, Blocks, or entire FlowSuites can be flagged for review.  
- Quarantine history is stored locally and optionally published (depending on trust tier).  
- Supports local override or escalation based on user or system role.  

---

### Flexible Enforcement Modes

FlowGuard-App can be configured with multiple enforcement levels:

| Mode | Behavior |
|------|-----------|
| **Strict** | Block on first violation. |
| **Adaptive** | Allow once, then quarantine if repeated. |
| **Passive** | Log only for debugging or training systems. |

SuiteGuard logic can inherit or override these policies at the suite level.

---

## Integration Points

- Works with **FlowDirector** to intercept and authorize all script executions.  
- Syncs with **FlowLog-App** for full audit trails.  
- Informs **ActionSystem** and **CommSystem** when trust thresholds are breached.  
- May use external or internal threat intelligence sources to evaluate trust.  

---

## Summary

**FlowGuard-App** is essential to Flowgramming’s modular trust model, allowing **security and observability** to be embedded at every level — from atomic Actions to entire Suites of distributed logic.
