<p align="center">
  <img src="../master-banner.png" alt="Waveframe Labs Banner" width="600">
</p>

# Waveframe Labs

Building deterministic execution-governance infrastructure for AI and automated systems.

Waveframe Labs develops systems that decide whether a proposed action is allowed to execute before it reaches production systems.

Most governance systems:
- monitor behavior
- generate warnings
- or audit after execution

Waveframe focuses on something else:

> deterministic admissibility at the execution boundary

---

# Canonical Execution Flow

```text
Governance Source
        ↓
Governance-Ledger
        ↓
Contract Compiler
        ↓
Compiled Authority Contract
        ↓
Proposal Normalizer
        ↓
Canonical Proposal
        ↓
CRI-CORE
        ↓
COMMIT ALLOWED / BLOCKED
        ↓
Waveframe Guard
        ↓
Production System
````

Waveframe Cloud provides:

* authority distribution
* registry infrastructure
* durable audit ingestion
* and receipt verification

---

# Start Here

### Install the developer-facing enforcement layer

```bash
pip install waveframe-guard
```

Waveframe Guard wraps runtime execution and enforces governance locally before actions execute.

---

# Minimal Runtime Example

```python
from pathlib import Path

from waveframe_guard import install_guard, guard

install_guard(
    actor={"id": "user-1", "type": "human", "role": "intern"},
    contract_path=Path("contracts") / "finance-policy-1.0.0.contract.json"
)

@guard
def transfer(amount):
    print(f"Transferred ${amount}")

transfer(100)
```

```text
Execution blocked: required role not satisfied: manager
```

---

# Core Infrastructure Layers

## Governance Layer

### Governance-Ledger

Turns governed source text into deterministic, reviewable governance authority.

Provides:

* governance normalization
* semantic diagnostics
* publication gating
* lineage verification
* deterministic publication artifacts

---

## Compilation Layer

### CRI-CORE Contract Compiler

Compiles governance policy into deterministic compiled contract artifacts.

```bash
pip install cricore-contract-compiler
```

Compiled contracts define:

* authority requirements
* approvals
* invariants
* artifact requirements
* execution constraints

---

## Proposal Layer

### Proposal Normalizer

Builds canonical CRI-CORE proposal objects from:

* actor identity
* mutation requests
* contract references
* governance artifacts

```bash
pip install cricore-proposal-normalizer
```

---

## Enforcement Layer

### CRI-CORE

Deterministic execution-boundary enforcement kernel.

```bash
pip install cricore
```

CRI-CORE evaluates:

* compiled contracts
* canonical proposals
* runtime context

and returns:

```python
commit_allowed = True | False
```

If `False`, the action must not execute.

CRI-CORE does not:

* generate actions
* orchestrate workflows
* persist logs
* interpret governance meaning

It only determines:

> whether a proposed action is admissible at execution time.

---

## Runtime Layer

### Waveframe Guard

Developer-facing runtime enforcement SDK.

Guard:

* loads published contracts
* wraps execution
* evaluates admissibility
* blocks invalid actions locally
* continues enforcement during Cloud outages

```bash
pip install waveframe-guard
```

---

## Authority & Audit Layer

### Waveframe Cloud

Authority distribution and durable evidence infrastructure.

Cloud provides:

* contract registry distribution
* immutable authority artifacts
* audit ingestion
* durable receipts
* organizational authority coordination

Cloud does not:

* evaluate admissibility
* execute actions
* normalize governance

---

# Example Scenario

## Financial Governance

An AI proposes reallocating $2M between cost centers.

Without enforcement:
→ execution proceeds immediately

With Waveframe:
→ proposal evaluated against authority contract
→ missing approval detected
→ COMMIT BLOCKED

The action never executes.

---

# Local vs Cloud

| Layer       | Responsibility                                     |
| ----------- | -------------------------------------------------- |
| Local Guard | Fast local enforcement                             |
| Cloud       | Registry, audit durability, authority distribution |

Local enforcement remains operational even if Cloud is unavailable.

---

# Core Repositories

| Repository          | Purpose                                             |
| ------------------- | --------------------------------------------------- |
| CRI-CORE            | Deterministic enforcement kernel                    |
| Waveframe Guard     | Runtime execution enforcement SDK                   |
| Governance-Ledger   | Governance compilation + publication infrastructure |
| Contract Compiler   | Compiles governance into contracts                  |
| Proposal Normalizer | Canonical proposal assembly                         |
| Waveframe Cloud     | Authority distribution + audit durability           |
| Stamp               | Artifact and metadata validation                    |

---

# Compatibility

Version compatibility and dependency requirements are documented at:

[https://waveframelabs.org/compatibility.html](https://waveframelabs.org/compatibility.html)

---

# Demonstrations

Repositories in this organization demonstrate:

* governed financial mutations
* execution-boundary enforcement
* role separation enforcement
* approval threshold enforcement
* admissibility replay
* runtime governance blocking

Each demo answers one question:

> does the proposed action execute or not?

---

# Licensing

| Category             | License         |
| -------------------- | --------------- |
| Tooling & Code       | Apache 2.0      |
| Documentation        | CC BY-NC-SA 4.0 |
| Governance & Methods | CC BY 4.0       |

---

# Links

Website — [https://waveframelabs.org](https://waveframelabs.org)
ORCID — [https://orcid.org/0009-0006-6043-9295](https://orcid.org/0009-0006-6043-9295)
Contact — [swright@waveframelabs.org](mailto:swright@waveframelabs.org)

---

<div align="center">
  <sub>© 2026 Waveframe Labs — Independent Open-Science Research Entity</sub>
</div>
