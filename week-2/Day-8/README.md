# Day 8 - Lightning Web Components (LWC) Basics

## What is LWC?

Lightning Web Components (LWC) is Salesforce's modern UI development framework used to build fast, reusable, and scalable user interfaces.

LWC is based on modern web standards such as:

- HTML
- JavaScript
- CSS
- Web Components

Each Lightning Web Component consists of:

1. HTML File – Defines the UI structure
2. JavaScript File – Handles logic and functionality
3. Meta XML File – Defines component configuration and visibility

LWC helps developers create modular and reusable components that improve application maintainability and performance.

---

## Why Salesforce Uses LWC

Salesforce adopted Lightning Web Components because:

- Better performance
- Faster rendering
- Reusable UI architecture
- Easier maintenance
- Modern JavaScript support
- Improved developer experience
- Component-based development

Instead of building an entire page repeatedly, developers can create reusable components and use them across multiple pages.

Example:

A notification component can be reused in:

- Student Dashboard
- Faculty Dashboard
- Admin Dashboard

This reduces development time and improves consistency.

---

# UI Thinking Exercise

## College Management System - Required UI Screens

### 1. Student Registration Screen
Purpose:
- Register new students
- Store student details
- Generate student records

### 2. Student Dashboard
Purpose:
- View profile information
- Attendance summary
- Academic performance
- Notifications

### 3. Attendance Management Screen
Purpose:
- Track attendance
- View attendance reports
- Update attendance records

### 4. Faculty Panel
Purpose:
- Manage courses
- Upload marks
- Update attendance
- Communicate with students

### 5. Notifications Dashboard
Purpose:
- Display announcements
- Event updates
- Exam schedules
- Important alerts

---

# Component Thinking

## Selected Screen: Student Dashboard

### Reusable Components

### 1. Header Component
Functions:
- College logo
- Navigation menu
- User profile icon

Why reusable?
Can be used across all pages.

---

### 2. Student Information Component

Functions:
- Student ID
- Name
- Department
- Semester

Why reusable?
Can be displayed wherever student details are needed.

---

### 3. Attendance Component

Functions:
- Attendance percentage
- Subject-wise attendance

Why reusable?
Can be reused in dashboard and attendance pages.

---

### 4. Academic Performance Component

Functions:
- Marks
- GPA
- Progress chart

Why reusable?
Can be displayed in student and faculty views.

---

### 5. Notification Component

Functions:
- Announcements
- Alerts
- Reminders

Why reusable?
Can be reused throughout the system.

---

# Why Reusable Components are Useful

Reusable components provide:

- Faster development
- Reduced code duplication
- Easier maintenance
- Better consistency
- Improved scalability
- Better user experience

When one component is updated, all screens using that component automatically benefit from the update.

---

# Frontend vs Backend Thinking

| Functionality | Frontend (UI) | Backend (Apex) |
|--------------|--------------|----------------|
| Button Click | Yes | No |
| Form Display | Yes | No |
| Notification Display | Yes | No |
| Data Validation | Partial | Yes |
| Database Operations | No | Yes |
| Fee Calculation | No | Yes |
| Student Record Storage | No | Yes |
| Security Checks | No | Yes |
| Attendance Submission | UI sends request | Backend processes request |

### Frontend Responsibilities

- User interaction
- Form rendering
- Displaying notifications
- Showing data
- Input collection

### Backend Responsibilities

- Business logic
- Database operations
- Security enforcement
- Calculations
- Data processing

---

# Reflection

## Why do modern enterprise systems use component-based UI architecture?

Modern enterprise systems use component-based architecture because it improves scalability, maintainability, and development efficiency.

Benefits include:

- Reusable code
- Faster development cycles
- Consistent user experience
- Easier debugging
- Better team collaboration
- Simplified maintenance

Large applications may contain hundreds of screens. Component-based design allows developers to build small independent modules and reuse them throughout the system instead of rewriting the same code repeatedly.

This approach reduces complexity and makes enterprise applications easier to manage and expand over time.

---

# Revision Questions

### 1. What is a component?

A component is a reusable and independent UI building block that performs a specific function.

### 2. Why are reusable components useful?

They reduce code duplication, improve consistency, and speed up development.

### 3. What is the difference between frontend and backend?

Frontend handles user interaction and display, while backend handles business logic, data processing, and database operations.

### 4. Why did Salesforce move toward LWC?

To achieve better performance, modern development standards, and reusable component architecture.

### 5. Why is UI important in enterprise systems?

UI improves usability, productivity, and user experience.

### 6. Why should systems separate UI and business logic?

It improves maintainability, scalability, security, and code organization.

### 7. What security risks exist in enterprise applications?

- Unauthorized access
- Data breaches
- Data manipulation
- Weak authentication
- Poor access control

### 8. Why should developers think modularly?

Modular design makes applications easier to build, test, maintain, and scale.

---

# Day 8 Outcome

After completing Day 8, I learned:

- What Lightning Web Components (LWC) are
- Modern Salesforce UI architecture
- Component-based development
- Frontend and backend separation
- Importance of reusable UI components
- Basic enterprise application design principles
