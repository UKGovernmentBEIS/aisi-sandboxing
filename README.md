# The Inspect Sandboxing Toolkit: Scalable and secure AI agent evaluations

How do we test AI systems for dangerous capabilities without risking real-world harm?

The more capable models become, the harder it is to safely evaluate them. When an agent can execute arbitrary code and interact with critical systems to gain sensitive information, running evaluations without adequate safeguards could put critical systems at risk.

Sandboxes are isolated environments for testing and monitoring AI behaviour. When we give a model access to use tools (such as for writing code), we execute that action in a sandbox to limit the model’s access to external systems and data. This lets us evaluate its capabilities without exposing sensitive resources.

## Inspect Plugins

Our toolkit includes three plugins to Inspect:

- [Docker Compose](https://inspect.aisi.org.uk/sandboxing.html): A tool for managing multi-container evaluation scenarios, allowing you to easily get started with agentic evaluations.
- [Kubernetes Plugin](https://k8s-sandbox.aisi.org.uk/): Allows you to simulate more complex environments, and automatically spin up or shut down containers based on resource demands.
- [Proxmox plugin](https://github.com/UKGovernmentBEIS/inspect_proxmox_sandbox): Strong virtual machine (VM) isolation for high-risk evaluations.

## Technical Documentation

Providing tools can be unhelpful without providing guidance on when to use them, particularly in a novel field like agentic evaluations. So, we also created an accompanying sandboxing protocol to help users understand the appropriate level of sandboxing for their evaluation and provide an end-to-end guide on how to set it up using our three tools.

Our sandboxing protocol classifies isolation along three different axes: tooling (restricts model access to certain tools, and/or the ability to execute code), host (prevents a model from escaping or compromising the host system), and network (controls a model’s interaction with external systems – including the internet – over the network).

In this repo, you will find a PDF containing documentation on how to approach choosing and setting up a sandbox that fits your eval.
