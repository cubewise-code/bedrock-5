# Bedrock 5.0.0 Release Notes

## Release Date: September 30, 2024

## Overview

Bedrock 5 is a major release specifically designed for IBM Planning Analytics TM1 Database 12.4+. This release addresses compatibility issues arising from deprecated TM1 functions while maintaining the full functionality of the Bedrock library.

## Breaking Changes

### Minimum Version Requirement

- **Required**: IBM Planning Analytics TM1 Database 12.4 or higher
- **Not Compatible**: TM1 11.x or Planning Analytics 2.0.x (use Bedrock 4 for these versions)

### Deprecated Processes

IBM Planning Analytics TM1 Database 12 has several deprecated functions when compared to the earlier versions of the TM1 Database. Because of this, the following Bedrock processes have now been deprecated:
| Bedrock Process | TM1 Deprecated Function |
|---------------------------------------------------|---------------------------------|
| `}bedrock.cube.data.save` | `CubeSaveData` |
| `}bedrock.dim.attr.swapalias` | `SwapAliasWithPrincipalName` |
| `}bedrock.hier.create.fromrollup.aliasswap` | `SwapAliasWithPrincipalName` |
| `}bedrock.security.client.password.reset` | `AssignClientPassword` |
| `}bedrock.server.dir.backup` | `ExecuteCommand` |
| `}bedrock.server.dir.listcontents` | `ExecuteCommand` |
| `}bedrock.server.encrypt.directory` | `ExecuteCommand` |
| `}bedrock.server.encrypt.file` | `ExecuteCommand` |
| `}bedrock.server.executecommand` | `ExecuteCommand` |
| `}bedrock.server.logfile.delete` | `ExecuteCommand` |
| `}bedrock.server.savedataall` | `SaveDataAll` |

## Modified Functions

### Summary of Changes

Due to the deprecation of the above functions in the IBM Planning Analytics TM1 Database 12, the following Bedrock processes have been modified to ensure compatibility with the IBM Planning Analytics TM1 Database 12.4+. **The functionality of these processes has not changed.**

Changes in the Bedrock processes were primarily due to:

- Deprecation of `CubeSetLogChanges`.
- Inability to access the `.rux` file.
- Deprecation of `ExecuteCommand` when used to delete a file (replaced with `ASCIIDelete`).
- Deprecation of the `}DimensionProperties` cube.
- Deprecation of `AssignClientPassword`.
- Deprecation of the `}ApplicationSecurity` cube.

### Detailed Process Modifications

| Process Name                        | Change Description                                                                                                                                                                                                               |
| ----------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `}bedrock.cube.clone`               | Replaced the attempt to read rules from the .rux file with the `CubeRuleGet` function.                                                                                                                                           |
| `}bedrock.cube.data.clear`          | Removed the `CubeSetLogChanges` function.                                                                                                                                                                                        |
| `}bedrock.cube.data.copy.intercube` | Removed the `CubeSetLogChanges` function. Replaced the use of `ExecuteCommand` to delete a file with `ASCIIDelete`.                                                                                                              |
| `}bedrock.cube.data.copy`           | Removed the `CubeSetLogChanges` function. Replaced the use of `ExecuteCommand` to delete a file with `ASCIIDelete`.                                                                                                              |
| `}bedrock.cube.data.export`         | Removed the `CubeSetLogChanges` function.                                                                                                                                                                                        |
| `}bedrock.cube.data.import`         | Removed the `CubeSetLogChanges` function.                                                                                                                                                                                        |
| `}bedrock.cube.dimension.add`       | Replaced the attempt to read rules from the `.rux` file with the `CubeRuleGet` function.                                                                                                                                         |
| `}bedrock.cube.dimension.delete`    | Replaced the attempt to read rules from the `.rux` file with the `CubeRuleGet` function.                                                                                                                                         |
| `}bedrock.cube.dimension.replace`   | Replaced the attempt to read rules from the `.rux` file with the `CubeRuleGet` function.                                                                                                                                         |
| `}bedrock.cube.rule.manage`         | Replaced the attempt to read rules from the `.rux` file with the `CubeRuleGet` function. Replaced the use of `ExecuteCommand` to delete a file with `ASCIIDelete`.                                                               |
| `}bedrock.dim.attr.create`          | Bug fix: The process parameters indicated that the default value for `pAttrType` was 'S', but this was not the case. The default has now been added.                                                                             |
| `}bedrock.dim.clone`                | The `}DimensionProperties` cube has been deprecated, and all references to it have been removed. Note: As a result, a dimension’s sort order can no longer be cloned.                                                            |
| `}bedrock.dim.create`               | Implemented the `}bedrock.dim.create` function.                                                                                                                                                                                  |
| `}bedrock.hier.clone`               | The `}DimensionProperties` cube has been deprecated, and all references have been removed. Note: Because of this, the hierarchy's sort order cannot be cloned.                                                                   |
| `}bedrock.hier.create.fromsubset`   | The `}DimensionProperties` cube has been deprecated, and all references have been removed. Note: Because of this, the hierarchy's sort order cannot be cloned. <br>Removal of `CubeSetLogChanges` function.                      |
| `}bedrock.hier.export.script`       | The `}DimensionProperties` cube has been deprecated, and all references have been removed. Note: Because of this, the dimension's sort order cannot be exported.                                                                 |
| `}bedrock.hier.export`              | The `}DimensionProperties` cube has been deprecated, and all references have been removed. Note: Because of this, the dimension's sort order cannot be exported. >Bug fix: String attribute values of "0" would not be exported. |
| `}bedrock.hier.import`              | The `}DimensionProperties` cube has been deprecated, and all references have been removed. Note: Because of this, the dimension's sort order cannot be imported.                                                                 |
| `}bedrock.hier.unwind`              | Removed the `CubeSetLogChanges` function.                                                                                                                                                                                        |
| `}bedrock.process.template`         | Removed the `CubeSetLogChanges` function.                                                                                                                                                                                        |
| `}bedrock.security.client.clone`    | Removed the `AssignClientPassword` function. Note: Because of this, a client's password cannot be set.                                                                                                                           |
| `}bedrock.security.client.create`   | Removed the `AssignClientPassword` function. Note: Because of this, a client's password cannot be set.                                                                                                                           |
| `}bedrock.security.object.assign`   | The `}ApplicationSecurity` cube has been deprecated, all references have been removed. Note: Because of this, an application's security cannot be set.                                                                           |

## Bug Fixes from Bedrock 4 to Bedrock 5

- Fixed `}bedrock.dim.attr.create` default parameter value for `pAttrType`
- Fixed `}bedrock.hier.export` bug where string attribute values of "0" were not exported

## Additional Resources

- [Full Comparison of Changes](https://github.com/bdunleavy22/bedrock-compare/pull/2/files)
- [Installation Guide](installation_files/README.md)
- [Process Documentation](https://github.com/cubewise-code/bedrock-5/wiki/Process-Documentation)

## Support

For questions or issues:

- GitHub Issues: [github.com/cubewise-code/bedrock-5/issues](https://github.com/cubewise-code/bedrock-5/issues)
- Documentation: [code.cubewise.com/bedrock](https://code.cubewise.com/bedrock)
- Community Support: [Coming Soon]

---

_Note: This is a living document and may be updated as new information becomes available or issues are discovered._
