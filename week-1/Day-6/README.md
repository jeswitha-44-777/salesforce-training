# Salesforce Summer Program – Day 6  
# SOQL & Apex Triggers

---

# Objective

The goal of Day 6 was to understand:
- How Salesforce stores and retrieves data
- What SOQL is
- What Apex Triggers are
- Difference between Flow and Trigger
- Event-driven automation in enterprise systems

---

# What is SOQL?

SOQL (Salesforce Object Query Language) is used to retrieve data from Salesforce objects.

It is similar to SQL but designed specifically for Salesforce objects and relationships.

SOQL is used to:
- Fetch records
- Filter records
- Query related objects
- Retrieve business data efficiently

---

# Example SOQL Query

```sql
SELECT Id, Name FROM Account
```

This query retrieves:
- Account Id
- Account Name

---

# What is SOSL?

SOSL (Salesforce Object Search Language) is used for searching text across multiple objects.

Example:
```sql
FIND {'Smith'} IN ALL FIELDS RETURNING Contact(Name), Lead(Name)
```

---

# What is an Apex Trigger?

An Apex Trigger is code that automatically executes when specific events occur in Salesforce.

Triggers respond to events like:
- before insert
- after insert
- before update
- after update
- before delete
- after delete

Triggers automate backend business logic.

---

# Difference Between Flow and Trigger

| Feature | Flow | Apex Trigger |
|---|---|---|
| Type | Declarative | Programmatic |
| Coding Needed | No | Yes |
| Complexity Handling | Medium | High |
| Best For | Simple automation | Advanced logic |
| Performance | Moderate | High |
| Flexibility | Limited | Very Flexible |

---

# Difference Between Before and After Trigger

| Before Trigger | After Trigger |
|---|---|
| Executes before saving record | Executes after saving record |
| Used for validation and updating fields | Used for related records/actions |
| Faster | Accesses record IDs |
| No DML usually needed | Often performs DML operations |

---

# Practical Trigger Implementations

## 1. AccountAddressTrigger

Purpose:
Automatically copies Billing Postal Code into Shipping Postal Code when:
```text
Match Billing Address = true
```

---

# Trigger Logic

```apex
trigger AccountAddressTrigger on Account (before insert, before update) {

    for(Account acc : Trigger.new) {

        if(acc.Match_Billing_Address__c == true) {

            acc.ShippingPostalCode = acc.BillingPostalCode;
        }
    }
}
```

---

# Working Process

1. User inserts or updates Account
2. Trigger executes automatically
3. Checks Match Billing Address checkbox
4. Copies BillingPostalCode into ShippingPostalCode
5. Record gets saved

---

# 2. ClosedOpportunityTrigger

Purpose:
Automatically creates a follow-up task when Opportunity stage becomes:
```text
Closed Won
```

---

# Trigger Logic

```apex
trigger ClosedOpportunityTrigger on Opportunity (after insert, after update) {

    List<Task> taskList = new List<Task>();

    for(Opportunity opp : Trigger.new) {

        if(opp.StageName == 'Closed Won') {

            Task t = new Task(
                Subject = 'Follow Up Test Task',
                WhatId = opp.Id
            );

            taskList.add(t);
        }
    }

    if(!taskList.isEmpty()) {
        insert taskList;
    }
}
```

---

# Why This Trigger is Bulkified

The trigger:
- Processes all records using loops
- Uses collections
- Performs only one DML operation

This allows handling:
```text
200+ Opportunity records
```

efficiently without governor limit issues.

---

# Trigger Use Cases

## 1. Student Registration
After registration:
- Send welcome email

---

## 2. Course Capacity
After course becomes full:
- Notify faculty automatically

---

## 3. Attendance Monitoring
If attendance drops below 75%:
- Send warning notification

---

## 4. Fee Payment
After successful payment:
- Generate receipt automatically

---

## 5. Exam Eligibility
If student becomes eligible:
- Unlock exam registration

---

# Query Thinking Examples

## Example 1
```text
Find all students in Course A
```

---

## Example 2
```text
Find all courses handled by Faculty X
```

---

## Example 3
```text
Find students with attendance below 75%
```

---

## Example 4
```text
Find students with pending fees
```

---

## Example 5
```text
Find courses with available seats
```

---

# Reflection

## Why Enterprise Systems Need Event-Driven Behavior

Enterprise systems must react automatically to:
- User actions
- Database changes
- Real-time updates
- Business events

Triggers help systems:
- Reduce manual work
- Improve automation
- Maintain consistency
- Handle real-time business processes

---

# Reflective Answers

## Why do systems need triggers?
Triggers automate actions whenever data changes occur.

---

## Difference between polling and event-driven systems?

| Polling | Event-Driven |
|---|---|
| Constantly checks for updates | Reacts only when event occurs |
| Slower | Faster |
| More resource usage | Efficient |

---

## Why are database queries important?
Queries help retrieve and process business data efficiently.

---

## When should Flows be preferred over Triggers?
Flows should be preferred for:
- Simple automation
- Notifications
- Record updates

---

## What problems happen if automation becomes too complex?
- Maintenance difficulty
- Performance issues
- Debugging complexity

---

## Why should developers think carefully before automation?
Bad automation can:
- Create duplicate processes
- Cause recursion
- Reduce performance

---

# Key Learnings

- SOQL retrieves Salesforce data
- SOSL performs text searches
- Triggers automate event-driven logic
- Before and After triggers serve different purposes
- Bulkification is important for scalability
- Enterprise systems react automatically to data changes

---

# Reference

Day 6 concepts were based on:
- SOQL
- SOSL
- DML Operations
- Apex Triggers
- Event-driven automation concepts from the Salesforce Summer Program Day 6 guide :contentReference[oaicite:0]{index=0}
