# Bedrock 5 – Frequently Asked Questions (FAQ)

Welcome to the FAQ for Bedrock 5 – the next-generation open-source TI library for IBM Planning Analytics (TM1) v12+, PA3, and Containerized deployments.
> Note: Bedrock 5 is under active development and will be officially released on September 30. See the upcoming webinar

## General

### ❓ What is Bedrock?

Bedrock is a community-driven framework for IBM Planning Analytics (TM1) that provides:
- Reusable, modular TurboIntegrator (TI) processes
- Best practice implementations
- Documentation and training resources

It aims to speed up model development, improve maintainability, and standardize development across teams.

### ❓ What versions of TM1 are supported?
Bedrock 5 supports:
- TM1 Containerized
- TM1 v12+
- Planning Analytics 3 (PA3)

Not supported: 
- TM1 v11
- PA 2.0.x

Use Bedrock 4

### ❓ What’s new in Bedrock 5?

- Full support for changes in TM1 v12+ and PA3
- Deprecated and modified processes to align with new TM1 APIs
- Removal of unsupported features (e.g., ExecuteCommand, .rux file access)
- Clean install via the bedrock.json file using the File Manager and TI

See: What’s New in Bedrock 5

### ❓ Is Bedrock 5 backward-compatible?

No. Bedrock 5 is not backward-compatible with TM1 v11 or earlier versions of Planning Analytics. For those environments, continue using Bedrock 4.

### ❓ Is Bedrock 5 production-ready?

Not yet. It’s under active development. The final release is scheduled for September 30, 2025. Avoid using it in production until then.

## Installation & Upgrade
### ❓ How do I install Bedrock 5?

Full Installation Guide
### ❓ What if I’ve already modified Bedrock processes?

Installing Bedrock 5 will overwrite them.

Use the Upgrade Guide to compare and preserve changes before installation.

### ❓ Where do I get my API key and Tenant ID?
See the Generate API Key Guide.
You’ll need:
- API key (via TM1 Portal > Manage API Keys)
- Tenant ID and Database name (from your environment URL)

### ❓ Can I selectively upgrade only a few processes?
Yes. Use the Upgrade Guide to:
- Compare old vs. new processes
- Filter out unchanged or custom ones
- Only apply selected updates

## Compatibility Changes
### ❓ Which Bedrock processes are deprecated in v12 and PA3?
Several processes using now-deprecated TM1 functions are removed, including:
- }bedrock.server.executecommand
- }bedrock.server.savedataall
- }bedrock.security.client.password.reset
See full list in the Deprecated Functions section.

### ❓ What changes were made to modified processes?

All modified processes maintain their functional intent but use new supported functions:
- `.rux` file access → replaced with `CubeRuleGet`
- `ExecuteCommand` → replaced with `ASCIIDelete` where applicable
- `AssignClientPassword`, `CubeSetLogChanges`, and references to deprecated control cubes have been removed
See full list in the Modified Functions section.

## Documentation & Resources
### ❓ Where can I find documentation for each process?
Check the Bedrock Wiki.

Each process includes:
- Purpose
- Parameters
- Dependencies

### ❓ Are there white papers or best practices?
Yes! Here are a few key ones:
- Modular TI Design
- TI Best Practices
- Cube Design
- Rules Best Practices

## Contributions & Licensing
### ❓ Can I contribute to Bedrock 5?
Yes! Fork the repo, make your changes, and create a pull request.

Start here: How to contribute

### ❓ What’s the license?
You’re free to:
- Copy
- Modify
- Use
- Distribute

❗ But you must not publish the code elsewhere (e.g., on websites or services) without express permission. You must also credit the original authors.

### ❓ Are there any warranties?
No. Bedrock is provided as-is, with no warranty or liability.

## Useful Links
- GitHub Repository
- Bedrock Wiki
- What's New
- Bedrock Homepage
- Compare Bedrock 4 to Bedrock 5


<h1></h1>

Have more questions? Feel free to open an issue.
