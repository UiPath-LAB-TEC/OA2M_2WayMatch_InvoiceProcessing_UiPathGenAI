Demo showcasing UiPath + GenAI
Showcases Pattern 2 (Analyst/Doer)
Created by Dhruv Patel <dhruv.patel@uipath.com>
Video showcasing Demo in action: https://view.highspot.com/viewer/648c7ed897109a3503a176a4


Thanks for joining our Dev Dive: Unleashing the Power of Automation with Generative AI! This template file is a great way to see how you can operationalize 
Generative AI in your organization with security, governance and auditability in mind. Please note, this template is not production ready, it is meant more for demos
and helping kick-start your journey with UiPath AI-Powered automation!

Pre-reqs/How-to-use:

1. Access to UiPath Document Understanding. The workflow points to our OOTB Invoice model. You may change this as needed to your customized model or another 
endpoint which you may find here: https://docs.uipath.com/document-understanding/automation-cloud/latest/user-guide/public-endpoints. For any DU questions, please
refer to docs.uipath.com.

2. Access to a Generative AI model, the template uses Micrsosoft Azure OpenAI, but you may swap out the activity for another GenAI model if needed. note: you may
need to update some configuration of the workflow.

3. Access to Integration Service. This is used to manage the authentication for the Microsoft Azure OpenAI Activity. If you do not have Integration Service, please 
reconfigure this activity with a generic API activity. See more here: https://docs.uipath.com/activities/other/latest/developer/about-the-web-activities-pack

4. Access to an ERP system. The workflow points to SAP by default, but this can work with any system that you use for two way matching. If you choose a different
system, please update the PO_Lookup.xaml activity accordingly to navigate to your PO data based on the PO number extracted from DU.

5. In the project panel, you will see a folder "prompts". These are the prompts used for both GenAI calls. You may change the prompts to see how it changes the output.
If you change any placeholders (they are between <>), then this may break the automation as we use it to add data from the automation before sending the prompts to
Azure OpenAI.

6. In the project panel, you will see a folder "documents". This is where you can place the Invoice document you would like to process. The Invoice DU workflow 
already points to this folder and will only process the first doc.


7. In Main.xaml the main variables you need to add "Default" values for is "du_api_key" and/or "du_api_key2" with your API key.

8. In PO_Lookup.xaml, if you use SAP, you need to update the erp_Client, erp_userName, erp_pwd with your credentials. You will also need to update the "Connection name"
and potentially the SAP Logon Path (review the first two SAP activities).

9. In Main.xaml, you will need to update the last activity "Create Document Validation Action" to point to your Orchestrator & storage bucket. 
Alternatively, you can replace this activity with a "Present Validation Station" activity for local review.


~~~ Happy Automating and looking forward to seeing all the AI-Powered Automations you build with the UiPath Business Automation Platform! ~~~