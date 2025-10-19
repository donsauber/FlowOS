<!--
This Source Code Form is subject to the terms of the Mozilla Public License, v. 2.0.
If a copy of the MPL was not distributed with this file, you can obtain one at:
https://mozilla.org/MPL/2.0/.
-->
# **Flowgramming Philosophy**

**Programming that reads like a sentence.**

---

## **Why Flowgramming?**

Traditional programming is powerful, but difficult for most people to learn. It often requires:

* Learning abstract syntax and formatting rules

* Memorizing library functions and language quirks

* Managing memory, error handling, and runtime behavior manually

**Flowgramming** reimagines code as something readable, modular, and flow-based—built around concepts people already understand: **sentences, actions, and roles.**

---

## **Programming as a Sentence**

At its core, a FlowScript describes **what to do**, **how to do it**, and **in what order**. Each line of logic becomes as readable as a sentence:

“Take the input, sort it using low memory, translate the results, and log the output.”

This translates directly to Flowgramming logic:

* **DataBlocks** \= Nouns  
   Represent the data being passed, used, or transformed

* **Actions** \= Verbs  
   Represent the goals or tasks (e.g., “sort list”, “send email”)

* **ActionBlocks** \= Code modules that perform the actions  
   Handled automatically by the system; you don’t need to write them

* **Action Tags** \= Adverbs  
   Modify *how* the action is performed (e.g., `encrypted`, `strict_mode`, `low_memory`)

* **FlowScripts** \= The sentence structure  
   They organize the flow, define intent, and control logic execution

---

## **A Simple Example**

`action:`  
  `intent: "sort_list"`  
  `input: "DataBlock: numbers.raw"`  
  `output: "DataBlock: numbers.sorted"`  
  `tags: [low_memory, auditable]`

This FlowScript sentence means:

“Sort the list in `numbers.raw`, use low memory, log every step, and save to `numbers.sorted`.”

You don’t have to choose which algorithm or library to use. The system will:

* Pick the best `ActionBlock` for sorting

* Enforce `low_memory` and `auditable` execution

* Handle errors and fallback logic if needed

* Annotate the script with results

---

## **How It Helps Beginners**

* **No syntax errors**: You’re describing intent, not writing code

* **No searching for libraries**: The system picks the best ActionBlock

* **No memory management**: Blocks scale internally and are sandboxed

* **No hidden behavior**: All steps are logged and explainable

* **No compiling**: FlowScripts are directly runnable workflows

* **No API clutter**: The CommSystem handles all communication logic

---

## **How It Helps Experts**

* **Fine-grained control**: Use `strict_mode`, specific block IDs, and tag constraints

* **Rapid prototyping**: Change the logic by changing just one line

* **Reusable logic**: All Actions and Blocks are modular and callable anywhere

* **Observable pipelines**: FlowLog tracks performance and errors across systems

* **Expandable libraries**: Add or convert new logic using ActionBlocks and the ActionSystem

---

## **A New Way to Think**

Flowgramming lets you focus on **what you want to happen**, not **how to make the computer do it**. You're no longer writing "programs" in the old sense—you're **authoring workflows** using:

* Clear sentences

* Standardized building blocks

* Dynamic execution

* Auditable, collaborative evolution
