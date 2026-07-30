# Activity 1: App Concept and API Proposal

**PROG7314 | Group Worksheet | Maximum 4 students**

## 1. Group and concept

**Group members and student numbers:** 

Yash Dhurumraj (ST10266783)

Heinrich Russouw (ST10434056)

Prean Govender (ST10447995)

Nosipho Buhlebemvelo Khubeka (ST10083146)

**Working app name:**

**CampusTask**


**Problem to be solved:**  


**Students often have assignments, tests and project deadlines spread across different learning platforms, group chats and documents. This makes it easy to overlook important work or submit tasks late.**


**Target users:**  

South African university and college students who need a simple way to organise their academic responsibilities.



## 2. Proposed mobile solution

**Core solution:** CampusTask allows students to create modules, record assignments and tests, set deadlines, receive reminders and mark work as completed.  

**Why Android?** A native Android application provides access to push notifications, biometric authentication, offline storage, background synchronisation and device language settings. Students generally keep their phones nearby, making a mobile reminder system more practical than a desktop-only solution. 

**Positive impact:** The app can help students plan their workload, reduce missed deadlines and improve time management. Offline support will also allow students to view and create tasks when they do not have reliable internet access.

## 3. Custom REST API

Explain what the API stores or processes and why it is central to the app.

**API responsibilities and business logic:**  

The custom REST API will store and process the information needed by the mobile application. It is central to the solution because it synchronises data between the Android application, the local offline database and the online database.



| # | Method and route | Purpose |
|---:|---|---|
| 1 | GET /api/tasks | Retrieve the signed-in user's tasks. |
| 2 | POST /api/tasks | Create a new assignment, test or study task. |
| 3 | PUT /api/tasks/{id} | Update a task, deadline or completion status. |
| 4 | DELETE /api/tasks/{id} | Delete a task. |
| 5 | GET /api/tasks/upcoming | Retrieve upcoming and overdue tasks for the dashboard. |
| 6 | GET /api/modules | Retrieve the user's modules. |
| 7 | POST /api/modules | Create a new module. |

## 4. POE feature fit

| Requirement | How it will fit the proposed app |
|---|---|
| Single Sign-On | Users sign in using their Google account through Google Sign-In or Firebase Authentication. |
| Settings — identify at least three | Language selection, light/dark theme, reminder time, default task sorting and notification enable/disable setting. |
| Biometric authentication | Users can enable fingerprint or facial authentication to reopen the app after signing in. |
| Offline action and synchronisation | Tasks and modules are stored locally using Room. Offline changes are uploaded through WorkManager when internet access returns. |
| Real-time notification | Firebase Cloud Messaging sends reminders when deadlines are approaching. Local notifications can act as a backup. |
| Two South African languages | The interface will support English and Afrikaans using Android string resource files. |

## 5. Five user-defined features

| # | Feature | Purpose and user value |
|---:|---|---|
| 1 | Module management | Students create modules and assign different colours or module codes to them. |
| 2 | Assignment and task management | Students create, edit, complete and delete assignments, tests and study tasks. |
| 3 | Upcoming-work dashboard | Displays the most urgent tasks and highlights overdue work. |
| 4 | Calendar view | Allows students to see deadlines arranged by date. |
| 5 | Progress summary | Shows completed, outstanding and overdue task totals. |

## 6. Comparable Android apps

This is not the formal research report. Identify three suitable apps that could later be compared with your concept.

| App | Google Play Store link | Why it is comparable |
|---|---|---|
| MyStudyLife |https://play.google.com/store/apps/details?id=com.virblue.mystudylife  | A student planner that organises academic tasks and schedules, making it the closest comparison to CampusTask. |
| Microsoft To Do | https://play.google.com/store/apps/details?id=com.microsoft.todos |Provides task lists, reminders and daily planning features.  |
| Todoist | https://play.google.com/store/apps/details?id=com.todoist | Allows users to organise tasks, deadlines and calendar-based work across devices. |

## 7. Feasibility and approval

**Proposed technology:** 

##
| Area | Technology |
|---:|---|
|Android application|Kotlin and Jetpack Compose|
| Architecture | MVVM |
| API connection | Retrofit |
| Offline database | Room |
| Background synchronisation | WorkManager |
| Custom API | ASP.NET Core Web API |
| Online database | PostgreSQL, SQL Server or Azure SQL |
| API data access | Entity Framework Core |
| Authentication | Firebase Authentication with Google Sign-In |
| Notifications | Firebase Cloud Messaging |
| Hosting | Azure App Service or another suitable cloud host |
| Source control | GitHub | 

**Three main risks and how they will be reduced:**  


1.  | Offline synchronisation conflicts | Each record will contain a last-updated timestamp. The API can use a simple latest-update-wins rule. |
2.  | Notifications not arriving correctly | The group will test notifications early and use scheduled local notifications as a backup. |
3.  | The application becoming too large | The group will finish task and module CRUD first before starting the calendar, statistics and visual improvements. |

**Scope check:**  

If the project becomes too large, remove the progress statistics first, followed by the full calendar view and advanced colour customisation. The core app would still include sign-in, modules, tasks, deadlines, offline access and notifications.

### Lecturer decision

- [ ] Approved
- [ ] Approved with changes
- [ ] Revise and resubmit

**Conditions or comments:**  
