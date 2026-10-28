🏫 RumiWare SchoolOS — School Management System

A modular, full-stack School Management System built with Django and PostgreSQL to centralize academic administration, student services, school operations, finance, and communication in one integrated platform.

RumiWare SchoolOS is a comprehensive school administration application designed to organize everyday school workflows through role-based dashboards, connected operational modules, structured records, and permission-controlled access.

The system brings together academic management, admissions, attendance, examinations, fee management, staff administration, payroll, library services, transportation, inventory, reporting, and personalized portals for students, parents, and teachers.

Project status: Controlled pilot candidate. The application is intended for demonstrations using fictional data or explicitly authorized testing. It is not approved for real-school production use until the outstanding security, operational, compliance, storage, and recovery requirements have been addressed.

📌 Table of Contents

Project Overview

Project Objectives

Key Features

User Roles and Access

Core Modules

Student and Family Portals

Security and Data Integrity

Technology Stack

System Architecture

Reporting and Analytics

Deployment and Infrastructure

Current Limitations

Production Readiness

Project Repository

Intended Use Cases

Future Development Opportunities

About the Project

📖 Project Overview

SchoolOS is a centralized School Management System (SMS), also known as a School ERP or School CMS, built to manage interconnected school operations through a single web application.

Instead of maintaining disconnected spreadsheets, separate records, and manual workflows, the system provides structured modules that share academic, student, staff, attendance, examination, and financial information.

The platform follows a modular application architecture, with dedicated Django applications for individual areas of school management and PostgreSQL as the relational database.

The system focuses on:

Centralized student, guardian, teacher, and employee records.

Academic year, term, class, section, and subject management.

Admissions and enrollment lifecycle management.

Student and staff attendance.

Examination setup, marks, grading, and report cards.

Fee billing, collections, refunds, and financial reporting.

Timetables, homework, and academic communication.

Human resources and payroll workflows.

Library circulation and transport administration.

Inventory, assets, and official certificates.

Role-specific portals, reports, and analytics.

Security-conscious access control and operational recordkeeping.

🎯 Project Objectives

Centralization: Bring major school administration workflows into one integrated platform.

Efficiency: Reduce repetitive administrative work and fragmented recordkeeping.

Accuracy: Maintain structured records, validation rules, and controlled lifecycle transitions.

Transparency: Provide authorized users with relevant academic, attendance, and financial information.

Accountability: Use approval workflows, audit records, and traceable financial transactions.

Access control: Restrict sensitive student, family, staff, and financial information according to user permissions.

Scalability: Organize functionality into separate modules that can be maintained and extended independently.

Operational visibility: Provide dashboards, reports, and analytics to help authorized school personnel understand school operations.

✨ Key Features

Modular Django-based web application.

PostgreSQL-backed relational data management.

Custom user model and role-based permission groups.

Authentication, logout, password reset, and login throttling.

Administrative dashboard and personalized user portals.

Student admissions, enrollment, and historical records.

Guardian relationships and family-specific access.

Teacher assignments and academic workspace restrictions.

Student and staff attendance management.

Examination scheduling, grading, results, and report cards.

Fee structures, concessions, invoices, receipts, and reconciliation.

Weekly timetables with conflict validation and teacher substitutions.

Homework assignments, submissions, and released feedback.

School events, announcements, and authorized conversations.

Human resources, employment records, and leave-related workflows.

Payroll approvals and accounting ledger integration.

Library books, circulation, renewals, and reservations.

Transport routes, vehicle assignments, maintenance, and incident records.

Inventory movements and durable asset tracking.

Controlled issuance of official documents and certificates.

Role-scoped analytics, CSV/PDF reports, and bounded exports.

Responsive, server-rendered user interfaces.

Database migrations, automated tests, and continuous integration configuration.

Deployment configuration and operational documentation.

👥 User Roles and Access

The system uses multiple permission groups and role-aware workflows. Access depends on the user's assigned permissions, relationships, and the specific record being requested.

User role

Main responsibilities

System administrator

Authorized system configuration, user administration, and privileged management

School administration

School settings, academic setup, admissions, and operational oversight according to permissions

Teachers

Assigned classes, attendance, assessment work, homework, and authorized student information

Students

Personal academic information, attendance, published results, homework, and permitted documents

Parents / Guardians

Information about currently linked children, attendance, published results, notices, and permitted fee records

Finance personnel

Authorized billing, collections, reconciliation, expenses, and financial reporting

HR and payroll personnel

Employment information, leave-related workflows, payroll preparation, and authorized approvals

Library personnel

Library circulation and reservation operations

Transport personnel

Assigned transport operations, vehicles, trips, and related records

Other authorized staff

Module-specific activities according to assigned permissions

Access-control principle: A user should not gain access to another student's records, a family's private information, confidential employee documents, or restricted financial information simply by changing a URL or record identifier.

The implementation includes object-level authorization checks in relevant workflows. Each deployment still requires comprehensive independent security validation.

🧩 Core Modules

1. Account Management and Authentication

Provides the foundation for authenticated access and permission-controlled workflows.

Capabilities include:

Custom user model.

Sign-in and secure POST-based logout.

Password reset through email workflows.

Password validation.

Database-backed login throttling and lockout controls.

Session management.

Permission groups and role-aware access.

Account information and password-change settings.

Authentication-related audit events.

2. School Administration and Academic Setup

Organizes the academic structure of a school.

Capabilities include:

School identity and configuration settings.

Academic year and term management.

Class and section configuration.

Subject management.

Teacher and subject assignments.

Academic date and ordering constraints.

Controlled academic lifecycle transitions.

Administration dashboard and operational summaries.

3. Student Information and Admissions

Maintains structured student records throughout the enrollment lifecycle.

Capabilities include:

Student directories and individual profiles.

Admissions and enrollment workflows.

Guardian and family relationships.

Enrollment history.

Student profile and identity information.

Staff and teacher profiles.

Student and staff image handling.

CSV import previews and confirmation workflows.

Import validation and duplicate or stale-data protections.

Authorized student record access.

4. Attendance Management

Supports student and staff attendance workflows.

Capabilities include:

Student attendance registers.

Staff attendance registers.

Attendance calendars.

Attendance corrections and approval workflows.

Leave requests and related records.

Attendance dashboards and summaries.

Guardian attendance notices.

Policy-based attendance statistics.

Scoped CSV and PDF reports.

Attendance history and record finalization controls.

5. Examination and Grading Management

Provides structured examination and assessment workflows.

Capabilities include:

Examination and assessment configuration.

Weighted assessments.

Configurable grading rules.

Examination date sheets.

Assigned-class marks entry.

Independent result review.

Result publication snapshots.

Controlled corrections to published results.

Student and guardian access to authorized published results.

Examination analytics.

Branded PDF report cards.

6. Fees and Financial Management

Organizes school billing and financial operations through controlled workflows.

Capabilities include:

Effective-dated fee structures.

Student billing and invoice generation.

Fee concessions.

Billing previews and validation.

Independent approval workflows.

Manual payment collection records.

Receipts and immutable financial history.

Refund and reversal workflows.

Expense management.

Balanced accounting journal entries.

Financial reconciliation.

Fee and collection reports.

Authorized family access to invoices, balances, and receipts.

Important: The system does not have a connected real banking or online payment gateway. Payment collection workflows should not be interpreted as automated payment processing.

7. Timetable and Scheduling

Supports the organization of weekly academic schedules.

Capabilities include:

Weekly timetable creation.

Academic-year and shift configuration.

Periods, breaks, and room setup.

Teacher availability management.

Workload limits.

Timetable conflict checks.

Timetable publication and archiving.

Teacher substitutions.

Workload and free-period reports.

Room utilization reports.

8. Learning and Homework

Provides workflows connecting teachers and students outside classroom attendance and examination records.

Capabilities include:

Homework creation by assigned teachers.

Homework instructions and deadlines.

Student submissions.

Submission versions and attachments.

Teacher feedback and grading.

Controlled feedback release.

Completion, late, missing, reviewed, and excused reporting.

Authorized student and guardian access to relevant learning records.

9. School Communication

Supports controlled information sharing among authorized school users and families.

Capabilities include:

School events and announcements.

Audience-scoped communication.

Calendar integration.

Authorized family and staff conversations.

Message search and pagination.

Conversation recipient restrictions.

Message reporting and moderation workflows.

Unified notification inbox.

Notifications related to attendance, examinations, finance, homework, and school activities.

These features do not constitute unrestricted student chat or a complete emergency communication service.

10. Human Resources

Supports employee administration and employment history.

Capabilities include:

Employee records linked to existing staff or teacher identities.

Employment history.

Departments and designations.

Manager relationships.

Contract and probation information.

Departure and rejoining history.

Leave-related workflows.

Confidential employee notes and documents.

Permission-controlled access to HR information.

11. Payroll Management

Provides controlled payroll preparation and accounting workflows.

Capabilities include:

Effective-dated salary revisions.

Salary component and payroll-period snapshots.

Payroll draft and submission workflows.

Independent approval.

Payroll finalization.

Payment recording.

Accounting journal integration.

Authorized reversals.

Released payslips for eligible employees.

Limitation: Payroll calculations have not been professionally approved for statutory taxes, employment law, benefits, or jurisdiction-specific compliance.

12. Library Management

Supports school library circulation and resource tracking.

Capabilities include:

Library title and physical-copy records.

Student and staff memberships.

Book issue and return.

Configurable borrowing limits.

Loan durations and renewals.

Grace periods and overdue fines.

Reservation queues.

Transaction-safe circulation workflows.

Library fines do not automatically become school fee invoices.

13. Transport Management

Organizes school transport records and assignments.

Capabilities include:

Vehicle records.

Transport routes and ordered stops.

Trip management.

Driver and attendant assignments.

Student transport assignments.

Vehicle capacity and assignment checks.

Maintenance and inspection records.

Transport notices and incident records.

Guardian access to linked children's transport information.

The system does not provide GPS-based live vehicle tracking.

14. Inventory and Asset Management

Supports consumable inventory and durable school asset tracking.

Capabilities include:

Inventory item records.

Stock movement history.

Stock issue and receipt operations.

Controlled stock corrections.

Protection against concurrent over-issuing.

Asset custody and location records.

Asset condition and warranty information.

Maintenance history.

Asset transfers.

Independently approved disposal events.

Stock quantities are derived from finalized movements rather than relying solely on manually editable balances.

15. Certificates and Official Documents

Provides controlled workflows for official document issuance.

Capabilities include:

Document issuance requests.

Subject authorization.

Review and approval stages.

Issued-record snapshots.

Authorized document access.

Recordkeeping for issued documents.

Government identity verification and external statutory integrations are not included.

16. Analytics and Reporting

Combines authorized operational indicators and reporting tools.

Capabilities include:

Executive dashboard indicators.

Student progress summaries.

Attendance and examination insights.

Finance-related operational indicators.

Integrated reporting center.

Data-quality checks.

CSV and PDF exports where supported.

Bounded export operations.

Permission-scoped access to reports.

Reporting documentation and metric definitions.

Reports are designed to support administrative visibility. They do not replace independent financial audits or official statutory reporting.

🎓 Student and Family Portals

The application includes personalized portals for students, parents/guardians, and teachers.

Student Portal

Students can access permitted personal information, including:

Academic profile and enrollment history.

Attendance calendar and statistics.

Published examination results.

Authorized report cards and documents.

Fee invoices, balances, and receipts.

Academic calendar information.

Homework and feedback.

Notifications and account settings.

Parent / Guardian Portal

Parents and guardians can access information about their currently linked children, including:

Family overview.

Child selection.

Academic and enrollment information.

Attendance history.

Published examination results.

Report cards and permitted documents.

Fee statements, invoices, and receipts.

School calendar and notifications.

Relevant homework and communication information.

Teacher Portal

Teachers can access permitted teaching and academic workflows, including:

Assigned-class and subject workspaces.

Student rosters.

Attendance-related workflows.

Assessment and marks-entry links.

Homework management.

Authorized student information.

Personal attendance and leave information.

Relevant school notifications.

The portals are integrated with existing application modules rather than operating as separate, disconnected systems.

🔐 Security and Data Integrity

Security and data integrity are important parts of the application's design.

Authentication and application security

Django authentication and password validation.

Role- and permission-based authorization.

Login throttling and temporary lockouts.

CSRF protection.

POST-based state-changing actions where implemented.

Secure production configuration checks.

Session and cookie security settings.

Security headers.

Protected access to relevant private records and downloads.

Data protection and integrity

PostgreSQL relational database.

Database migrations and integrity constraints.

Validation of important lifecycle transitions.

Restricted access to student and guardian records.

Approval workflows for selected financial and operational actions.

Immutable financial history in relevant workflows.

Balanced double-entry accounting journals.

Concurrency safeguards for selected operations.

Audit records and controlled exports.

Important security disclaimer

These controls describe implemented design and workflows; they are not a guarantee that the application is completely secure. Independent penetration testing, infrastructure review, privacy assessment, and operational validation remain necessary before handling real school records.

🛠️ Technology Stack

Technology

Purpose

Python 3.13

Application programming language

Django 5.2

Backend web framework

PostgreSQL

Relational database

psycopg 3

PostgreSQL database connectivity

Django Templates

Server-rendered user interfaces

HTML5 and CSS

Page structure and styling

JavaScript

Client-side interactions where required

Pillow

Image processing support

ReportLab

PDF document generation

WhiteNoise

Static asset serving

django-axes

Login throttling and lockout support

dj-database-url

Database URL configuration

python-dotenv

Environment variable loading

Ruff

Python linting and code-quality checks

Automated tests and CI

Regression checking and continuous integration

The application uses a modular Django structure with separate applications for accounts, academics, people, attendance, examinations, finance, scheduling, learning, communications, HR, payroll, library, transport, inventory, certificates, analytics, and related portals.

🏗️ System Architecture

The system follows a modular, server-rendered web application architecture.

Users
  |
  v
Role-Based Web Interfaces
  |
  v
Django Views and Application Logic
  |
  +-- Authentication and Permissions
  +-- Academic Administration
  +-- Students and Admissions
  +-- Attendance and Examinations
  +-- Finance and Payroll
  +-- Scheduling and Learning
  +-- Communication and Notifications
  +-- HR, Library, and Transport
  +-- Inventory, Assets, and Certificates
  +-- Analytics and Reporting
  |
  v
Django ORM and Database Constraints
  |
  v
PostgreSQL Database

Architectural characteristics

Modular applications with distinct responsibilities.

Shared authentication and authorization.

Relational data models.

Server-rendered templates.

Database-backed workflows.

Controlled interactions between academic and operational modules.

Centralized reporting and personalized portals.

📊 Reporting and Analytics

The reporting layer helps authorized users review information across connected modules.

Examples include:

Attendance summaries and trends.

Examination performance and published results.

Homework completion and submission status.

Financial collections and reconciliation reports.

Teacher workload and timetable utilization.

Inventory and asset movement records.

Student progress summaries.

Operational data-quality indicators.

Available reports and fields depend on the module, user permissions, and configured data.

🚀 Deployment and Infrastructure

The project includes deployment-oriented configuration and operational documentation for a Django application using PostgreSQL.

The deployment setup includes:

Environment-based configuration.

PostgreSQL connection through DATABASE_URL.

Separate Django settings for application environments.

Production checks for required security settings.

Static asset collection and serving configuration.

Database migrations.

CI and automated quality checks.

Vercel deployment configuration.

Neon PostgreSQL integration.

Health diagnostics and deployment checks.

Backup and restore procedures documented for operational preparation.

Deployment environment variables

A deployment typically requires environment-specific values such as:

Variable

Purpose

SECRET_KEY

Django application secret

DATABASE_URL

PostgreSQL connection URL

ALLOWED_HOSTS

Allowed application hostnames

CSRF_TRUSTED_ORIGINS

Trusted origins for CSRF validation

TIME_ZONE

Application timezone configuration

Actual requirements depend on the selected settings module and hosting environment. Production secrets must be configured privately and must never be committed to a public repository.

Deployment status: Deployment configuration does not mean the application is certified or ready for production. The project has an explicit production-readiness assessment and outstanding release blockers.

⚠️ Current Limitations

The following limitations are important when evaluating the project.

Production approval: The current release decision is limited to controlled pilot use with fictional data or an explicitly authorized test environment.

Online payments: No real payment gateway or banking integration is connected.

Transport tracking: GPS-based live tracking is not provided.

Payroll compliance: Statutory taxes and jurisdiction-specific payroll rules have not received professional approval.

Private file storage: Durable production-grade private storage and malware scanning/quarantine remain outstanding.

Backup and recovery: A complete approved production backup and recovery arrangement, including protected media, remains outstanding.

Monitoring: Hosted alerting, error tracking, and operational response procedures are not fully configured.

Security verification: Independent penetration and infrastructure testing remain outstanding.

Privacy and compliance: Legal, safeguarding, retention, and external privacy reviews remain necessary.

Performance: Production-scale load and soak testing remain outstanding.

Accessibility: A complete assistive-technology audit and formal accessibility certification have not been completed.

External services: Email delivery and other external integrations require environment-specific configuration and verification.

These limitations are documented to distinguish implemented application functionality from capabilities that require additional infrastructure, integrations, or independent validation.

✅ Production Readiness

Before the system is used by a real school, the following work must be completed and verified:

Independent security testing and threat modelling.

Privacy, data retention, and safeguarding review.

Validation of financial, payroll, and accounting policies.

Durable private file storage with appropriate access controls.

Malware scanning and file quarantine.

Encrypted backups and a tested full recovery process.

Defined recovery objectives and incident response procedures.

Monitoring, alerting, and error tracking.

Production-scale performance testing.

Email delivery and external integration testing.

Accessibility testing.

School-specific user acceptance testing.

Review of applicable legal and regulatory requirements.

No claim of legal compliance, certified security, or production readiness should be inferred from the presence of security controls or deployment configuration alone.

🔗 Project Repository

The application source code is maintained separately from this documentation repository.

Main project: School-Management-System — Private Source Repository

The source repository contains the implementation. This public repository serves as the project's documentation and portfolio page.

Because the source repository is private, visitors without authorized access cannot browse or clone its code.

🎯 Intended Use Cases

The system is designed around common school administration scenarios, including:

Managing student admissions and enrollment records.

Organizing academic years, classes, sections, and subjects.

Recording student and staff attendance.

Preparing examinations and publishing results.

Managing school fee billing and financial records.

Creating timetables and assigning teachers.

Distributing homework and collecting student submissions.

Communicating school announcements and events.

Maintaining employee and payroll records.

Managing library resources and circulation.

Organizing school transport and vehicle assignments.

Tracking inventory and durable school assets.

Issuing authorized certificates and documents.

Reviewing school operations through reports and analytics.

Providing personalized access to students, families, teachers, and authorized staff.

🔮 Future Development Opportunities

Potential areas for future development include:

Integration with a secure online payment provider.

Durable private object storage and automated malware scanning.

Production-grade monitoring and recovery automation.

Advanced academic analytics and configurable reports.

Mobile-friendly enhancements and progressive web app capabilities.

Optional SMS and messaging-provider integrations.

Additional language and localization support.

School-specific configuration and multi-school tenancy, if required.

More extensive accessibility and automated end-to-end testing.

Professionally validated payroll and accounting policy support.

These are potential enhancements, not claims that the integrations already exist.

👨‍💻 About the Project

RumiWare SchoolOS is a full-stack software project focused on bringing school administration, academic workflows, financial operations, and user-specific services together in a modular web application.

It demonstrates practical software engineering concepts including:

Backend development with Python and Django.

Relational database design with PostgreSQL.

Authentication and authorization.

Multi-module application architecture.

Database migrations and integrity constraints.

Workflow design and approval processes.

Reporting and PDF generation.

Application security considerations.

Automated testing and deployment preparation.

The project is intended to evolve through continued development, testing, and validation.

Built with Python, Django, PostgreSQL, and a focus on structured school operations.

RumiWare SchoolOS — Bringing school workflows together in one platform.
