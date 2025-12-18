
---
agent: 'agent'
description: Generate detailed manual test cases in CSV format for the given user story and acceptance criteria.
---
 
# Manual Test Case Generation Prompt
 
## Input Requirements
 
**User Story File Path:** Prompt user to provide the file path at runtime
- Example: `/workspaces/FNOL-/1_Base_repo/Userstory/CAMS-1863.md'

- The prompt will ask: "Please provide the User Story file path:"
 
**Template Reference:** `/workspaces/FNOL-/1_Base_repo/Template/Template.md'

**Navigation Steps Reference:** `/workspaces/FNOL-/1_Base_repo/Reference/navigation_steps.md`

**Output Location:** `/workspaces/FNOL-/4_Design_Studio/CCI-101_Output.csv`

- The prompt will ask: "Please provide the Output Location file path:"


---
 
## Goal
 
Generate manual test cases in CSV format based on the user story provided in the input file path. Each test case should follow the template structure and application flow defined in the reference documents.
 
---
 
## Instructions
 
### 1. Read Input Files
- Prompt the user to enter the User Story file path
- Read the user story from the provided file path
- Read the template structure from `Template.md`
- Read any reference documents for application flow and navigation steps from `navigation_steps.md`
 
### 2. Analyze User Story
- Identify all distinct scenarios within the user story **ONLY**
- Do not create additional scenarios beyond what is explicitly defined in the user story 
- Extract scenario-specific details:
  - Scenario title/name
  - Acceptance criteria
  - Preconditions (explicit or contextual)
  - Expected outcomes
  - UI elements mentioned
 
### 3. Generate Test Cases
 
**For each scenario give me testcases positive and negative with clear steps with test case name,test case description, expected result and status **

 
 **Complete Test Case Information**
- TC ID: Sequential number
- Test Type: Manual
- Test Case Name: Full descriptive name following format
- Test case Description: Complete objective of the test case
- Test steps: First  step (numbered as "1. ")
- Expected Result: First expected result (numbered as "1. ")
- Status: Done ,In Progress ,Not Started
- Components: Middle Market
- User Story: CCI-101
- Priority: High / Medium / Low
- Scenario Type: Positive and Negative
 
 
#### Test Case Structure (Based on Template)
 
**Required Fields:**
- **TC ID:** Sequential number (1, 2, 3...)
- **Test Type:** Manual
- **Test Case Name:** {Format: TC{ID}_{Scenario name}_{LOB/Module}
- **Description:** {Clear description of the objective and what the test case validates}
- **Test steps:** {Single  step - one per row}
- **Expected Result:** {Expected result for the corresponding action - one per row}
- **Status:** Done / In Progress / Not Started
- **Components:** Middle Market
- **User Story:** CCI-101
- **Priority:** High / Medium / Low
- **Scenario Type:** Positive / Negative
**Navigation Requirements:**
### FNOL claim submission workflow
 
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

**Setup Requirements:**
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

 
#### Validation Requirements
 
**UI Element Validation:**
Validate as a First Notification of Loss (FNOL) Portal user, I want to view and manage work item cards categorized by their status: unassigned, assigned, processed, and unmatched. These cards should be visually distinct using color coding and appropriate spacing (margins). I want the ability to move assigned cards to the assigned tab and processed cards to the processed tab, making it easy to track and update the status of each work item efficiently.

In-Scope

Work Item Card UI:


Design and display cards for work items in four categories: Unassigned, Assigned, Processed, and Unmatched.

Visual color coding for each category (e.g.,light blue for unassigned, dark blue  for assigned, green for processed and so on )

Proper margins and spacing between cards for clarity and readability.

Tabs or Sections:

UI tabs or distinct sections for each status category.

Cards appear under their respective status tab/section.

Status Update:

Updating the card’s status when moved (e.g., from unassigned to assigned).


  
 
## Output Format: CSV Structure
 
Generate test cases in CSV format with the following columns:
 
**CSV Headers:**
```
TC ID,Test Type,Test Case Name,Test case Description,Test steps ,Expected Result,Status,Component,User Story,Priority,Scenario Type
```
 
**CSV Format Rules:**
1. **Each Step-Expected Result pair is a separate row**
2. **First row of each test case** contains:
   - TC ID (e.g., 1, 2, 3)
   - Test Type (Manual)
   - Test Case Name (full descriptive name)
   - Test case Description (objective of the test case)
   - Test steps: First  step (numbered as "1. ")
   - Expected Result: First Expected Result (numbered as "1. ")
   - Status
   - Components (Middle Market)
   - User Story ID
   - Priority
   - Scenario Type
3. Number actions sequentially (1., 2., 3., etc.)
4. Number expected results sequentially (1., 2., 3., etc.)
5. **CRITICAL:** Keep Action and Expected Result in SEPARATE columns - do NOT combine them

#### Scenario Coverage Rules
 
**Focus on Explicit Requirements:**
- Focus only on the specific functionality described in each scenario
- Generate **exactly one test case per scenario** as defined in the user story
- Invlude postive, Negative scenarios as defined in the user story only
- Include in scope considerations  
- Genearte atleast 20 to 30 test cases covering all scenarios 
- The number of test cases must match exactly the number of scenarios defined in the user story
 
**No Duplicate Test Cases:**
- Do not create duplicate test cases for the same scenario
- Do not create additional scenarios beyond what is defined in the user story
- Do not include steps/validations not explicitly mentioned in the user story or acceptance criteria

 
**Example CSV Rows (Multiple rows for one test case):**
```csv
1,Manual,TC01_All Work Items View - UI,Display all active work item for the logged in user,1. Login into FNOL portal,2. Navigate to the All Work Items section,3.Observe the list of work items displayed on the screen  Middle Market,CCI-101,High,Medium,Low,Positive/Negative
```
 
---
**CSV Formatting:**
- Ensure proper escaping of special characters
- Use double quotes for fields containing commas
- Use || as step separator and | as input/expected separator
- Keep formatting consistent across all test cases
 
---
 
## Example Test Case Generation
 
**Given User Story:**
```
This sub-screen contains those work items where no data could be extracted from the email contents and attachments. These work items are categorized with case status = Unmatched. They require manual review by the FNOL team member to determine the necessary course of action of the following:

Assign work item: Assigning the work item indicates that the work item is valid and should undergo human in the loop processing to become a claim. The work item would then appear under the assigned user's Assigned to Me tab
Terminate the work item: Terminating the work item indicates that the work item should not become a claim (e.g., in the case that an email unrelated to FNOL is received in the inbox). Once terminated, the work item would appear under the Processed tab.
Merge work item: Merging the work item indicates that the work item is related to an existing work item and the two should be consolidated. The work item would then be categorized/appear under the same tabs as the other work item.

Acceptance Criteria

GIVEN an FNOL Admin or FNOL Team Member signs in to the FNOL portal

WHEN the user navigates to the Unmatched Emails screen

THEN a list of work items appears where Case Status = Unmatched, indicating that GenAI was unable to match any email/attachment contents to the FNOL mandatory fields.Screen elements should align to Figma wireframes
```
 
**Generated CSV Output:**
```csv
TC ID,Test Type,Test Case Name,Description,Action,Expected Result,Test Repository Path,Status,Components,User Story,Priority,Scenario Type
1,Manual,"TC01_All Work Items View - UI,Display all active work item for the logged in user,1. Login into FNOL portal,2. Navigate to the All Work Items section,3.Observe the list of work items displayed on the screen  Middle Market,CCI-101,High,Medium,Low,Positive/Negative
``
---
 
## Execution Command
 
When ready to generate test cases, the system will:
1. Prompt user for input file path
2. Read and analyze the user story
3. Generate test cases following the template
4. Save as CSV in the specified location
5. Display confirmation with file path and test case count
 
---