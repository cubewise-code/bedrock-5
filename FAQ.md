# 📖 Bedrock 5 FAQ

Welcome to the **Bedrock 5 Frequently Asked Questions (FAQ)**.  
This document provides quick answers to common questions about Bedrock 5, its compatibility, installation, and usage.

---

## ❓ What is Bedrock?

Bedrock is a **community-driven IBM Planning Analytics best practice framework**.  
It provides modular, reusable TurboIntegrator (TI) processes, tools, documentation, and training resources designed to:

- Accelerate model development
- Increase maintainability
- Improve auditability
- Reduce administration and support overhead

Bedrock has been widely adopted in **enterprise-level IBM Planning Analytics environments**.

---

## ❓ What is new in Bedrock 5?

Bedrock 5 has been **refactored and optimized** for compatibility with **IBM Planning Analytics TM1 Database 12.4+**.  
Key updates include:

- ✅ **Compatibility fixes** for new IBM Planning Analytics behaviors.
- 🚫 **Deprecated Functions** removed due to IBM Planning Analytics TM1 Database v12 changes.
- 🔄 **Modified processes** updated to maintain functionality under new syntax and rules.
- 📘 **Updated installation guide** for smooth deployment.

> ⚠️ Note: Bedrock 5 supports **only IBM Planning Analytics TM1 Database 12.4+**. For TM1 11.x or IBM Planning Analytics 2.0.x, use [Bedrock 4](https://github.com/cubewise-code/bedrock).

---

## ❓ When will Bedrock 5 be officially released?

Bedrock 5 is currently under development and will be **released on September 30th**.  
👉 [Click here to join the upcoming release webinar](https://events.teams.microsoft.com/event/f7564ab5-78aa-4c30-a93f-b880451f2de2@0635d657-0279-4110-9c8f-2ee27b1e065b).

---

## ❓ Which TM1 versions are supported?

- **Supported:** IBM Planning Analytics TM1 Database **12.4+**
- **Not supported:** TM1 11.x (use [Bedrock 4](https://github.com/cubewise-code/bedrock))

---

## ❓ What version of Arc supports Bedrock 5?
Arc 5.1+ has direct integration for Bedrock 5, meaning you can install it directly from Arc!  You can find out more information [here](https://code.cubewise.com/software/products/arc/).

---

## ❓ Why should I use Bedrock?

Using Bedrock ensures **standardization and scalability** in IBM Planning Analytics projects:

- Reusable, modular TI codebase.
- Faster development cycles.
- Reduced learning curve for new developers.
- Transparent, auditable processes.
- Improved scalability for large datasets and concurrent users.

---

## ❓ Where can I find more information?

- 🌐 Official site: [code.cubewise.com/bedrock](https://code.cubewise.com/bedrock)
- 📘 [Bedrock Wiki](https://github.com/cubewise-code/bedrock-5/wiki) with full process documentation
- 🆕 [What’s New in Bedrock 5](https://github.com/cubewise-code/bedrock-5/wiki#whats-new-in-bedrock-5)
- 📑 White Papers:
  - [Bedrock Modular Approach](https://downloads.cubewise.com/Bedrock/whitepapers/White_Paper_Modular_Approach.pdf)
  - [Best Practice Turbo Integrator](https://downloads.cubewise.com/Bedrock/whitepapers/White_Paper_Best_Practice_Turbo_Integrator.pdf)
  - [Best Practice Cube Design](https://downloads.cubewise.com/Bedrock/whitepapers/White_Paper_Best_Practice_Cube_Design.pdf)
  - [Best Practice Rules](https://downloads.cubewise.com/Bedrock/whitepapers/White_Paper_Best_Practice_Rules.pdf)

---

## ❓ What functions have been deprecated in Bedrock 5?

Some Bedrock processes are no longer supported due to IBM Planning Anayltics TM1 Database 12 deprecations.  
Examples include:

- `}bedrock.cube.data.save` → `CubeSaveData` deprecated
- `}bedrock.dim.attr.swapalias` → `SwapAliasWithPrincipalName` deprecated
- `}bedrock.server.savedataall` → `SaveDataAll` deprecated

👉 [Full list of deprecated functions here](#deprecated-functions).

---

## ❓ What processes were modified?

Many functions were updated for compatibility while preserving functionality.  
For example:

- `}bedrock.cube.clone` → Uses `CubeRuleGet` instead of reading `.rux` files
- `}bedrock.cube.data.copy` → Uses `ASCIIDelete` instead of `ExecuteCommand`
- `}bedrock.security.client.create` → Passwords can no longer be set due to `AssignClientPassword` deprecation  
  👉 [Full list of Modified Processes here](RELEASE_NOTES.md#modified-processes).  
  👉 [Compare changes from Bedrock 4 → 5](https://github.com/bdunleavy22/bedrock-compare/pull/2/files).

---

## ❓ How is Bedrock licensed?

Bedrock is **free and open-source**:

- ✅ You may copy, modify, use, compile, sell, or distribute the code for **any purpose** (commercial or non-commercial).
- ❌ You may not publish the information on external websites, online services, or print media without permission.
- ℹ️ Credit to the original authors must always remain intact.

---

## ❓ Are there warranties?

No.  
All code, documents, and information in Bedrock are provided **without warranty**.

---

## ❓ How can I contribute?

- 🔗 Source code: [github.com/cubewise-code/bedrock-5](https://github.com/cubewise-code/bedrock-5)
- 🛠️ To contribute:
  1. [Fork the repo](https://help.github.com/articles/fork-a-repo/)
  2. Make your changes
  3. Submit a [pull request](https://help.github.com/articles/about-pull-requests/)

---

## ❓ Where can I see deprecated and modified processes?

See the dedicated sections below:

- [Deprecated Functions](RELEASE_NOTES.md#deprecated-functions)
- [Modified Processes](RELEASE_NOTES.md#modified-processes)

---

# 📉 Deprecated Functions

| Bedrock Process                             | TM1 Deprecated Function      |
| ------------------------------------------- | ---------------------------- |
| `}bedrock.cube.data.save`                   | `CubeSaveData`               |
| `}bedrock.dim.attr.swapalias`               | `SwapAliasWithPrincipalName` |
| `}bedrock.hier.create.fromrollup.aliasswap` | `SwapAliasWithPrincipalName` |
| `}bedrock.security.client.password.reset`   | `AssignClientPassword`       |
| `}bedrock.server.dir.backup`                | `ExecuteCommand`             |
| `}bedrock.server.dir.listcontents`          | `ExecuteCommand`             |
| `}bedrock.server.encrypt.directory`         | `ExecuteCommand`             |
| `}bedrock.server.encrypt.file`              | `ExecuteCommand`             |
| `}bedrock.server.executecommand`            | `ExecuteCommand`             |
| `}bedrock.server.logfile.delete`            | `ExecuteCommand`             |
| `}bedrock.server.savedataall`               | `SaveDataAll`                |

---

# 🔄 Modified Processes

Due to deprecations in IBM Planning Analytics TM1 Database 12, the following Bedrock processes were modified (functionality unchanged):

- Removal of `CubeSetLogChanges`
- Replacing `.rux` file reads with `CubeRuleGet`
- Replacement of `ExecuteCommand` (for file deletion) with `ASCIIDelete`
- Removal of references to deprecated cubes such as `}DimensionProperties` and `}ApplicationSecurity`
- Removal of `AssignClientPassword` support

👉 See the full [list of modified processes here](RELEASE_NOTES.md#modified-processes).

---

## ✅ Summary

- Bedrock 5 supports **IBM Planning Analytics TM1 Database 12.4+ only**
- Bedrock 4 remains the option for older TM1 versions
- Deprecations and modifications align Bedrock with the **latest TM1 standards**
- Fully open-source, community-driven, and available on GitHub

---
