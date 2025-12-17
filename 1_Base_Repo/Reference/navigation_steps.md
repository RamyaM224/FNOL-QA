# FNOL claim submission workflow
## Initial Setup of sending email
### 1. Email setup
- Send an email from CAZ_Claims_UAT_FNOL <caz.claims.uat.fnol@zurich.com>
- Verify in COSMOS DB to check for the work item 
- Validate all fields like email subject,date and time ,policy no ,date of loss

### 2. Creation of work item in FNOL portal
Verify if work item is created in FNOL portal
- Person who sent email
- Urgent flag
- Asterisk
- Work item id
- Subject
- Date and time
- Policy no
- Date of loss
## Work item case status To do and assignee as "Unassigned"
### 3. Case status as "To do" 
- Verify the work item id for the email extracted 
- Validate the work item status and check the assignee of Work item id
- Work item id status will be "To do" and will be in Unassigned state

### 4. Validation of "Start a Claim" button and Assign to me dropdown
- Select the extracted work item id for the email sent
- Assign the work item id to yourself or others
- Select the work item id and click on start a claim button
### 5. Validation of Policy search screen in FNOL portal
- Verify the extracted email preview for the email sent
- Verify if policy number ,loss date and attachments are extracted from email in policy search screen.
- Verify if user is able to download attachment from the extracted email in the extracted work item. 
### 6. General Liability LOB
- Login into FNOL Portal
- Select the work item id ,assign and click on start a claim button
- Search a General Liability policy 
### 7. Property LOB
- Login into FNOL Portal
- Select the work item id ,assign and click on start a claim button
- Search a Property policy
### 8. Financial Lines LOB
- Login into FNOL Portal
- Select the work item id ,assign and click on start a claim button
- Search a Financial Lines policy
 
### 9. Inland Marine LOB
- Login into FNOL Portal
- Select the work item id ,assign and click on start a claim button
- Search a Inland marine policy
 
### 10. Umbrella LOB
- Login into FNOL portal
- Select the work item id ,assign and click on start a claim button
- Search a Umbrella policy
 
### 11. Contigent Lessor LOB
- Login into FNOL portal
- Select the work item id ,assign and click on start a claim button
- Search a Contigent Lessor  policy
 
### 12. Excess auto LOB
- Login into FNOL portal
- Select the work item id ,assign and click on start a claim button
- Search a Excess Auto  policy
 
 
