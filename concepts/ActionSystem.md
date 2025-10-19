<!--
This Source Code Form is subject to the terms of the Mozilla Public License, v. 2.0.
If a copy of the MPL was not distributed with this file, you can obtain one at:
https://mozilla.org/MPL/2.0/.
-->


# ActionSystem and ActionBlocks  
**Modular, Adaptive Logic Execution in Flowgramming**

---

## What Are ActionBlocks?

**ActionBlocks** are the modular units of computation in Flowgramming.  
They function as the **verbs** of the system—discrete, sandboxed logic modules that perform specific actions or tasks.

Each ActionBlock:

- Is fully self-contained and secure  
- Can be reused across any compatible FlowScript  
- May expand internally to handle increased workload  
- **Cannot spawn other Blocks**  
- Reports performance and status to the FlowLog and ActionSystem  
- Can be selected by intent or ID through a FlowScript  
- Declares which **Action Tags** it supports (e.g., `low_memory`, `encrypted`)

---

## What Is the ActionSystem?

The **ActionSystem** is the execution and management environment for all ActionBlocks.  
It is responsible for:

- Running and sandboxing ActionBlocks  
- Interpreting FlowScript instructions (intent or explicit)  
- Matching actions to the best available implementation  
- Handling failure, substitution, and fallback  
- Annotating FlowScripts with execution results and suggestions  
- Monitoring and updating a registry of available actions  
- Enforcing Action Tags to control execution behavior  
- Converting traditional code libraries into modular ActionBlocks  

---

## Key Responsibilities of ActionBlocks

- **Modularity:** Each ActionBlock contains one functional task  
- **Sandboxing:** Runs in an isolated environment with declared access  
- **Expansion:** Can scale its own threads or processes under load  
- **No Spawning:** Cannot create new Blocks or modify outside the sandbox  
- **Performance Logging:** Reports memory, CPU, duration, and outcome  
- **Declarative Tags:** Supports or rejects Action Tags requested by FlowScripts  

---

## Key Responsibilities of the ActionSystem

### Action Resolution
- **Intent-based matching:** Find best ActionBlock for `"sort list"`  
- **Explicit mode:** Run exact named block only  
- **Fallback Handling:** Automatically use backup ActionBlocks if one fails  
- **Annotation:** If problems occur, the FlowScript is annotated for review  

### Library Deconstruction
- Breaks down traditional libraries (e.g., Python, C) into modular ActionBlocks  
- Stores them by **function**, not by language  

### Performance Tracking
- Keeps trust scores, success rates, and efficiency stats  
- Flags unreliable blocks  

### Dynamic Selection
- Uses runtime context, data size, resource limits, and Flo
