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
