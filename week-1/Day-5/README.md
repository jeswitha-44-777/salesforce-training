# Salesforce Summer Program – Day 5  
# Apex Introduction & Trigger Development

---

# Objective

The goal of Day 5 was to understand:
- What Apex is
- Why Salesforce requires programming
- Difference between declarative and programmatic development
- Basic Apex syntax and logic
- How Apex supports enterprise business logic

---

# What is Apex?

Apex is Salesforce’s proprietary programming language used to build custom business logic on the Salesforce Platform.

It is:
- Object-oriented
- Strongly typed
- Similar to Java

Apex helps developers:
- Automate business processes
- Create triggers
- Build custom validations
- Integrate external systems
- Process bulk records efficiently

---

# Why Apex is Needed

Salesforce provides no-code tools like:
- Flow
- Validation Rules
- Process Builder

However, enterprise applications often require:
- Complex calculations
- Custom workflows
- External API integrations
- Advanced validations
- Bulk data processing

These requirements are handled using Apex.

---

# Difference Between Flow and Apex

| Feature | Flow | Apex |
|---|---|---|
| Development Type | Declarative | Programmatic |
| Coding Required | No | Yes |
| Complexity Handling | Moderate | High |
| Performance | Medium | High |
| Flexibility | Limited | Very Flexible |
| Best For | Simple automation | Complex business logic |

---

# Difference Between Configuration and Coding

| Configuration | Coding |
|---|---|
| Click-based setup | Code-based setup |
| Easy to maintain | Highly customizable |
| Best for admins | Best for developers |
| Limited complexity | Handles advanced logic |
| Faster implementation | Greater flexibility |

---

# Real Examples Where Apex is Needed

## 1. Complex Fee Calculation
A university system may require fee calculations based on:
- Attendance
- Scholarship
- Hostel fees
- Course type

This becomes difficult using only Flow.

---

## 2. External Payment Integration
Salesforce may need integration with:
- Razorpay
- Stripe
- PayPal

Apex is required for:
- API calls
- Response handling
- Secure processing

---

## 3. Advanced Eligibility Logic
Example:
A student can register only if:
- Attendance > 75%
- Fees are cleared
- GPA > 6
- Seats are available

Such multi-condition logic is easier in Apex.

---

# College Management System Design

## CRM Usage
Salesforce acts as a CRM to manage:
- Students
- Faculty
- Admissions
- Courses
- Fees

---

# Objects Used

| Object | Purpose |
|---|---|
| Student | Stores student details |
| Course | Stores course information |
| Faculty | Stores faculty data |
| Admission | Tracks admissions |
| Fee | Stores payment information |

---

# Relationships

| Relationship | Description |
|---|---|
| Student ↔ Course | Students enroll in courses |
| Faculty ↔ Course | Faculty teaches courses |
| Student ↔ Fee | Students pay fees |

---

# Validation Rules

Examples:
- Email cannot be blank
- Attendance cannot exceed 100%
- GPA must remain between 0–10

---

# Flow Usage

Flows were used for:
- Notifications
- Record updates
- Admission automation
- Follow-up task creation

---

# Apex Usage

Apex was used for:
- Complex business logic
- Trigger automation
- Eligibility checks
- Backend processing

---

# Practical Implementation

## Apex Trigger Development

Created:
- AccountTriggerHandler
- AccountTrigger
- AccountTriggerTest

Purpose:
Automatically copy BillingState into ShippingState before inserting Account records.

---

# Trigger Logic

```apex
acc.ShippingState = acc.BillingState;
```

---

# Trigger Flow

1. User inserts Account record
2. Trigger executes before insert
3. Handler class updates ShippingState
4. Record gets saved

---

# Test Class Implementation

The test class:
- Inserts 200 Account records
- Sets BillingState = CA
- Verifies ShippingState = CA
- Validates trigger functionality

---

# Pseudocode Examples

## Example 1

```text
IF seats are full
THEN block registration
```

---

## Example 2

```text
IF attendance < 75%
THEN notify student
```

---

## Example 3

```text
IF fee is unpaid
THEN prevent exam registration
```

---

# Reflection

## Why Enterprise Systems Need Programming

Enterprise systems contain:
- Complex workflows
- Large-scale automation
- Security requirements
- Real-time integrations
- Custom business rules

No-code tools are powerful, but eventually:
- Logic becomes complex
- Performance becomes critical
- Full customization becomes necessary

Apex provides:
- Flexibility
- Scalability
- Better control
- Advanced automation

---

# Key Learnings

- Apex extends Salesforce capabilities
- Triggers automate backend logic
- Test classes validate reliability
- Business logic is critical in enterprise applications
- Declarative and programmatic tools work together

---

# Screenshots

Add screenshots inside:

```text
/day5-apex-introduction/screenshots/
```

Include:
- AccountTriggerHandler
- AccountTrigger
- AccountTriggerTest

---

# Folder Structure

```text
/day5-apex-introduction
│
├── README.md
├── tasks.md
└── screenshots/
    ├── AccountTriggerHandler.png
    ├── AccountTrigger.png
    └── AccountTriggerTest.png
```
