<!--
This Source Code Form is subject to the terms of the Mozilla Public License, v. 2.0.
If a copy of the MPL was not distributed with this file, you can obtain one at:
https://mozilla.org/MPL/2.0/.
-->
# DataBlocks & DataSystem  
**Unified Data Handling in Flowgramming**

---

## Purpose

**DataBlocks** are the foundational unit for data storage, flow, and transformation in Flowgramming.  
They represent any data structure—from a single config file to a live multi-version dataset—while maintaining trust, traceability, and flexibility.

To ensure this, every DataBlock is governed by the **DataSystem**, a runtime partner that enforces integrity, trust, permissions, and lifecycle management.

---

## What Are DataBlocks?

A **DataBlock** is any unit of data wrapped with a Flow-compatible logic and metadata layer.  
It can be:

- A JSON file  
- An encrypted blob  
- A collaboration dataset  
- A raw sensor feed  
- A scientific model  
- Even a traditional file format like `.csv`, `.jpg`, or `.sqlite`  

DataBlocks are designed to:

- Handle versioning and lineage tracking  
- Contain embedded or referenced permissions  
- Allow annotations, logs, and warnings  
- Be processed and routed by FlowScripts across blocks  

---

## DataBlock Traits

| Feature | Description |
|----------|-------------|
| **File-Agnostic** | Can wrap any existing file format |
| **Permission-Scoped** | Can declare program/user-level access per version |
| **Versioned** | Supports multi-versioned workflows, snapshots, and immutables |
| **Trust-Aware** | Tracks data source reliability and behavior over time |
| **Commentable** | Allows internal or external annotation/logging |
| **Processable** | Can be parsed or transformed by LibraryBlocks |
| **Auditable** | Every access or mutation is logged to FlowLog via DataSystem |

---

## DataBlock Types (by Behavior)

FlowOS does not hard-code these types but recognizes them as emergent patterns based on metadata flags and usage.

| Type | Use Case |
|------|-----------|
| **RawBlock** | Immutable snapshot or external data dump (e.g., downloaded satellite data) |
| **SharedBlock** | Read/write shared file for multiple FlowBlocks (e.g., shared state) |
| **CollabBlock** | Multi-version writable data with user annotations (e.g., scientific notes, training data) |
| **FlatBlock** | Simple, schema-light data (e.g., config file, basic JSON) |
| **EncryptedBlock** | Data wrapped in security; may be individually trusted or decrypted on access |

All types are managed the same way by FlowOS.  
Their behavior is guided by:

- Metadata flags  
- Permissions  
- Access patterns  
- Trust source  

---

## DataSystem: The Partner Service

The **DataSystem** is the paired runtime service that monitors, validates, and governs all DataBlocks.

### Primary Functions

| Category | What DataSystem Does |
|-----------|----------------------|
| **Validation** | Checks format, schema, integrity, trust, and lineage |
| **Permissions** | Enforces declared read/write/modify/delete access per actor or program |
| **Lifecycle** | Manages creation, versioning, mutation, expiration, and deletion |
| **Logging** | Emits FlowLog records for every read/write/annotation |
| **Trust Memory** | Tracks reliability of source, correctness, and mutation behavior |
| **Threat Detection** | Flags unexpected formats, content drift, or malicious patterns |
| **Storage Mapping** | Optimizes physical placement, load balancing, and caching rules |
| **Coordination** | Communicates with FlowOS, FlowGuard, and FlowScripts for process security |

---

## FlowScript Interaction

FlowScripts can:

- Declare the type of DataBlock needed  
- Reference an existing one (via ID, URI, or query)  
- Fork a DataBlock for isolated processing  
- Annotate results or mark a version for validation  
- Request quarantine or blocklisting of untrusted sources  

All DataBlock declarations trigger DataSystem mediation.

---

## Example DataBlock Declaration

```yaml
DataBlock:
  id: "user.prefs.json"
  type: "SharedBlock"
  encrypted: false
  version: "v2.1"
  permissions:
    read: ["lib.settings.parser"]
    write: ["lib.settings.writer"]
  trust_required: 80
  managed_by: "DataSystem"
