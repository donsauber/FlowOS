<!--
This Source Code Form is subject to the terms of the Mozilla Public License, v. 2.0.
If a copy of the MPL was not distributed with this file, you can obtain one at:
https://mozilla.org/MPL/2.0/.
-->
# Core Action Tags for FlowScripts

Each **Action Tag** modifies *how* the ActionBlock is executed, without changing *what* it does.  
Tags can be used alone or in combination.

---

## 1. `encrypted`
Run the Action inside a secure, encrypted memory space.

- Input and output data must be encrypted at rest and in transit.  
- Only trusted Actions that support secure execution will be accepted.  

---

## 2. `untrusted`
Use an ActionBlock even if it has a low trust score or unknown source.

- Automatically sandboxed more aggressively.  
- Logs are flagged for additional FlowGuard review.  

---

## 3. `low_memory`
Prioritize memory conservation over speed or parallelism.

- The ActionBlock must limit internal memory usage and avoid caching.  
- Useful for running on lightweight devices or embedded systems.  

---

## 4. `low_cpu`
Minimize processor use even if execution time increases.

- Useful for background or batch jobs under load constraints.  

---

## 5. `realtime`
Action must respond within a strict time window.

- The system may choose a faster but less accurate implementation.  
- Logs timing for diagnostic and performance review.
