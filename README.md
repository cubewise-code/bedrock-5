# Bedrock NextGen
This repository provides updates to the Bedrock library for compatibility with TM1 Version 12. It includes a list of deprecated and modified Bedrock processes due to changes in TM1 functions and system behavior. The modified processes maintain the same functionality, with necessary adjustments to support TM1 V12. An installation guide is included to help deploy the updated processes.

[Depreciation Functions](#depreciation-functions)

[Modified Functions](#modified-functions)

[Installation Guide](#installation-guide)

# Depreciation Functions
Due to certain functions being depreciated in TM1 V12, the following bedrock processes have been depreciated:
| Bedrock Process                                   | TM1 Deprecated Function         |
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

When these processes are run, they will only log an output stating that they have been depreciated. They will not do what they did in TM1 V11.

# Modified Functions
Due to certain functions being depreciated in TM1 V12, the following bedrock processes have been modified to be able to run on TM1 V12. **The functionality of these processes has not changed.**
## Overview
Changes were primarily due to the:
- Depreciation of `CubeSetLogChanges`.
- Inability to access to the .rux file.
- Depreciation of `ExecuteCommand`, using the function to delete a file. Replaced with ASCIIDelete.
- Depreciation of the `}DimensionProperties` cube.
- Depreciation of `AssignClientPassword`.
- Depreciation of the `}ApplicationSecurity` cube.
  
## List of Changes
| Process Name                                 | Change Description                                                                                                                                       |
|---------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------|
| `}bedrock.cube.clone`                        | Replaced attempt to read rule from .rux file to `CubeRuleGet` function.                                                                                  |
| `}bedrock.cube.data.clear`                  | Removal of `CubeSetLogChanges` function.                                                                                                                 |
| `}bedrock.cube.data.copy.intercube`         | Removal of `CubeSetLogChanges` function.<br>Replaced use of `ExecuteCommand` to delete a file with `ASCIIDelete`.                                       |
| `}bedrock.cube.data.copy`                   | Removal of `CubeSetLogChanges` function.<br>Replaced use of `ExecuteCommand` to delete a file with `ASCIIDelete`.                                       |
| `}bedrock.cube.data.export`                 | Removal of `CubeSetLogChanges` function.                                                                                                                 |
| `}bedrock.cube.data.import`                 | Removal of `CubeSetLogChanges` function.                                                                                                                 |
| `}bedrock.cube.dimension.add`               | Replaced attempt to read rule from .rux file to `CubeRuleGet` function.                                                                                  |
| `}bedrock.cube.dimension.delete`            | Replaced attempt to read rule from .rux file to `CubeRuleGet` function.                                                                                  |
| `}bedrock.cube.dimension.replace`           | Replaced attempt to read rule from .rux file to `CubeRuleGet` function.                                                                                  |
| `}bedrock.cube.rule.manage`                 | Replaced attempt to read rule from .rux file to `CubeRuleGet` function.<br>Replaced use of `ExecuteCommand` to delete a file with `ASCIIDelete`.         |
| `}bedrock.dim.attr.create`                  | Bug fix: The process parameters say that the default value for `pAttrType` is 'S' but that was not true. It has been added.                                |
| `}bedrock.dim.clone`                        | The `}DimensionProperties` cube has been depreciated, all references have been removed.<br>NOTE: Because of this the dimension's sort order cannot be cloned. |
| `}bedrock.dim.create`                       | Created this function.                                                                                                                                   |
| `}bedrock.hier.clone`                       | The `}DimensionProperties` cube has been depreciated, all references have been removed.<br>NOTE: Because of this the hierarchy's sort order cannot be cloned. |
| `}bedrock.hier.create.fromsubset`           | The `}DimensionProperties` cube has been depreciated, all references have been removed.<br>NOTE: Because of this the hierarchy's sort order cannot be cloned.<br>Removal of `CubeSetLogChanges` function. |
| `}bedrock.hier.export.script`               | The `}DimensionProperties` cube has been depreciated, all references have been removed.<br>NOTE: Because of this the dimension's sort order cannot be exported. |
| `}bedrock.hier.export`                      | The `}DimensionProperties` cube has been depreciated, all references have been removed.<br>NOTE: Because of this the dimension's sort order cannot be exported.<br>Bug fix: String attribute values of "0" would not be exported. |
| `}bedrock.hier.import`                      | The `}DimensionProperties` cube has been depreciated, all references have been removed.<br>NOTE: Because of this the dimension's sort order cannot be imported. |
| `}bedrock.hier.unwind`                      | Removal of `CubeSetLogChanges` function.                                                                                                                 |
| `}bedrock.process.template`                 | Removal of `CubeSetLogChanges` function.                                                                                                                 |
| `}bedrock.security.client.clone`            | Removal of `AssignClientPassword` function.<br>NOTE: Because of this a client's password cannot be set.                                                  |
| `}bedrock.security.client.create`           | Removal of `AssignClientPassword` function.<br>NOTE: Because of this a client's password cannot be set.                                                  |
| `}bedrock.security.object.assign`           | The `}ApplicationSecurity` cube has been depreciated, all references have been removed.<br>NOTE: Because of this an application's security cannot be set. |

A full list of all process modifications from Bedrock V4 to Bedrock NextGen can be found [here](https://github.com/bdunleavy22/bedrock-compare/pull/2/files).
# Installation Guide
> [!CAUTION]
> :bangbang: If the current bedrock processes have been modified, this installation guide will overwrite those changes. Please see the [Upgrade Guide](#upgrade-guide) instead. :bangbang:
1. Navigate to the folder `installation_files` in this GitHub Repo.
2. Download a copy of the file `bedrock.json`.
3. Go to your TM1 Database File Manager.
4. Upload the file `bedrock.json` to your TM1 Database. Do not rename the file and do not upload it to a folder, upload it to the root directory.
5. Create a new Turbo Integrator Process, you can name it whatever you like. It can be deleted after the installation process is complete.
6. Go back to the folder `installation_files` in this GitHub Repo.
7. Copy the text in the file `bedrock_installation_ti.txt` and paste it into the prologue of the Turbo Integrator process you just created.
8. In line 15, replace `<api_key_value>` with your API Key.
9. In line 16, replace `<tenant_id>` with your instance's Tenant ID.
10. In line 16, replace `<database_name>` with your TM1 Database's Name.
11. Save the process, then run the process.
12. When the process is complete, bedrock will be installed!
13. Delete `}bedrock-installation.process` from the TM1 Database.
14. (Optional) Delete `bedrock.json` from your Database's files. Delete the process you created.

# Upgrade Guide
1. Navigate to the folder `installation_files` in this GitHub Repo.
2. Download a copy of the file `bedrock-v11.json`.
3. Create a process with the following specifications:
  1. In the Variables Tab, create 11 string variables in the following order with the following names:
```
[{"Name":"vName","Type":"String","Position":1,"StartByte":0,"EndByte":0},
{"Name":"vPrologProcedure","Type":"String","Position":2,"StartByte":0,"EndByte":0},
{"Name":"vMetadataProcedure","Type":"String","Position":3,"StartByte":0,"EndByte":0},
{"Name":"vDataProcedure","Type":"String","Position":4,"StartByte":0,"EndByte":0},
{"Name":"vEpilogProcedure","Type":"String","Position":5,"StartByte":0,"EndByte":0},
{"Name":"vHasSecurityAccess","Type":"String","Position":6,"StartByte":0,"EndByte":0},
{"Name":"vUIData","Type":"String","Position":7,"StartByte":0,"EndByte":0},
{"Name":"vDataSource","Type":"String","Position":8,"StartByte":0,"EndByte":0},
{"Name":"vParameters","Type":"String","Position":9,"StartByte":0,"EndByte":0},
{"Name":"vVariables","Type":"String","Position":10,"StartByte":0,"EndByte":0},
{"Name":"vVariablesUIData","Type":"String","Position":11,"StartByte":0,"EndByte":0}] 
```
  3. In the Prologue Tab, paste the following code:
``` # List of Keys required for a Process to be created from HTTP Request
url = '<base_url>';
api_key = '<api_key>';
sJsonKeyList = '[
    "Name",
    "PrologProcedure",
    "MetadataProcedure",
    "DataProcedure",
    "EpilogProcedure",
    "HasSecurityAccess",
    "UIData",
    "DataSource",
    "Parameters",
    "Variables",
    "VariablesUIData"
]';

# Create the Variable Mapping based on List of Keys
sVarMapping = '{}';
nListSize = JsonSize( sJsonKeyList );
i = 0;
WHILE( i <  nListSize );
    sKeyName = JsonToString( JsonGet(sJsonKeyList, i ) );
    sVarMapping = JsonAdd( sVarMapping, 'v' | sKeyName, StringToJson ( '/' | sKeyName ) );

    i = i + 1;
END;

# Datasource Variables
DataSourceJsonVariableMapping = sVarMapping;
DataSourceType = 'JSON';
DataSourceJsonRootPointer     = '/data';
DatasourceNameForServer       = 'bedrock-v11.json';
```
  replacing `<base_url>` and `<api_key>` with the correct values.
  
  4. In the Data Tab, paste the following code:
  ```
sProcessJson = '{}';
i = 0;
WHILE( i <  nListSize );
    sKeyName = JsonToString( JsonGet(sJsonKeyList, i ) );
    sProcessJson = JsonAdd( sProcessJson, sKeyName, EXPAND( '%v' | sKeyName | '%' ) );

    i = i + 1;
END;


sProcessName = JsonToString( JsonGet( sProcessJson, 'Name' ) );

ExecuteHttpRequest( 'GET', url | '(''' | sProcessName | ''')', '-u apikey:' | api_key, '-h User-Agent:BedrockInstaller', '-h Content-Type:application/json; odata.streaming=true; charset=utf-8', '-h Accept:application/json;odata.metadata=none,text/plain', '-h TM1-SessionContext:BedrockInstaller', '-k' );
sBody = HttpResponseGetBody(); nStatusCode = HttpResponseGetStatusCode();
sDifference = 'SAME: ';
IF( JsonTest( sBody, sProcessJson ) = 0 );
  sDifference = 'DIFF: ';
ENDIF;
TextOutput( 'bedrock_process_comparison.txt', sDifference, sProcessName );
```
5. Run the process.
6. Open `bedrock_process_comparison.txt` to see which processes were found to be different.
7. Navigate to the folder `installation_files` in this GitHub Repo.
8. Download a copy of the file `bedrock.json`.
9. Manually delete the lines in the file `bedrock.json` which has `ProcessName` of the processes which you would not like to be overridden.
10. Continue to Step 3. in the [Installation Guide](#installation-guide)
