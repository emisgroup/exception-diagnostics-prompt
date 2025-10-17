# Exception Diagnostics Prompt (BERTHA)

This repository hosts the BERTHA prompt: a structured, evidence-driven workflow for analysing and remediating exceptions and defects in .NET Framework / C# Windows applications (WinForms, WPF, Windows Service, WCF, Console) using VS Code + GitHub Copilot Chat.

## Overview
The prompt defines:
- Activation protocol (explicit “Analyse Problem:” with a JSON case file)
- Workspace bootstrap inventory (solutions, projects, configs, symbol map)
- Multi-phase analysis (Recon → Pattern Reference → Root Cause → Fix Design → Validation → Release)
- Strict output contract suitable for pull request inclusion
- Quality & governance rules ensuring minimal, auditable, and safe changes
- Fallback instrumentation path when the issue cannot be reproduced directly

## Usage
1. Add the prompt file (BERTHA.md) to your workspace.
2. Prepare a JSON problem descriptor (e.g. `problem.json`) containing exception details, reproduction info, and metadata.
3. In Copilot Chat, trigger analysis by sending:
   Analyse Problem:
   (attach or reference the JSON file)
4. Review the structured output sections; apply or adapt the proposed patch and tests.

## JSON Case File (Suggested Fields)
- number, short_description
- u_steps_to_reproduce, u_able_to_reproduce
- exception stack traces
- u_root_cause_detail (if suspected), u_impact_to_practice
- u_workaround (if any)

## Output Sections Produced
1) Problem Digest  
2) Trace-to-Code Map  
3) Root Cause Analysis  
4) Fix Plan  
5) Proposed Patch (Unified Diff)  
6) Test Changes  
7) Manual Validation Guide  
8) Observability & Ops  
9) Release Notes & Backport  
10) PR Package (commit message, title, description)  
Fallback: Hypothesis & Instrumentation Plan (if non-repro)

## Principles
- Evidence-based (every claim cites file:line)
- Minimal surface fix
- Additive & backward compatible where possible
- Strong observability (structured logs, metrics, optional tracing)
- Avoid large refactors or speculative changes

## Topics
dotnet, diagnostics, exceptions, root-cause-analysis, prompt-engineering, observability, remediation, winforms, wpf, wcf

## Contributing
Feel free to open issues suggesting:
- Additional RCA categories
- Expanded observability templates
- Improved test scaffolding examples

## License
(Replace this section after selecting a license.)

## Status
Version v1 of the prompt.
