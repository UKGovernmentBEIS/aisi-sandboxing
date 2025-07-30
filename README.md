
**AISI Sandboxing Framework for Agentic AI Evaluations**

AISI's open-source sandboxing framework for secure agentic AI evaluations. This framework provides tools and guidance for more safely running evaluations where AI agents can execute code, make API calls, browse the web, and interact with complex systems - while minimizing risks to infrastructure and preventing unintended real-world consequences.

**Disclaimer**

This taxonomy represents AISI's internal approach to sandboxing for agentic evaluations and is shared as a community resource. It does not constitute official UK government guidance, nor does it guarantee complete protection against all risks. Users should conduct their own risk assessments and implement additional safeguards as appropriate.

**Quick Start / Overview**

AISI uses a three-dimensional taxonomy for sandboxing agentic evaluations:

**Dimension	Description	Levels**
Tooling (T)	Defines the agent's execution capabilities	T1-T4
Host Isolation (H)	Defines the containment level of the execution environment	H1-H4
Network Isolation (N)	Controls the agent's access to external networks	N1-N4
Sandbox profiles are expressed in the format TX.HX.NX (e.g., T2.H3.N3), where higher numbers indicate stronger isolation.

**For complete guidance on selecting appropriate sandbox levels, see the full taxonomy PDF.**

**Available Tools**

All tools are implemented as plugins for Inspect, our open-source evaluation framework:

Docker: Run evaluation tools within Docker containers <Configuration guide> 
Docker-compose: Manage multiple related containers locally for complex evaluation scenarios <Config guide>
Inspect Kubernetes sandbox provider: Run multiple containers on a K8s cluster for improved scalability and security <Config guide>
Inspect Proxmox sandbox provider: Use VMs within Proxmox for hardware-level virtualization, highest level of security <Configuration gudie)


For detailed setup instructions, refer to the documentation links <link to PDF>

**When to Use Which Tool**

We indicate below common use-cases and their ideal sandbox profiles:

| Evaluation Type | Description | Sandbox Profile | Explanation |
|-----------------|-------------|-----------------|-------------|
| Chem/Bio with PyPI | Write and execute Python code using PyPI libraries | N2.H1.T0 | Can install PyPI packages but no other internet; Kubernetes host sandboxing; can write and execute code |
| Cyber with Ghidra | Decompiling binaries using Ghidra tool | T1.H2.N1 | Ghidra runs in separate sandbox; can invoke CLI but not write/execute arbitrary code; no network access |
| Docker zero-day exploit | Finding vulnerabilities in Docker runtime | T0.H2.N2 | No internet required; model is actively hostile; needs to write and execute code |
| Deep research | Information retrieval using general computer tool | T1.H1.N0 or T0.H1.N0 | May need access to tools but won't write/execute code |

See the full taxonomy PDF for comprehensive guidance on profile selection.

**Documentation**

Full Sandboxing Taxonomy PDF - Complete 12-page guide with detailed protocols <link>

AISI Blog Post - 500-word overview of our sandboxing approach <link> 

Inspect Framework Documentation - Core evaluation framework documentation <link < 

**Contributing & Support**

Report issues or contribute: Please submit issues or pull requests to this repository 

Questions: Join the Inspect community on Slack <link>

If you discover security vulnerabilities, please report them responsibly to jason.gwartz@dsit.gov.uk 

