
# Day 9 - LWC Communication & Application Architecture

## 📌 Objective

The goal of Day 9 was to understand how Lightning Web Components (LWC) communicate with each other, how data flows inside Salesforce applications, and why modular architecture is important in enterprise systems.

---

# 🔹 Component Communication in LWC

Component communication allows multiple components to work together and share data efficiently.

## Types of Communication

### 1. Parent to Child Communication

* Data is passed using `@api`
* Parent component controls child component behavior

Example:

```js
@api studentName;
```

### 2. Child to Parent Communication

* Uses Custom Events
* Child component sends information to parent

Example:

```js
this.dispatchEvent(new CustomEvent('save'));
```

### 3. Unrelated Component Communication

* Uses Pub/Sub or Lightning Message Service
* Components communicate without direct relationship

---

# 🔹 Dashboard Design

## Student Dashboard

Features:

* View courses
* Attendance status
* Notifications
* Assignment tracking

Components:

* StudentProfile
* AttendanceCard
* CourseList
* NotificationPanel

## Faculty Dashboard

Features:

* Manage attendance
* Upload marks
* Course management

Components:

* FacultyProfile
* StudentTable
* AttendanceManager

## Admin Dashboard

Features:

* User management
* Reports
* Course allocation
* System monitoring

Components:

* UserManagement
* AnalyticsPanel
* CourseAllocation

---

# 🔹 Component Communication Example

| Sender Component  | Receiver Component | Purpose           |
| ----------------- | ------------------ | ----------------- |
| StudentForm       | StudentDashboard   | Pass student data |
| AttendanceManager | StudentTable       | Update attendance |
| AdminPanel        | AnalyticsPanel     | Send report data  |

---

# 🔹 Data Flow Explanation

## Example: Student Registration Process

### Step-by-Step Flow

### 1. UI Layer

Student enters:

* Name
* Email
* Course details

### 2. Validation

System checks:

* Required fields
* Valid email format
* Duplicate records

### 3. Flow

Salesforce Flow automates:

* Record creation
* Approval process
* Email trigger

### 4. Apex Layer

Apex handles:

* Complex business logic
* Server-side processing
* Data manipulation

### 5. Database

Data gets stored inside Salesforce Objects.

### 6. Notification

Confirmation email or success message is sent to the user.

---

# 🔹 Aura vs LWC

| Aura Components      | Lightning Web Components |
| -------------------- | ------------------------ |
| Older framework      | Modern framework         |
| Slower performance   | Faster performance       |
| Complex architecture | Simple architecture      |
| Custom framework     | Based on Web Standards   |
| More code required   | Cleaner reusable code    |

## Why Salesforce Moved to LWC

Salesforce adopted LWC because:

* Better performance
* Faster rendering
* Modern JavaScript support
* Improved developer experience
* Easier maintenance
* Reusable modular components

---

# 🔹 Reflection

## Why Enterprise Applications Need Modular Architecture

Large enterprise systems are divided into modules because:

* Easier maintenance
* Better scalability
* Reusable components
* Faster development
* Independent testing
* Improved collaboration among teams

Without modular architecture, systems become tightly coupled and difficult to manage.

---

# 🔹 Revision Questions

### 1. Why do components communicate?

Components communicate to share data and coordinate application behavior.

### 2. Difference between parent-child communication and events?

* Parent-child communication passes data directly.
* Events are used to notify other components about actions.

### 3. Why is modular architecture useful?

It improves scalability, maintainability, and code reusability.

### 4. Why did Salesforce move toward LWC?

For better performance, modern standards, and improved development experience.

### 5. What problems happen in tightly coupled systems?

* Difficult maintenance
* Poor scalability
* Hard debugging
* Low reusability

### 6. Why is frontend architecture important?

It helps organize UI components and improves user experience.

### 7. Why should UI and backend remain separate?

To improve flexibility, scalability, and maintainability.

### 8. Why do large systems need reusable modules?

Reusable modules reduce development time and improve consistency.

---

# ✅ Day 9 Outcome

By completing Day 9, I learned:

* LWC component communication
* Event-driven architecture
* Salesforce data flow
* Modular enterprise design
* Differences between Aura and LWC
* Importance of modern frontend architecture
