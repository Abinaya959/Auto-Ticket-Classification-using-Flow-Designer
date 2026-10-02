# 🎫 Auto Ticket Classification using Flow Designer

## 📌 Project Overview

**Auto Ticket Classification using Flow Designer** is a ServiceNow-based automation project designed to simplify IT helpdesk ticket management.

In a school environment, the IT helpdesk receives various incidents, such as Wi-Fi connectivity problems, projector issues, password/login problems, and slow computers. Manually classifying these tickets takes time and may result in inconsistent categorization.

This project uses **ServiceNow Flow Designer** to automatically classify newly created tickets based on predefined keywords in the ticket's Short Description and Description fields. It assigns the appropriate Category and Subcategory and supports automated email notifications to the caller.

## 🎯 Objectives

- Automate IT helpdesk ticket classification.
- Reduce manual effort in ticket categorization.
- Improve consistency in Category and Subcategory assignment.
- Use ServiceNow Flow Designer to implement no-code/low-code automation.
- Maintain structured ticket information.
- Notify callers through automated email notifications.

## ✨ Features

- **Automatic Ticket Classification:** Classifies tickets when new records are created.
- **Keyword-Based Detection:** Identifies issue types using predefined keywords.
- **Category and Subcategory Assignment:** Automatically assigns the appropriate values.
- **Dependent Choice Configuration:** Maintains valid Category and Subcategory combinations.
- **Email Notifications:** Sends notifications to callers after ticket processing.
- **Structured Ticket Management:** Stores ticket details in a custom ServiceNow table.
- **Maintainable Workflow:** Classification conditions can be modified or extended in Flow Designer.

## 🛠️ Technology Stack

| Technology | Purpose |
|---|---|
| ServiceNow | Platform for managing IT helpdesk tickets |
| Flow Designer | Automates ticket classification and notifications |
| Incident WorkFlow Table | Stores ticket details |
| ServiceNow Choice Fields | Defines Category and Subcategory options |
| Email Notification Action | Sends notifications to callers |

## ⚙️ Ticket Classification Logic

The system uses predefined keywords to identify common IT support issues.

| Keywords / Issue | Category | Subcategory |
|---|---|---|
| Wi-Fi / WiFi | Network | Wi-Fi |
| Projector | Hardware | Projector |
| Password / Login | Access | Forgot Password |
| Slow / Hanging | Performance | Slow Computer |

### Classification Workflow

1. A user or support staff member creates a new IT helpdesk ticket.
2. The ticket is stored in the `Incident WorkFlow` table.
3. ServiceNow Flow Designer triggers when the new record is created.
4. The flow checks whether the Category field is empty.
5. Predefined keyword conditions evaluate the ticket description.
6. The matching Category and Subcategory are assigned.
7. An email notification is sent to the caller when configured.
8. The classified ticket is available for further processing.

## 🗂️ Ticket Information

The custom `Incident WorkFlow` table contains the following fields:

| Field | Description |
|---|---|
| Number | Unique ticket number |
| Caller | Person who reported the issue |
| Category | Main classification of the ticket |
| Subcategory | Specific type of issue |
| Short Description | Brief summary of the incident |
| Description | Detailed explanation of the issue |
| State | Current status of the ticket |
| Assigned Group | Support group responsible for the ticket |
| Assigned To | Individual assigned to handle the ticket |

## 🏗️ System Architecture

The project consists of three main components:

### 1. User Interface
The ServiceNow ticket form allows users or support staff to create tickets and enter issue details.

### 2. Data Layer
The custom `Incident WorkFlow` table stores ticket details, classification fields, and assignment information.

### 3. Automation Layer
ServiceNow Flow Designer processes newly created records, evaluates keyword conditions, assigns the relevant Category and Subcategory, and triggers email notifications.

**Workflow:**

`Ticket Creation → Flow Designer Trigger → Keyword Evaluation → Category/Subcategory Assignment → Email Notification`

## 🚀 Setup and Configuration

This project runs within a ServiceNow instance. It does not require a separate MERN application or `npm start` commands.

### Prerequisites

- Access to a ServiceNow instance.
- Permission to create or configure tables and fields.
- Access to ServiceNow Flow Designer.
- A valid caller record for testing.
- Email notification configuration, if notification testing is required.

### Configuration Steps

1. Log in to your authorized ServiceNow instance.
2. Create or configure the custom `Incident WorkFlow` table.
3. Configure the required ticket fields.
4. Set up Category and Subcategory choice values.
5. Configure the dependent-choice relationships.
6. Open Flow Designer and create a new flow.
7. Configure the trigger to run when a new ticket record is created.
8. Add conditions to check the ticket description for supported keywords.
9. Configure the corresponding Category and Subcategory field updates.
10. Add the email notification action.
11. Save and activate the flow.
12. Create test tickets to verify the classification logic.

> **Note:** Exact navigation and configuration options may vary depending on your ServiceNow version and access permissions.

## 🧪 Testing

The project can be validated using the following test scenarios:

| Test Case | Input / Scenario | Expected Result |
|---|---|---|
| TC-001 | Create a new ticket | Ticket is created successfully |
| TC-002 | Wi-Fi-related issue | Network → Wi-Fi |
| TC-003 | Projector-related issue | Hardware → Projector |
| TC-004 | Password/Login issue | Access → Forgot Password |
| TC-005 | Slow/Hanging computer issue | Performance → Slow Computer |
| TC-006 | Ticket with a valid caller email | Email notification is triggered |
| TC-007 | Unsupported keyword | No incorrect classification should be assigned |
| TC-008 | Multiple tickets with different keywords | Each ticket is classified according to its matching condition |

### Testing Approach

- Functional testing
- Performance testing
- Data validation
- Multiple-ticket processing
- User Acceptance Testing (UAT)

Since this project uses predefined keyword conditions rather than a trained machine-learning model, traditional training accuracy, validation accuracy, and model confidence scores are not applicable.

## 📸 Screenshots

Add screenshots of your implementation to a folder named `screenshots/` in the repository.

Recommended screenshots include:

- Incident WorkFlow table and ticket form
- Category and Subcategory configuration
- Flow Designer trigger
- Keyword-based classification branches
- Example classified Wi-Fi ticket
- Example classified Projector ticket
- Example classified Password/Login ticket
- Example classified Slow/Hanging ticket
- Email notification output

Example Markdown for displaying a screenshot:

```markdown
![Flow Designer Workflow](screenshots/flow-designer.png)
```

Replace the example image path with the actual path of your screenshot.

## 📊 Expected Results

The automation is designed to:

- Classify supported IT helpdesk tickets automatically.
- Assign the correct Category and Subcategory based on configured keywords.
- Reduce repetitive manual categorization.
- Maintain structured ticket information.
- Trigger email notifications when configured.
- Support future changes through Flow Designer.

Actual results should be confirmed by executing the test cases in the ServiceNow instance.

## ✅ Advantages

- Reduces manual classification effort.
- Improves consistency in ticket categorization.
- Supports faster ticket processing.
- Uses low-code/no-code workflow automation.
- Makes classification rules easier to maintain.
- Can be extended to support additional ticket types.

## ⚠️ Limitations

- Classification depends on predefined keywords.
- Unrecognized wording may not match an existing condition.
- Tickets containing multiple unrelated issues may require additional rules.
- The system does not learn automatically from previous tickets.
- Correct operation depends on proper ServiceNow configuration.

## 🔮 Future Enhancements

- Add more IT support categories and subcategories.
- Expand keyword conditions to cover more variations of user descriptions.
- Implement automatic assignment to specific support groups.
- Add priority-based ticket routing.
- Configure escalation rules for unresolved incidents.
- Introduce dashboards and reports for ticket analysis.
- Explore AI/ML-based classification as a future enhancement.

## 👥 Team Members

| Team Member | Role |
|---|---|
| Member 1 | Project Lead & ServiceNow Developer |
| Member 2 | Business Analyst & Configuration Developer |
| Member 3 | Testing & Documentation Analyst |

Replace the member labels with the actual team members' names.

## 📚 Project Documentation

The project documentation covers:

- Project Overview
- Problem Statement
- Empathy Map and Brainstorming
- Requirement Analysis
- Customer Journey Map
- Data Flow Diagram
- Solution Architecture
- Project Planning and Sprint Scheduling
- Functional and Performance Testing
- User Acceptance Testing
- Results and Screenshots
- Advantages and Disadvantages
- Conclusion and Future Scope

## 🏁 Conclusion

The **Auto Ticket Classification using Flow Designer** project demonstrates how ServiceNow workflow automation can simplify IT helpdesk ticket management.

By using predefined keyword conditions, the system automatically assigns Category and Subcategory values to supported incidents and can notify callers through email. The solution reduces repetitive manual work and provides a maintainable foundation for expanding IT support automation.

---

**Project Name:** Auto Ticket Classification using Flow Designer  
**Platform:** ServiceNow  
**Automation Tool:** Flow Designer  
**Project Type:** IT Helpdesk Automation
