Follow these steps to upgrade Bedrock 5.

---

## Step 1: Get the comparison file
1. In this repository, go to the [`installation_files`](https://github.com/cubewise-code/bedrock-5/tree/main/installation_files) folder.  
2. Download the file **`installation_files/assets/bedrock-v11.json`**.  
3. Upload **`bedrock-v11.json`** to the **TM1 Database File Manager**.  
   - For navigation steps, see **Step 3** in the [Installation Guide](https://github.com/cubewise-code/bedrock-5/wiki/Installation-Guide#step-3).  

---

## Step 2: Create a comparison process
Create a new TurboIntegrator process in IBM Planning Analytics with the following configuration:

### Variables Tab
Add **11 string variables** in this exact order:

- `vName`  
- `vPrologProcedure`  
- `vMetadataProcedure`  
- `vDataProcedure`  
- `vEpilogProcedure`  
- `vHasSecurityAccess`  
- `vUIData`  
- `vDataSource`  
- `vParameters`  
- `vVariables`  
- `vVariablesUIData`  

---

### Prolog Tab
Paste the following code:

```plaintext
sError = '';
sAuthenticationMode = 'BASIC_API_KEY';

# BASIC API KEY AUTHENTICATION PARAMETERS
user = 'apikey';
password = '<api_key_value>';
base_url = 'https://<region>.planninganalytics.saas.ibm.com/api/<tenant_id>/v0/tm1/<database_name>';

auth_url = '';

##########################################################################################
# Region - _construct_service_and_auth_root (Convert Python to TI)
##########################################################################################

# Region - _construct_all_version_service_and_auth_root_from_base_url (Convert Python to TI)

sEndsWith = '/api/v1';
nEndsWith = LONG( sEndsWith );

IF( SCAN( 'api/v1/Databases', base_url ) <> 0 );
  IF( auth_url @= '' );
    sError = 'Authentication Method was determined to be: "' | sAuthenticationMode | '" and base_url includes "api/v1/Databases", which requires "auth_url". However, "auth_url='|auth_url|'".';
    LogOutput( 'ERROR', sError );
    ProcessBreak();
  ENDIF;
  
ELSEIF( SUBST( base_url, LONG( base_url ) - nEndsWith, nEndsWith ) @= sEndsWith );
  auth_url = base_url | '/Configuration/ProductVersion/$value';
ELSE;
  base_url = base_url | sEndsWith;
  auth_url = base_url | '/Configuration/ProductVersion/$value';
ENDIF;
# EndRegion

##########################################################################################
# EndRegion
##########################################################################################

base_url = base_url | '/Processes';

# List of Keys required for a Process to be created from HTTP Request
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
    sVarMapping = JsonAdd( sVarMapping, 'v' | NumberToString( i + 1 ), StringToJson ( '/' | sKeyName ) );
    i = i + 1;
END;

# Datasource Variables
DataSourceJsonVariableMapping = sVarMapping;
DataSourceType = 'JSON';
DataSourceJsonRootPointer     = '/data';
DatasourceNameForServer       = 'bedrock-v11.json';
DatasourceASCIIQuoteCharacter = '';
```

➡ **Update lines 6–7:** Replace:  
- `<api_key_value>`  
- `<database_name>`  
- `<region>`  
- `<tenant_id>`  

with the correct values.  
To locate them, see **Steps 8–10** in the [Installation Guide](https://github.com/cubewise-code/bedrock-5/wiki/Installation-Guide#step-8).  

---

### Data Tab
Paste the following code:

```plaintext
sStandardProcessJson = '{}';
i = 0;
WHILE( i <  nListSize );
    sKeyName = JsonToString( JsonGet(sJsonKeyList, i ) );
    sProcessBodySection = EXPAND( '%v' | NumberToString( i + 1 ) | '%' );
    sStandardProcessJson = JsonAdd( sStandardProcessJson, sKeyName, sProcessBodySection );
    
    i = i + 1;
END;

sProcessName = JsonToString( JsonGet( sStandardProcessJson, 'Name' ) );
TextOutput( 'bedrock_process_comparison.txt', sProcessName );

ExecuteHttpRequest( 'GET', base_url | '(''' | sProcessName | ''')', '-u '|user|':'|password, '-h User-Agent:BedrockInstaller', '-h Content-Type:application/json; odata.streaming=true; charset=utf-8', '-h Accept:application/json;odata.metadata=none,text/plain', '-h TM1-SessionContext:BedrockInstaller', '-k' );
sCurrentProcessJson = HttpResponseGetBody(); nStatusCode = HttpResponseGetStatusCode();

nDifferent = 0;
i = 0;
WHILE( i <  nListSize );
    sKeyName = JsonToString( JsonGet(sJsonKeyList, i ) );
    
    sStandardProcessJsonSection = JsonGet( sStandardProcessJson, sKeyName );
    sCurrentProcessJsonSection = JsonGet( sCurrentProcessJson, sKeyName );

    IF( JsonTest( sStandardProcessJsonSection, sCurrentProcessJsonSection ) = 0 );
        TextOutput( 'bedrock_process_comparison.txt', sKeyName );
        nDifferent = 1;
    ENDIF;
    
    i = i + 1;
END;

IF( nDifferent = 0 );
    TextOutput( 'bedrock_process_comparison.txt', 'NO DIFFERENCE' );
ENDIF;

TextOutput( 'bedrock_process_comparison.txt', '' );
```

---

## Step 3: Run the comparison
1. Save and run the process.  
2. Open **`bedrock_process_comparison.txt`** to see which processes differ.  

---

## Step 4: Apply updates
1. Navigate back to the [`installation_files`](https://github.com/cubewise-code/bedrock-5/tree/main/installation_files) folder in this repository.  
2. Download the file **`installation_files/assets/bedrock.json`**.  
3. Inside that file, locate the `"data"` key — this is a JSON array.  
4. In the array, find any JSON object where `"Name"` equals the process you **do not want to overwrite**.  
5. Remove that JSON object from the array.  

   > For help with JSON structure, see [JavaScript JSON Basics](https://www.w3schools.com/js/js_json.asp).  

---

## Step 5: Continue installation
Return to **Step 3** in the [Installation Guide](https://github.com/cubewise-code/bedrock-5/wiki/Installation-Guide#step-3) and proceed with the standard installation steps.
