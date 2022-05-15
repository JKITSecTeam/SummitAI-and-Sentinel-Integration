# SummitAI-and-Sentinel-Integration
This project is to integrate Microsoft Sentinel with SummitAI Helpdesk for ticket and incident creation and update.

# Prerequistes:
1. Acquire an API address from SummitAI
2. Deploy user accounts with admin prvileges in Summit AI helpdesk
3. A Keyvault in Azure to store SummitAI Username and Password as secrets.

# Deployment:

1. We would need a Sentinel Soltuion with incidents generated.
2. In Automation, created a playbook with Sentinel Incident trigger and logic app will be created.
3. In the logic app page, go to logic app designer and the sentinel incident trigger will be displayed.
4. Next, click on the plus sign and select add an action.
5. Search for Http and select the Http action.
6. On the Http connector, following fields should be filled as follows.


Method: POST

URI: SummitAI API url (https://stgsea2.symphonysummit.com/JohnKeells/api.integration/REST/Summit_RESTWCF.svc/RESTService/CommonWS_JsonObjCall)

Body: Use provided json format. (Note: Please replace the appropriate fields.)

# Automation:
1. Go to Sentinel Workspace and select automation.
2. Create a automation rule, and fill out the conditions as follows:
In the condtions, If analytic rule name contains all.
In the actions, Select run playbook and select the playbook we have created in the previous step and click apply.
