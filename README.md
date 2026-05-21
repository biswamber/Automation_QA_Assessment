

## Candidate Name
Biswamber Behera

## Task 1: QA Testing Report

### Overview
For Task 1, I tested the assigned web application and prepared a detailed QA report. The testing covered UI/UX issues, spelling and content issues, broken links, button functionality, responsiveness, form validation, and overall user experience.

### Deliverables
- Task1_QA_Report_BiswamberBehera.pdf
- Screenshots of identified bugs/issues

### Testing Areas Covered
- UI and layout consistency
- Button and link functionality
- Spelling and grammar
- Responsiveness
- Form validation
- Navigation flow
- Visual bugs
- User experience issues

---

## Task 2: n8n API Integration Workflow

### Workflow Name
GitHub Morning Brief Workflow

### Overview
For Task 2, I created an n8n workflow that uses a scheduled trigger, integrates with the GitHub API, transforms API data, enriches the data with a second API call, applies conditional logic, and sends the final output to Telegram.

### APIs Used
1. GitHub Search Repositories API  
   `https://api.github.com/search/repositories?q=automation+testing&sort=stars&order=desc&per_page=10`

2. GitHub Repository Details API  
   The workflow uses the selected repository API URL from the first API response.

### Workflow Steps
1. Schedule Trigger runs every 1 hour.
2. First HTTP Request searches GitHub repositories related to automation testing.
3. IF node checks whether the first API request failed.
4. Code node transforms the response and keeps the top 5 repositories.
5. Second HTTP Request fetches detailed data for the top repository.
6. IF node checks whether the second API request failed.
7. Code node creates a digest message.
8. IF node checks whether the repository has more than 1000 stars.
9. Telegram node sends either a high-priority or normal-priority digest.
10. Error branches send Telegram alerts if API calls fail.

### Error Handling
Both API calls include error-checking branches. If an API request fails, the workflow creates an error message and sends a Telegram alert instead of failing silently.

### Credentials
Telegram bot credentials are stored securely in n8n Credentials and are not hard-coded in the workflow.

### Deliverables
- Task2_Workflow_BiswamberBehera.json
- screenshots/task2_workflow_canvas.png
- screenshots/task2_success_execution.png
