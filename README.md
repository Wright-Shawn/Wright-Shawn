 <p align="center">
  <img src="https://raw.githubusercontent.com/Wright-Shawn/Wright-Shawn/main/figures/waveframe-logo-banner-mark.png" width="100%" />
</p>

# Shawn C. Wright

Building systems that decide whether AI-generated actions are allowed to execute.

---

## What I’m Working On

AI systems can propose actions.

But what actually stops a bad one from executing?

Most systems:
- detect issues
- log them
- audit after the fact

I focus on something else:

**stopping invalid actions before they execute.**

---

## Start Here

### Governed Mutation Demo (Finance)

A working end-to-end pipeline that:

- takes a proposed action  
- evaluates it against governance rules  
- decides:  
  - ✅ COMMIT ALLOWED  
  - ❌ COMMIT BLOCKED  

🔗 https://github.com/Waveframe-Labs/governed-finance-mutation-demo

---

## How It Works

Policy  
↓
Contract Compiler  
↓
Proposal  
↓
Normalizer    
↓
CRI-COR    
↓
COMMIT ALLOWED / BLOCKED    

---

## Core System

### CRI-CORE
Deterministic enforcement engine that decides whether a system state change is allowed to commit.  
🔗 https://github.com/Waveframe-Labs/CRI-CORE

### Contract Compiler
Turns governance rules into executable contracts.  
🔗 https://github.com/Waveframe-Labs/cricore-contract-compiler

### Proposal Normalizer
Converts actions into a standard structure for enforcement.  
🔗 https://github.com/Waveframe-Labs/proposal-normalizer

---

## Context

This work is developed under **Waveframe Labs**, where I’m building infrastructure for governed, auditable AI systems.

The focus is the **execution boundary**:
the moment a system attempts to act.

---

## Contact

📧 swright@waveframelabs.org  
🌐 https://waveframelabs.org  
🧭 https://orcid.org/0009-0006-6043-9295  

---

<div align="center">
  <sub>© 2026 Waveframe Labs</sub>
</div>
