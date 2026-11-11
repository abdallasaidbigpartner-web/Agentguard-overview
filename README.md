AgentGuard

Policy-as-Code & Tamper-Evident Audit Logging for AI Coding Agents

«Project status: Pre-alpha. AgentGuard is an actively developing project. Its current capabilities and limitations should be evaluated carefully; it is not presented as a complete or independently certified security boundary.»

Overview

AI coding agents can run shell commands, modify files, and interact with network resources. AgentGuard is being developed to help make those actions more controlled, explainable, and auditable.

The project provides a policy-based decision layer that evaluates proposed actions and records decisions in a tamper-evident audit log. Its goal is to make agent activity easier to govern and review without overstating what policy enforcement can guarantee.

Project Goals

- Evaluate agent actions against explicit security policies.
- Return clear "allow", "ask", or "deny" decisions.
- Explain policy decisions with human-readable reasons.
- Record decisions in an append-only, hash-chained audit log.
- Make audit-log integrity verifiable.
- Build a foundation for integrations with AI coding-agent workflows.

Current Documented Capabilities

The following capabilities are documented for the current pre-alpha stage:

Area| Documented capability
Policy evaluation| Allow, ask, and deny decisions with reasons
Matching| Glob-based matching for commands, paths, and hosts
Path handling| Path normalization before policy evaluation
Policy validation| Strict validation of policy definitions
CLI| "agentguard check" and "agentguard validate"
Audit integrity| "agentguard audit verify" verifies hash-chained audit logs
Decision recording| "check --audit-log" records decisions; audit-write failure is handled fail-closed

These statements describe the documented project scope and are not a substitute for independent security testing. Compatibility, platform behavior, and edge cases may change during pre-alpha development.

Development Roadmap

The roadmap is directional. Items below are planned work, not claims that the features are already implemented.

Planned stage| Focus
v0.2| Audit reports
v0.3| YAML policies, policy explanation, and policy linting
v0.4| Agent integrations, hook adapter, and standard-input workflows
v0.5| Fuzz testing, benchmarks, and coverage gates
v1.0| Policy language v2, migration support, and a stable release

Roadmap items may be refined as implementation and testing progress.

Technology

- TypeScript
- Node.js (current project requirement: Node.js 22.18 or newer)
- Strict TypeScript configuration
- Zero runtime dependencies (as currently specified by the project)

Security Approach and Limitations

AgentGuard is intended to add a policy and audit layer around AI coding-agent actions. It should be treated as one component of a broader security design, not as a replacement for operating-system permissions, sandboxing, network controls, code review, or secure development practices.

In particular:

- A policy decision is only as reliable as the policy, matching logic, and enforcement path around it.
- Audit logs improve traceability; they do not by themselves prevent malicious or unsafe actions.
- Hash chaining can help detect modification of recorded entries, but does not prove that every relevant action was captured or that the log is stored beyond an attacker's ability to replace it.
- Pre-alpha software may contain defects and should not be relied on as the sole security control for sensitive systems.

Project Status

AgentGuard is in pre-alpha development. The public showcase is intended to communicate the project's purpose, documented capabilities, security approach, and roadmap. Feature status should be updated only when implementation and verification support the change.

Contributing and Collaboration

This repository is a documentation-only public project overview. It does not contain the private implementation source code.

For questions about the project direction or potential collaboration, use the contact information on the repository owner's GitHub profile.

Intellectual Property

Unless a separate license is added, no permission is granted to copy, modify, distribute, or use this project's documentation or associated materials beyond what applicable law permits. The private implementation is maintained separately.

---

Last documentation review: 11 November 2026.
