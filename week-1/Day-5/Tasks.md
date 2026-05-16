# Day 5 Tasks – Apex Introduction

---

# Completed Trailhead Modules

## 1. Apex & .NET Basics

Topics Learned:
- What is Apex
- Variables
- Conditional Statements
- Loops
- Classes
- Basic Syntax

---

## 2. Apex Basics & Database

Topics Learned:
- SOQL Queries
- DML Operations
- Triggers
- Collections
- Data Manipulation
- Exception Handling

---

# Practical Work Completed

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

# Trigger Working Process

1. User inserts Account record
2. Trigger fires before insert
3. Trigger calls handler class
4. ShippingState gets updated
5. Record is saved

---

# Test Class Validation

Test class inserted:
- 200 Account records

Verified:
- BillingState = CA
- ShippingState = CA

Purpose:
To ensure trigger works correctly for bulk records.

---

# Business Understanding

Learned:
- Difference between declarative and programmatic development
- Why Apex is important
- How business logic works in Salesforce
- How triggers automate backend processes

---

# Real Business Examples

## Example 1
Complex student fee calculation system

## Example 2
External payment gateway integration

## Example 3
Advanced student eligibility verification

---

# Pseudocode Practice

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
IF fees are pending
THEN prevent exam registration
```

---

# Reflection

Programming becomes necessary when:
- Logic becomes complex
- Large-scale automation is required
- External integrations are needed
- Business requirements become advanced

Apex provides:
- Flexibility
- Scalability
- Customization
- Better automation control

---

# Key Learnings

- Apex extends Salesforce functionality
- Triggers automate backend processes
- Test classes improve reliability
- Enterprise systems require programming
- Business logic is critical in CRM systems

---

# Screenshots Added

Screenshots included:
- AccountTriggerHandler
- AccountTrigger
- AccountTriggerTest

Stored inside:
```text
/day5-apex-introduction/screenshots/
```
