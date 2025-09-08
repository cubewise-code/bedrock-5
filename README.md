<h1 align="center">
  <br>
  <a href="https://github.com/cubewise-code/bedrock-5"><img width="9149" height="2224" alt="bedrock5_logogray" src="https://github.com/user-attachments/assets/bdb178a3-7463-4c0b-a74b-f2c1a5059532" />
</h1>

# Bedrock 5 is fully compatible with IBM® Planning Analytics TM1 Database 12.4+

<p align="center">
  <a href="https://www.ibm.com/docs/en/planning-analytics/2.0.0?topic=12-welcome-tm1-database"><img src="https://img.shields.io/badge/TM1_Database-v12.4+-blue" alt="TM1 versions"></a>
  <a href="https://code.cubewise.com/open-source/bedrock/"><img src="https://img.shields.io/badge/Bedrock_5_latest_release-v5.0.0-green" alt="v5.0.0"></a>
</p>
<h1></h1>

### ⚠️ Bedrock 5 is still under development and will be released on the 30th of September, [click here for the upcoming webinar](https://events.teams.microsoft.com/event/f7564ab5-78aa-4c30-a93f-b880451f2de2@0635d657-0279-4110-9c8f-2ee27b1e065b). Please wait for the upcoming official release to use it in your projects. ⚠️ 

### This next-generation release of Bedrock has been refactored and rigorously tested to support the latest IBM Planning Analytics deployment options including TM1 Containerized, v12, and PA3 versions of the TM1 Server. Bedrock 5 does not support earlier versions of the TM1 Server. These versions (v11) are supported by [Bedrock 4](https://github.com/cubewise-code/bedrock)

<b>Bedrock 5</b> is the latest evolution of the Bedrock library, specifically updated for compatibility with TM1 Containerized, v12, and PA3 versions of the TM1 Server. This release reflects the ongoing commitment to maintaining best practices for Planning Analytics development, providing optimized, standardized, and scalable TurboIntegrator (TI) code assets that align with changes introduced in the TM1 Containerized, v12, and PA3 versions of the TM1 Server.

In this article:
- [What is Bedrock?](#what-is-bedrock)
- [Deprecated Functions](#deprecated-functions)
- [Modified Functions](#modified-functions)
- [Installation Guide](#installation-guide)

## What is Bedrock?
Bedrock is a community-driven Planning Analytics best practice framework. It provides modular, reusable TI processes, tools, documentation, and training resources designed to:
- Accelerate model development
- Increase maintainability
- Improve auditability
- Reduce administration and support overhead

The Bedrock library is built on years of global Planning Analytics implementation experience and is widely adopted in complex, enterprise-level Planning Analytics environments.

## What's New in Bedrock 5?

Bedrock 5 brings targeted updates to support TM1 Containerized, v12, and PA3 versions of the TM1 Server, including:
- <b>Compatibility Fixes</b>: Adjustments for updated Planning Analytics system behavior and function changes.
- <b>Deprecated Processes</b>: Clear documentation of processes no longer required or supported in the latest version of Planning Analytics.
- <b>Modified Processes</b>: Existing processes updated to maintain their original functionality while aligning with new Planning Analytics features and syntax.
- <b>Updated Installation Guide</b>: Step-by-step instructions for deploying Bedrock 5 into your Planning Analytics environment.

Note: Bedrock 5 is intended only for the TM1 Containerized, v12, and PA3 versions of the TM1 Server. For TM1 v11.x or PA 2.0.x, use [Bedrock 4](https://github.com/cubewise-code/bedrock)

## Why Bedrock?
With growing Planning Analytics adoption, standardization is critical. Bedrock provides:
- A standardized TI codebase for reuse across models and teams
- Faster development cycles through proven, modular processes
- Lower learning curve for new developers
- Reduced black-box risk through increased transparency and logging
- Improved scalability to handle complex business models with large datasets and high concurrency

## Where can I get more information?

The first place for further information is the [code.cubewise.com/bedrock](https://code.cubewise.com/bedrock) website. 

**Key resources**:
* Check out the [What's New](https://github.com/cubewise-code/bedrock/wiki/WhatsNew) page to familiarize yourself with what is different versus the previous version. 
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
TM1 Containerized, v12, and PA3 versions of the TM1 Server have deprecated functions when compared to the earlier versions of the TM1 Server. Because of this, the following Bedrock processes have now been deprecated:
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

# Modified Functions
Due to the deprecation of the above functions in the TM1 Containerized, v12, and PA3 versions of the TM1 Server, the following Bedrock processes have been modified to ensure compatibility with the latest version of Planning Analytics. **The functionality of these processes has not changed.**
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


# Installation Guide (For IBM Planning Analytics as a Service on AWS or Azure) <a name="installation-guide"></a>
> [!CAUTION]
> :bangbang: If the current Bedrock processes have been modified, this installation guide will overwrite those changes. Please see the [Upgrade Guide](#upgrade-guide) instead. :bangbang:
1. In this repository, navigate to the folder [`installation_files`](https://github.com/cubewise-code/bedrock-5/tree/main/installation_files).
2. Download a copy of the file `bedrock.json`.
<a name="database-file-manager-steps"></a>
3. Go to your Planning Analytics Database File Manager. To open your Planning Analytics Database File Manager, complete the following steps:
    - Navigate to your Planning Analytics v12 environment at: `https://<us-east-1>.planninganalytics.saas.ibm.com`. Replace `<us-east-1>` with your region.

       <img width="1584" height="718" alt="Screenshot 2025-08-28 205253" src="https://github.com/user-attachments/assets/5e5a9cda-98b5-426b-bd0e-1108969e0df7" />
    - Click the hamburger menu icon.
     
       <img width="1599" height="713" alt="Screenshot 2025-08-28 205516" src="https://github.com/user-attachments/assets/1c921878-7848-43ee-a84d-210ba4df510a" />
    - Click "+ New".
     
       <img width="1582" height="663" alt="Screenshot 2025-08-28 205627" src="https://github.com/user-attachments/assets/6b558d52-693e-4059-90ab-5d7e019f8940" />
    - Click "Workbench".
  
       <img width="464" height="410" alt="Screenshot 2025-08-28 210003" src="https://github.com/user-attachments/assets/9327664d-fba9-4467-bc15-95765d5793af" />
    - Right-Click the name of the Database you would like to install bedrock to.
  
       <img width="506" height="638" alt="Screenshot 2025-08-28 210319" src="https://github.com/user-attachments/assets/39183f40-5625-4d02-aeab-3ae2f09fb36f" />
    - Click "File Manager".
  
       <img width="2549" height="372" alt="Screenshot 2025-08-28 210757" src="https://github.com/user-attachments/assets/72d6295e-4625-4556-bd17-1b38307b5f2e" />
4. Upload the file `bedrock.json` to your TM1 Database. Do not rename the file or upload it into a folder. To upload, click the upload icon.

   <img width="2551" height="373" alt="Screenshot 2025-08-28 210607" src="https://github.com/user-attachments/assets/04e40ae1-87a8-41f3-9e09-90eacd533b77" />
5. Create a new Turbo Integrator Process. You can name it anything; it can be deleted after installation.

   <img width="535" height="648" alt="Screenshot 2025-08-28 211047" src="https://github.com/user-attachments/assets/7d34635c-a499-4597-9c4b-ee5cdc843373" />
6. Go back to the folder [`installation_files`](https://github.com/cubewise-code/bedrock-5/tree/main/installation_files).
7. Copy the text in the file `bedrock_installation_ti.txt` and paste it into the prologue of the Turbo Integrator process you just created.

  <img width="2554" height="1217" alt="Screenshot 2025-08-29 122531" src="https://github.com/user-attachments/assets/0dd381c8-93f9-4400-9230-d62f15be9169" />

8. <a name="get-connection-details"></a>In line 7, replace `<api_key_value>` with your API Key. [To generate an API Key, follow the steps in this guide](#Generate-API-Key-Guide).
9. In line 8, replace `<tenant_id>` with your instance's Tenant ID. Your Tenant ID can be found in the TM1 url, after `tenantId=` and before `&`, as seen here: 
  <img width="1129" height="513" alt="Screenshot 2025-08-29 123349" src="https://github.com/user-attachments/assets/bb3d228b-d608-466d-a218-a058b21ea1b2" />

10. In line 8, replace `<database_name>` with your TM1 Database's Name. The TM1 Database Name can be seen here: 

  <img width="350" height="361" alt="Screenshot 2025-08-29 123603" src="https://github.com/user-attachments/assets/17e8fa89-dcc6-4c34-a5f9-5682b1f72e56" />
  
  ‼️Make sure your Planning Analytics Database Name is url encoded. To url encode your Database Name, paste it in the text box at this website: [URL Encoder](https://www.urlencoder.org/)

11. Save and run the process.
12. When the process is complete, Bedrock will be installed!
13. Delete `}bedrock-installation.process` from the TM1 Database.
14. (Optional) Delete `bedrock.json` and the process you created.

# Upgrade Guide
1. In this repository, navigate to the folder [`installation_files`](https://github.com/cubewise-code/bedrock-5/tree/main/installation_files).
2. Download a copy of the file `bedrock-v11.json`.
3. Upload the `bedrock-v11.json` to the TM1 Database File Manager. [For how to navigate to the File Manager, go to step 3. in the Installation Guide.](#database-file-manager-steps)
4. Create a process with the following specifications:
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
    2. In the Prologue Tab, paste the following code:

    ```
    # List of Keys required for a Process to be created from HTTP Request
    user = 'apikey';
    password = '<api_key_value>';
    base_url = 'https://us-east-1.planninganalytics.saas.ibm.com/api/<tenant_id>/v0/tm1/<database_name>';
    
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
    replacing `<api_key_value>`, `<database_name>` and `<tenant_id>` with the correct values. [To find the correct values, go to steps 9-11. in the Installation Guide.](#get-connection-details)
    
    3. In the Data Tab, paste the following code:

    ```
    sProcessJson = '{}';
    i = 0;
    WHILE( i <  nListSize );
        sKeyName = JsonToString( JsonGet(sJsonKeyList, i ) );
        sProcessJson = JsonAdd( sProcessJson, sKeyName, EXPAND( '%v' | sKeyName | '%' ) );
    
        i = i + 1;
    END;
    
    
    sProcessName = JsonToString( JsonGet( sProcessJson, 'Name' ) );
    
    ExecuteHttpRequest( 'GET', base_url | '(''' | sProcessName | ''')', '-u '|user|':'|password, '-h User-Agent:BedrockInstaller', '-h Content-Type:application/json; odata.streaming=true; charset=utf-8', '-h Accept:application/json;odata.metadata=none,text/plain', '-h TM1-SessionContext:BedrockInstaller', '-k' );
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

# Generate API Key Guide
1. Navigate to your TM1 v12 environment at: `https://<us-east-1>.planninganalytics.saas.ibm.com`. Replace `<us-east-1>` with your region.

   <img width="1584" height="718" alt="Screenshot 2025-08-28 205253" src="https://github.com/user-attachments/assets/5e5a9cda-98b5-426b-bd0e-1108969e0df7" />
2. Click your profile icon in the top-right corner of the screen.

   <img width="648" height="375" alt="Screenshot 2025-09-03 101340" src="https://github.com/user-attachments/assets/491f5ef8-096b-4c83-ba2e-ab86fe145a97" />
3. Click "Manage API Keys".

   <img width="1928" height="498" alt="Screenshot 2025-09-03 101554" src="https://github.com/user-attachments/assets/30347cd0-e19a-4087-a6c8-5f333aca7786" />
4. Click "Generate Key".

   <img width="901" height="358" alt="Screenshot 2025-09-03 102959" src="https://github.com/user-attachments/assets/51e51736-065a-442e-a38c-72c3cecc1f4e" />
5. Enter an "API key name". Click "generate key".

   <img width="936" height="374" alt="Screenshot 2025-09-03 102004" src="https://github.com/user-attachments/assets/92d6568f-7641-47c9-8cd2-89d42f3d4b37" />
6. Save your API key in a secure location. :warning: This unique API key is unrecoverable. If you lose it, you must recreate a new one.



