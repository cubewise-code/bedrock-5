<h1 align="center">
  <br>
  <a href="https://github.com/cubewise-code/bedrock-5"><img width="9149" height="2224" alt="bedrock5_logogray" src="https://github.com/user-attachments/assets/bdb178a3-7463-4c0b-a74b-f2c1a5059532" />
</h1>

# Bedrock 5 is fully compatible with IBM Planning Analytics TM1 Database 12.4+

<p align="center">
  <a href="https://www.ibm.com/docs/en/planning-analytics/2.0.0?topic=12-welcome-tm1-database"><img src="https://img.shields.io/badge/TM1_Database-v12.4+-blue" alt="TM1 versions"></a>
  <a href="https://code.cubewise.com/open-source/bedrock/"><img src="https://img.shields.io/badge/Bedrock_5_Latest_Release-v5.0.0-green" alt="v5.0.0"></a>
</p>
<h1></h1>

### ⚠️ Bedrock 5 is still under development and will be released on the 30th of September, [click here for the upcoming webinar](https://events.teams.microsoft.com/event/f7564ab5-78aa-4c30-a93f-b880451f2de2@0635d657-0279-4110-9c8f-2ee27b1e065b). Please wait for the upcoming official release to use it in your projects. ⚠️ 

### This next-generation release of Bedrock has been refactored and rigorously tested to support IBM Planning Analytics TM1 Database 12.4+. Bedrock 5 does not support earlier versions of the TM1 Database (e.g. 11.x). These versions are supported by [Bedrock 4](https://github.com/cubewise-code/bedrock)

<b>Bedrock 5</b> is the latest evolution of the Bedrock library, specifically updated for compatibility with IBM Planning Analytics TM1 Database 12.4+. This release reflects the ongoing commitment to maintaining best practices for IBM Planning Analytics development, providing optimized, standardized, and scalable TurboIntegrator (TI) code assets that align with changes introduced in the IBM Planning Analytics TM1 Database 12.

In this article:
- [What is Bedrock?](#what-is-bedrock)
- [Deprecated Functions](#deprecated-functions)
- [Modified Functions](#modified-functions)
- [Installation Guide](https://github.com/cubewise-code/bedrock-5/wiki/Installation-Guide#installation-guide-for-ibm-planning-analytics-as-a-service-on-aws-or-azure-)

## What is Bedrock?
Bedrock is a community-driven IBM Planning Analytics best practice framework. It provides modular, reusable TI processes, tools, documentation, and training resources designed to:
- Accelerate model development
- Increase maintainability
- Improve auditability
- Reduce administration and support overhead

The Bedrock library is built on years of global IBM Planning Analytics implementation experience and is widely adopted in complex, enterprise-level IBM Planning Analytics environments.

## What's New in Bedrock 5?

Bedrock 5 brings targeted updates to support IBM Planning Analytics TM1 Database 12.4+, including:
- <b>Compatibility Fixes</b>: Adjustments for updated IBM Planning Analytics system behavior and function changes.
- <b>Deprecated Processes</b>: Clear documentation of processes no longer required or supported in the latest version of IBM Planning Analytics.
- <b>Modified Processes</b>: Existing processes updated to maintain their original functionality while aligning with new IBM Planning Analytics features and syntax.
- <b>Updated Installation Guide</b>: Step-by-step instructions for deploying Bedrock 5 into your IBM Planning Analytics environment.

Note: Bedrock 5 is intended only for the IBM Planning Analytics TM1 Database 12.4+. For TM1 11.x or IBM Planning Analytics 2.0.x, use [Bedrock 4](https://github.com/cubewise-code/bedrock)

## Why Bedrock?
With growing IBM Planning Analytics adoption, standardization is critical. Bedrock provides:
- A standardized TI codebase for reuse across models and teams.
- Faster development cycles through proven, modular processes.
- Lower learning curve for new developers.
- Reduced black-box risk through increased transparency and logging.
- Improved scalability to handle complex business models with large datasets and high concurrency.

## Where can I get more information?

The first place for further information is the [code.cubewise.com/bedrock](https://code.cubewise.com/bedrock) website. 

**Key resources**:
* Check out the [What's New](https://github.com/cubewise-code/bedrock-5/wiki#whats-new-in-bedrock-5) page to familiarize yourself with what is different versus the previous version. 
* [Bedrock Wiki](https://github.com/cubewise-code/bedrock-5/wiki). Each process has a full documentation of what it does, the intended purpose, needed parameters, and dependencies within the library.

**White Papers**:
* [Bedrock Modular Approach](https://downloads.cubewise.com/Bedrock/whitepapers/White_Paper_Modular_Approach.pdf)
* [Best Practice Turbo Integrator](https://downloads.cubewise.com/Bedrock/whitepapers/White_Paper_Best_Practice_Turbo_Integrator.pdf)
* [Best Practice Cube Design](https://downloads.cubewise.com/Bedrock/whitepapers/White_Paper_Best_Practice_Cube_Design.pdf)
* [Best Practice Rules](https://downloads.cubewise.com/Bedrock/whitepapers/White_Paper_Best_Practice_Rules.pdf)

## How to License

Anyone is free to copy, modify, use, compile, sell or distribute the original Bedrock code, documents and information (the information), either in source code form or as a compiled binary, for any purpose, commercial or non-commercial, and by any means, with the exception that you may not reproduce or publish the information on any web site, online service or printed media without prior express permission.

Where the information is copied, modified, used, compiled, sold or distributed, credit to the original author or authors must be left intact in the code or document.

All of the deliverable code on this site has been written from scratch. No code has been taken from other projects or from the open internet. Every line of code can be traced back to its original author. So the Bedrock code base is clean and is uncontaminated with licensed code from other projects.

## Warranties

All of the code, documents and information in Bedrock for TM1 are to be deemed without warranty.

## Contributions

The source code is hosted at [github.com/cubewise-code/bedrock-5](https://github.com/cubewise-code/bedrock-5). If you find a bug or feel like you can contribute please [fork](https://help.github.com/articles/fork-a-repo/) the repository, update the code and then create a [pull request](https://help.github.com/articles/about-pull-requests/) so we can merge in the changes.


# Deprecated Functions
IBM Planning Analytics TM1 Database 12 has several deprecated functions when compared to the earlier versions of the TM1 Database (e.g. 11.x) . Because of this, the following Bedrock processes have now been deprecated:
| Bedrock Process                                   | TM1 Database Deprecated Function         |
|---------------------------------------------------|---------------------------------|
| `}bedrock.cube.data.save`                         | `CubeSaveData`                  |
| `}bedrock.dim.attr.swapalias`                     | `SwapAliasWithPrincipalName`    |
| `}bedrock.hier.create.fromrollup.aliasswap`       | `SwapAliasWithPrincipalName`    |
| `}bedrock.security.client.password.reset`         | `AssignClientPassword`          |
| `}bedrock.server.dir.backup`                      | `ExecuteCommand`                |
| `}bedrock.server.dir.listcontents`                | `ExecuteCommand`                |
| `}bedrock.server.encrypt.directory`               | `ExecuteCommand`                |
| `}bedrock.server.encrypt.file`                    | `ExecuteCommand`                |
| `}bedrock.server.executecommand`                  | `ExecuteCommand`                |
| `}bedrock.server.logfile.delete`                  | `ExecuteCommand`                |
| `}bedrock.server.savedataall`                     | `SaveDataAll`                   |

# Modified Functions
Due to the deprecation of the above functions in the IBM Planning Analytics TM1 Database 12, the following Bedrock processes have been modified to ensure compatibility with the IBM Planning Analytics TM1 Database 12.4+. **The functionality of these processes has not changed.**
## Overview
Changes in the Bedrock processes were primarily due to:
- Deprecation of `CubeSetLogChanges`.
- Inability to access the `.rux` file.
- Deprecation of `ExecuteCommand` when used to delete a file (replaced with `ASCIIDelete`).
- Deprecation of the `}DimensionProperties` cube.
- Deprecation of `AssignClientPassword`.
- Deprecation of the `}ApplicationSecurity` cube.
  
## List of Changes
| Process Name                                 | Change Description                                                                                                                                       |
|---------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------|
| `}bedrock.cube.clone`                        | Replaced the attempt to read rules from the .rux file with the `CubeRuleGet` function.                                                                                  |
| `}bedrock.cube.data.clear`                  | Removed the `CubeSetLogChanges` function.                                                                                                                 |
| `}bedrock.cube.data.copy.intercube`         | Removed the `CubeSetLogChanges` function. Replaced the use of `ExecuteCommand` to delete a file with `ASCIIDelete`.                                       |
| `}bedrock.cube.data.copy`                   | Removed the `CubeSetLogChanges` function. Replaced the use of `ExecuteCommand` to delete a file with `ASCIIDelete`.                                       |
| `}bedrock.cube.data.export`                 | Removed the `CubeSetLogChanges` function.                                                                                                                 |
| `}bedrock.cube.data.import`                 | Removed the `CubeSetLogChanges` function.                                                                                                                 |
| `}bedrock.cube.dimension.add`               | Replaced the attempt to read rules from the `.rux` file with the `CubeRuleGet` function.                                                                                  |
| `}bedrock.cube.dimension.delete`            | Replaced the attempt to read rules from the `.rux` file with the `CubeRuleGet` function.                                                                                  |
| `}bedrock.cube.dimension.replace`           | Replaced the attempt to read rules from the `.rux` file with the `CubeRuleGet` function.                                                                                 |
| `}bedrock.cube.rule.manage`                 | Replaced the attempt to read rules from the `.rux` file with the `CubeRuleGet` function. Replaced the use of `ExecuteCommand` to delete a file with `ASCIIDelete`.         |
| `}bedrock.dim.attr.create`                  | Bug fix: The process parameters indicated that the default value for `pAttrType` was 'S', but this was not the case. The default has now been added.                                |
| `}bedrock.dim.clone`                        | The `}DimensionProperties` cube has been deprecated, and all references to it have been removed. Note: As a result, a dimension’s sort order can no longer be cloned. |
| `}bedrock.dim.create`                       | Implemented the `}bedrock.dim.create` function.                                                                                                                                  |
| `}bedrock.hier.clone`                       | The `}DimensionProperties` cube has been deprecated, and all references have been removed. Note: Because of this, the hierarchy's sort order cannot be cloned. |
| `}bedrock.hier.create.fromsubset`           | The `}DimensionProperties` cube has been deprecated, and all references have been removed. Note: Because of this, the hierarchy's sort order cannot be cloned. <br>Removal of `CubeSetLogChanges` function. |
| `}bedrock.hier.export.script`               | The `}DimensionProperties` cube has been deprecated, and all references have been removed. Note: Because of this, the dimension's sort order cannot be exported. |
| `}bedrock.hier.export`                      | The `}DimensionProperties` cube has been deprecated, and all references have been removed. Note: Because of this, the dimension's sort order cannot be exported. >Bug fix: String attribute values of "0" would not be exported. |
| `}bedrock.hier.import`                      | The `}DimensionProperties` cube has been deprecated, and all references have been removed. Note: Because of this, the dimension's sort order cannot be imported. |
| `}bedrock.hier.unwind`                      | Removed the `CubeSetLogChanges` function.                                                                                                                |
| `}bedrock.process.template`                 | Removed the `CubeSetLogChanges` function.                                                                                                               |
| `}bedrock.security.client.clone`            | Removed the `AssignClientPassword` function. Note: Because of this, a client's password cannot be set.                                                    |
| `}bedrock.security.client.create`           | Removed the `AssignClientPassword` function. Note: Because of this, a client's password cannot be set.                                                    |
| `}bedrock.security.object.assign`           | The `}ApplicationSecurity` cube has been deprecated, all references have been removed. Note: Because of this, an application's security cannot be set. |

A full list of all process modifications from Bedrock 4 to Bedrock 5 can be found here: [Bedrock Compare Pull Request](https://github.com/bdunleavy22/bedrock-compare/pull/2/files).
