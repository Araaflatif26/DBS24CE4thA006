School Management System
CMPE-232 Term Project
University of Engineering and Technology, Lahore
---
 Project Overview
A complete School Management System built with C# Windows Forms and MySQL (Workbench).
---
 Requirements Coverage
Requirement	Status
Minimum 8 domain classes	✅ 10 domain + 5 software classes
Minimum 5 software classes	✅ Done
Entities in ERD (Min 10)	✅ 16 tables
Database tables (Min 15)	✅ 16 tables
Validators	✅ Validator.cs
Handle exceptions	✅ Try/catch + Logger everywhere
UI elements (textbox, password, radio, checkbox, dropdown, date, textarea, scrollbar, tables, panels, file menu)	✅ All forms
Logging in case of errors	✅ Logger.cs + ErrorLogs table + LogViewerForm
Transactions (min 3)	✅ 3 in stored procedures
Views (min 5)	✅ 7 views
Stored Procedures (min 3)	✅ 5 stored procedures
Triggers (min 2)	✅ 4 triggers
Constraints (min 10)	✅ 12+ constraints
PDF Reports (min 10)	✅ 11 PDF reports
Responsive UI	✅ Panels, scroll, resize
Reports by parameters	✅ All reports have parameter inputs
---
 Setup Instructions
Step 1: Database Setup
Open MySQL Workbench
Run `Database/schema.sql` — creates all tables
Run `Database/procedures\_views\_triggers.sql` — creates views, SPs, triggers, constraints, sample data
Step 2: Update Connection String
Open `DAL/DatabaseHelper.cs` and change:
```csharp
private static readonly string ConnectionString =
    "Server=localhost;Database=SchoolManagementDB;Uid=root;Pwd=yourpassword;";
```
Replace `yourpassword` with your MySQL root password.
Step 3: Install .NET & Build
Requirements:
.NET 6.0 SDK (Windows)
Visual Studio 2022 or later
Open `SchoolManagementSystem.sln` in Visual Studio.  
NuGet packages will auto-restore:
`MySql.Data` (8.0.33)
`iTextSharp` (5.5.13.3)
Press F5 to build and run.
Step 4: Login
Default admin credentials:
Username: `admin`
Password: `admin123`
---
 Project Structure
```
SchoolManagementSystem/
├── Database/
│   ├── schema.sql                   # All 16 tables
│   └── procedures\_views\_triggers.sql # Views, SPs, Triggers
├── SchoolManagementSystem/
│   ├── DAL/
│   │   ├── DatabaseHelper.cs        # DB connection \& query helpers
│   │   └── StudentDAL.cs            # Student data access layer
│   ├── Models/
│   │   └── Models.cs                # 10 domain + 5 software classes
│   ├── Validators/
│   │   └── Validator.cs             # Input validation
│   ├── Utilities/
│   │   └── Logger.cs                # Logging to DB + file
│   ├── Reports/
│   │   └── PdfReportGenerator.cs    # 11 PDF reports (iTextSharp)
│   ├── Forms/
│   │   ├── LoginForm.cs
│   │   ├── DashboardForm.cs
│   │   ├── StudentForm.cs
│   │   ├── TeacherForm.cs
│   │   ├── ClassForm.cs
│   │   ├── SubjectForm.cs
│   │   ├── DepartmentForm.cs
│   │   ├── AttendanceForm.cs
│   │   ├── ExamForm.cs
│   │   ├── FeeManagementForm.cs
│   │   ├── TimetableForm.cs
│   │   ├── AnnouncementForm.cs
│   │   ├── LogViewerForm.cs
│   │   └── ReportForm.cs
│   └── Program.cs
```
---
 Database Schema Summary
16 Tables: Students, Teachers, Classes, Subjects, Departments, Users, Attendance, Exams, ExamResults, FeeStructure, FeePayments, Timetable, TeacherSubjects, Announcements, LeaveRequests, ErrorLogs
7 Views: vw_StudentDetails, vw_TeacherDetails, vw_AttendanceSummary, vw_ExamResultsSummary, vw_FeeStatus, vw_ClassTimetable, vw_ReportCard
5 Stored Procedures: sp_AddStudent, sp_RecordFeePayment, sp_GetClassAttendanceReport, sp_GetStudentReportCard, sp_BulkMarkAttendance
4 Triggers: trg_AssignGrade, trg_LogFeePayment, trg_PreventStudentDelete, trg_LogResultUpdate
12+ Constraints on all major tables
---
 PDF Reports (11 total)
Student List Report
Attendance Report (by class/subject/date range)
Exam Results Report
Student Report Card
Fee Collection Report
Teacher List Report
Class-wise Student Count
Fee Defaulters Report
Subject-wise Results Summary
Daily Attendance Summary
Class Timetable
 GitHub Repository
Name format: `DBS26CE4thAF006` where `006` is my Project ID.
---
CMPE-232 | Computer Engineering Department | UET Lahore
