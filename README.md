# 🛡️ Multi-Line Insurance Policy and Claims Management System

## 📌 Project Overview

The **Multi-Line Insurance Policy and Claims Management System** is a Salesforce-based application designed to manage multiple insurance products through a centralized platform.

The system supports **Auto, Property, and Life Insurance** and automates the complete workflow from policy quotation and premium calculation to claim creation, claim routing, claims management, and high-value claim approval.

This project was developed as a **team project by three members** using Salesforce CRM capabilities, automation tools, Apex, and Lightning Web Components.

---

## 🎯 Project Objectives

- Manage multiple insurance policy types in a single Salesforce platform.
- Automate the insurance quotation process.
- Calculate policy premiums automatically.
- Validate important policy information.
- Automatically route claims to the appropriate teams.
- Provide a centralized dashboard for Claims Adjusters.
- Automate high-value claim approval.
- Implement role-based access using Permission Sets.
- Reduce manual processing and improve data consistency.

---

## 🚀 Key Features

### 1. Multi-Line Insurance Management

The system supports three major insurance types:

- 🚗 Auto Insurance
- 🏠 Property Insurance
- ❤️ Life Insurance

Salesforce **Record Types** are used to manage the different insurance products within the Policy object.

---

### 2. Auto Quoting

A **Screen Flow** guides users through the Auto Insurance quotation process.

The flow collects:

- Customer
- Policy Start Date
- Policy State
- VIN
- Model Year

After completing the flow, the Auto Policy record is created automatically.

---

### 3. VIN Validation

A Salesforce **Validation Rule** ensures that the Vehicle Identification Number contains exactly 17 characters.

This prevents invalid vehicle information from being entered into the system.

---

### 4. Automatic Premium Calculation

The project uses an **Apex class named `PremiumCalculator`** to calculate the Auto Policy premium.

The Auto Quoting Flow invokes the Apex logic and updates the calculated premium in the Policy record.

This eliminates the need for manual premium calculation.

---

### 5. Automated Claim Routing

When a Claim is created, a **Record-Triggered Flow** identifies the related Policy Type.

The claim is automatically routed to the appropriate queue:

| Policy Type | Claim Queue |
|---|---|
| Auto | Auto Claims Queue |
| Property | Property Claims Queue |
| Life | Life Claims Queue |

This reduces manual claim assignment.

---

### 6. Claims Adjuster Dashboard

A custom **Lightning Web Component (LWC)** provides a centralized Claims Adjuster Dashboard.

The dashboard displays information such as:

- Claim Number
- Policy Type
- Policy Holder
- Claim Amount
- Approval Status
- Days Open

Claims can also be filtered by:

- All
- Auto
- Property
- Life

---

### 7. High-Value Claim Approval

Claims with an amount greater than **$50,000** are automatically submitted for approval.

The approval workflow consists of:

```text
Claim Created
      ↓
Claim Amount > $50,000
      ↓
Automatic Submission
      ↓
Senior Adjuster
      ↓
Department Manager
      ↓
Final Approval
      ↓
Claim Status = Approved
```

This provides a controlled multi-level approval process for high-value claims.

---

### 8. Approve / Reject Claim

A Screen Flow allows authorized users to process claims directly from the Claim record.

The approver can:

- Review claim information
- Select Approve or Reject
- Enter comments
- Process the claim

---

### 9. Role-Based Security

The project uses Salesforce **Permission Sets** to provide access according to user responsibilities.

Implemented access levels include:

- **Insurance Agent Access**
- **Claims Adjuster Access**
- **Claims Manager Access**

---

# 🛠️ Technologies Used

### Salesforce

- Salesforce Lightning
- Salesforce Objects
- Record Types
- Record-Triggered Flows
- Screen Flows
- Approval Processes
- Validation Rules
- Permission Sets
- Queues

### Development

- Apex
- SOQL
- Lightning Web Components
- JavaScript
- HTML
- CSS

---

# 🔄 Complete System Workflow

```text
Customer
   ↓
Policy Creation
   ↓
Select Insurance Type
   ↓
Auto / Property / Life
   ↓
Auto Quotation Flow
   ↓
VIN Validation
   ↓
Premium Calculation
   ↓
Policy Created
   ↓
Claim Creation
   ↓
Automatic Claim Routing
   ↓
Claims Adjuster Dashboard
   ↓
Claim Review
   ↓
Claim Amount > $50,000?
   ↓
Approval Process
   ↓
Senior Adjuster
   ↓
Department Manager
   ↓
Final Approval
```

---

# 📊 Salesforce Components

| Component | Purpose |
|---|---|
| Policy Object | Stores insurance policy information |
| Claim Object | Stores claim information |
| Record Types | Separates Auto, Property and Life policies |
| Screen Flow | Automates Auto quotation |
| Record-Triggered Flow | Automates claim routing |
| Apex | Calculates premium and retrieves claim data |
| Lightning Web Components | Provides Claims Adjuster Dashboard |
| Validation Rule | Validates VIN |
| Approval Process | Handles high-value claims |
| Permission Sets | Provides role-based access |
| Queues | Routes claims to appropriate teams |

---

# 👥 Team Members

This project was developed collaboratively by a team of three members.

### Team Member 1
**MUTHAMILSELVAN T**  
B.E. Computer Science and Engineering

**Primary Contributions:**
- Salesforce project design
- Policy and Auto Quoting workflow
- Flow automation
- Premium calculation integration
- Testing and documentation

### Team Member 2
**BHUVANESH C T**
B.E. Computer Science and Engineering

**Primary Contributions:**
- Claims Management
- Claim routing automation
- Approval Process
- Claims workflow testing

### Team Member 3
**HARIHARAN R**
B.E. Computer Science and Engineering

**Primary Contributions:**
- Lightning Web Components
- Claims Adjuster Dashboard
- User interface
- Permission Sets and security

> Update the names and contribution areas according to the actual work performed by each team member.

---

# 📈 Project Updates / Development Progress

## ✅ Phase 1 — Salesforce Setup
- Created Salesforce application
- Created required objects and fields
- Configured relationships
- Created Policy and Claim data model

## ✅ Phase 2 — Insurance Policy Management
- Implemented Auto, Property and Life Record Types
- Configured policy-specific fields
- Created Auto Quoting Screen Flow

## ✅ Phase 3 — Validation & Premium Automation
- Implemented VIN Validation Rule
- Developed `PremiumCalculator` Apex class
- Integrated Apex with Auto Quoting Flow
- Automated premium calculation

## ✅ Phase 4 — Claims Management
- Implemented Claim creation
- Developed automatic claim routing
- Configured Auto, Property and Life claim queues

## ✅ Phase 5 — Claims Dashboard
- Developed Claims Adjuster Dashboard
- Implemented Apex controller
- Created reusable claim display components
- Added policy-type filtering

## ✅ Phase 6 — Approval Automation
- Configured High-Value Claim Approval Process
- Implemented automatic submission for claims above $50,000
- Configured Senior Adjuster approval
- Configured Department Manager approval
- Implemented final approval status update

## ✅ Phase 7 — Security
- Created Insurance Agent Permission Set
- Created Claims Adjuster Permission Set
- Created Claims Manager Permission Set
- Configured role-based access

## ✅ Phase 8 — Testing & Demonstration
- Tested policy creation
- Tested VIN validation
- Tested premium calculation
- Tested claim routing
- Tested dashboard filtering
- Tested high-value claim approval workflow
- Completed Salesforce project demonstration

---

# 🧪 Testing Scenarios

| Test Case | Expected Result |
|---|---|
| Create Auto Policy | Policy created successfully |
| Enter invalid VIN | Validation error displayed |
| Complete Auto Quotation | Policy created with premium |
| Create Auto Claim | Claim routed to Auto Queue |
| Create Property Claim | Claim routed to Property Queue |
| Create Life Claim | Claim routed to Life Queue |
| Claim > $50,000 | Approval automatically submitted |
| Senior Adjuster Approval | Claim moves to next stage |
| Manager Approval | Claim becomes Approved |
| Dashboard Filter | Relevant claims displayed |

---

# 🎓 Learning Outcomes

Through this project, the team gained practical experience in:

- Salesforce CRM development
- Salesforce Flow automation
- Apex programming
- SOQL
- Lightning Web Components
- Salesforce Approval Processes
- Validation Rules
- Permission Sets
- Queue-based record assignment
- Salesforce data modeling
- Role-based security
- End-to-end business process automation

---

# 📌 Future Enhancements

Potential future improvements include:

- Email and SMS notifications
- Customer self-service portal
- Advanced analytics and reporting
- AI-based claim risk assessment
- Automated document verification
- Mobile-friendly claims processing
- Integration with external insurance systems

---

# 🏆 Project Status

**Status: ✅ Completed**

The project successfully demonstrates an end-to-end Salesforce insurance management workflow covering policy creation, quotation, premium calculation, claim management, automated routing, dashboard visualization, and multi-level claim approval.

---

## 👨‍💻 Project Type

**Salesforce CRM / Insurance Management System**

**Team Size:** 3 Members

**Platform:** Salesforce

**Project Status:** Completed
