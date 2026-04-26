# Harness Resilience

**Harness Resilience** is a position paper and practice framework for improving the reliability of agentic AI engineering workflows. It argues that in modern AI-assisted software development, the practical dependency is no longer only the large language model (LLM), but the full **model–harness combination**: prompts, tools, sandboxes, connectors, memory, execution policies, permissions, and user interfaces.

The paper focuses on how engineering teams can continue safe and effective work when a preferred AI coding agent or agent harness changes behavior, loses access, degrades, becomes rate-limited, or is no longer available.

## Paper

**Title:** Harness Resilience: From LLM Availability to Toolchain Continuity in Agentic AI Engineering  
**Author:** John Cheung  
**Affiliation:** College of Professional and Continuing Education

This repository contains the LaTeX source and PDF version of the paper.

## Motivation

Agentic AI tools such as Codex, Claude Code, Gemini CLI, Cursor-like development environments, MCP-based agents, and general-purpose agents have become part of software engineering workflows. These systems are not just chat interfaces. They package context, call tools, edit files, run commands, manage permissions, and shape how engineers work.

As a result, AI resilience must extend beyond model availability and benchmark performance. A strong model can still become unreliable in practice if the surrounding harness changes, fails, or becomes unavailable.

This paper introduces **harness resilience** as the ability of a team to maintain acceptable engineering productivity, safety, and governance when an AI harness fails, changes, or disappears.

## Key Ideas

The paper proposes that AI engineering teams should treat agent harnesses as first-class operational dependencies. It covers:

- A reference architecture for separating model, harness, application, and governance layers
- Boundary criteria for identifying what belongs to the harness layer
- A taxonomy of common harness failure modes
- A connector-centric threat model for MCP-style and tool-using agents
- Practical KPIs for measuring harness resilience
- A maturity model from ad hoc usage to antifragile harness operations
- Operational practices such as harness-agnostic context packages, runbooks, golden-task regression tests, permission controls, provenance capture, and fallback planning
- Enterprise procurement and governance considerations

## What Is an AI Harness?

In this paper, a **harness** is the operational layer around a model that enables it to act. It may include:

- System prompts and instruction files
- Repository context and project memory
- Tool schemas and connector definitions
- Shell execution and sandboxing
- Approval gates and permission policies
- MCP servers and external integrations
- Context compression and retrieval modules
- Logging, tracing, provenance, and rollback mechanisms
- CLI, IDE, browser, or cloud workspace interfaces

The harness turns model output into action. Therefore, failure at the harness layer can disrupt software delivery even when the model itself remains available.

## Proposed Resilience Dimensions

The framework defines five major dimensions of harness resilience:

1. **Functional resilience** — the team can still complete key engineering tasks.
2. **Context resilience** — project knowledge remains portable across harnesses.
3. **Tool resilience** — tool integrations can be replaced or wrapped with minimal disruption.
4. **Governance resilience** — auditability, security, privacy, and compliance continue across tools.
5. **Human resilience** — engineers retain the knowledge and procedures needed to recover manually.

## Example KPIs

The paper proposes measurable indicators such as:

- **Time-to-Fallback (TTF):** time required to move from a failed harness to a usable fallback path.
- **Mean Time to Harness Recovery (MTTHR):** average time to restore normal harness operation.
- **Context Exportability Score (CES):** proportion of required project context that can be transferred to another harness.
- **Connector Replacement Ratio (CRR):** proportion of tool integrations that can be replaced through documented wrappers or standards.
- **Provenance Coverage (PCov):** proportion of agent actions with complete audit traces.
- **Permission Surface Area (PSA):** weighted measure of the privileges exposed to the agent harness.

## Recommended Practices

Engineering teams can improve harness resilience by:

- Maintaining a vendor-neutral `AGENTS.md` or equivalent project context file
- Separating model, harness, tool, execution, memory, and governance layers
- Creating an agent runbook for fallback and incident handling
- Maintaining a small golden-task suite for agent regression testing
- Using failure-injection exercises to test harness continuity
- Capturing provenance for file edits, tool calls, approvals, and generated changes
- Restricting tool permissions using least privilege and sandboxing
- Keeping a local or open-source fallback workflow
- Including harness continuity in procurement and enterprise risk planning

## Suggested Repository Structure

```text
.
├── README.md
├── paper.tex
├── paper.pdf
├── templates/
│   ├── AGENTS.md
│   ├── harness-runbook.md
│   └── fallback-checklist.md
├── examples/
│   ├── golden-tasks/
│   └── failure-injection/
└── metrics/
    └── kpi-definitions.md
```

## Potential Use Cases

This work may be useful for:

- AI engineering teams adopting coding agents
- DevOps and platform teams managing AI-assisted SDLC workflows
- Enterprise architects evaluating agentic AI tools
- Security teams assessing MCP/tool-execution risks
- Researchers studying agent reliability, provenance, and governance
- Procurement teams comparing AI coding platforms

## Status

This is a position paper and conceptual framework. Future work may include:

- A public benchmark of cross-harness golden tasks
- Failure-injection scripts for agentic coding workflows
- KPI calculators for context portability and provenance coverage
- Templates for AGENTS.md, runbooks, and fallback planning
- Case studies measuring harness recovery and continuity outcomes

## Citation

If you use or discuss this work, please cite:

```bibtex
@article{cheung2026harnessresilience,
  title   = {Harness Resilience: From LLM Availability to Toolchain Continuity in Agentic AI Engineering},
  author  = {Cheung, John},
  year    = {2026},
  note    = {Position paper}
}
```

## License

Add your preferred license here, for example:

- `CC BY 4.0` for the paper text
- `MIT License` for templates and scripts

## Contact

For questions, suggestions, or collaboration, please open an issue or submit a pull request.
