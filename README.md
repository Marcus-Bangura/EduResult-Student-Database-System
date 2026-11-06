EduResults – Student Examination and Result Management System

1. Project Overview

EduResults is a PostgreSQL-based Student Examination and Result Management System developed as an academic database development project. The system is designed to demonstrate the practical application of relational database concepts, advanced SQL queries, database relationships, views, triggers, stored procedures, and data management techniques.

The project focuses on the organization and management of student academic information, including student registration, course information, academic departments, programmes, academic sessions, student enrollments, examination results, and lecturer assignments.

EduResults provides a structured database environment where student academic records can be stored, related, retrieved, updated, and monitored through SQL operations.

The project was developed using PostgreSQL 18 as the database management system and pgAdmin 4 as the graphical interface for database administration, SQL execution, testing, and implementation.

This project demonstrates how a properly designed relational database can improve the organization, accessibility, consistency, and management of academic information within an educational institution.

2. Background of the Project

Educational institutions manage large volumes of academic information daily. These include student biodata, course registrations, departmental records, academic programmes, examination scores, grades, and academic performance records.

When such information is managed through poorly organized or disconnected systems, institutions may experience difficulties retrieving student records, tracking enrollment information, monitoring examination results, and maintaining accurate academic records.

A well-structured database management system provides a more reliable approach to organizing this information.

EduResults was developed to demonstrate how PostgreSQL can be used to address these challenges through a relational database structure supported by primary keys, foreign keys, constraints, SQL queries, views, triggers, and stored procedures.

The database brings together different academic entities and establishes relationships between them. This makes it possible to retrieve related information across multiple tables without unnecessarily duplicating records.

For example, the system can retrieve a student’s personal information alongside their registered courses, academic session, enrollment status, examination scores, and results.

The project also incorporates database automation and accountability mechanisms. Triggers are used to automate selected database operations, while the audit trigger provides a mechanism for recording changes to examination-result records.

Furthermore, the stored procedure provides a reusable operation for registering students for courses within specified academic sessions.

Through these features, EduResults demonstrates the practical importance of database design, data integrity, automation, and efficient information retrieval in an academic environment.

3. Aim of the Project

The main aim of EduResults is to design, develop, implement, and test a relational PostgreSQL database that supports the management of student academic records and demonstrates the application of advanced SQL and PostgreSQL database features.

4. Project Objectives

The specific objectives are to:

1. Design and implement a relational database for managing student academic information.
2. Create related database tables with appropriate primary keys and foreign keys.
3. Establish relationships between students, courses, departments, programmes, lecturers, academic sessions, enrollments, and examination results.
4. Develop advanced SQL queries to retrieve meaningful academic information.
5. Implement INNER JOIN, LEFT JOIN, and RIGHT JOIN operations.
6. Create PostgreSQL views for simplified reporting and information retrieval.
7. Develop triggers to automate selected database activities.
8. Implement an audit mechanism for monitoring examination-result changes.
9. Develop and execute a stored procedure for student course registration.
10. Test the database operations and verify that the implemented features work as intended.

5. Technologies and Tools Used

The following technologies and tools were used in developing the EduResults database:

Technology	Purpose
PostgreSQL 18	Relational database management system
pgAdmin 4	Database administration and SQL development interface
SQL	Database creation, manipulation, querying, and management
PL/pgSQL	Development of PostgreSQL trigger functions and stored procedures
GitHub	Project source-code hosting and version control
Microsoft Word	Preparation of the technical project report

6. Database Structure and Organization

The EduResults database consists of eight principal relational tables designed to organize academic information and establish relationships between different entities.

6.1 Main Database Tables

1. Students

The students table stores information relating to individual students. It contains student identification details and personal information required for academic record management.

2. Departments

The departments table stores information about the academic departments within the institution. It helps organize students, courses, and academic activities according to departmental structures.

3. Programmes

The programmes table contains information about the academic programmes offered by the institution.

4. Courses

The courses table stores information about academic courses, including course codes and course titles. It provides the basis for associating students with the courses they undertake.

5. Lecturers

The lecturers table stores information about lecturers responsible for academic teaching and course assignments.

6. Academic Sessions

The academic_sessions table stores academic-year and semester information. It allows student enrollment and academic activities to be associated with particular academic periods.

7. Enrollments

The enrollments table records student course registrations. It establishes relationships between students, courses, and academic sessions and maintains enrollment-status information.

8. Results

The results table stores examination-result information associated with student enrollments. It supports the management of examination scores, grades, and result publication status.

6.2 Database Relationships

The database uses primary keys and foreign keys to establish relationships between its tables.

These relationships help maintain referential integrity and ensure that related academic records are properly connected.

For example:

* A student can have multiple enrollment records.
* A course can be associated with multiple student enrollments.
* An academic session can contain multiple enrollments.
* An enrollment can have an associated examination result.
* Departments and programmes help organize academic records.

The relational structure makes it possible to retrieve information from different tables through SQL JOIN operations.

7. Advanced SQL Queries and JOIN Operations

Advanced SQL queries were implemented to demonstrate how information can be retrieved from multiple related tables.

The project uses different JOIN operations to answer meaningful questions about student enrollment, academic performance, examination results, and course registration.

7.1 INNER JOIN

INNER JOIN retrieves records that have matching values in the related tables.

In EduResults, INNER JOIN is used to combine student information with enrollment, course, academic-session, and examination-result information.

Examples of implemented queries include:

* Student performance details.
* Student examination results.
* Average performance per course.
* Course enrollment summaries.
* Students with excellent examination results.
* Student examination performance rankings.

7.2 LEFT JOIN

LEFT JOIN retrieves all records from the left-hand table and matching records from the right-hand table.

This is useful for identifying students who may not yet have enrollment records and examining student enrollment information without excluding unmatched students.

7.3 RIGHT JOIN

RIGHT JOIN retrieves all records from the right-hand table and matching records from the left-hand table.

It is used to demonstrate how related academic records can be retrieved while retaining all records from the right-hand table.

These queries demonstrate the practical application of relational database operations in academic information management.

8. PostgreSQL Views

EduResults implements five database views to simplify information retrieval and support academic reporting.

A view is a virtual table created from the result of an SQL query. It allows frequently required information to be accessed without rewriting the entire query each time.

The five views developed include:

View 1: Student Result Summary

Provides a summarized presentation of student examination-result information.

View 2: Course Performance Summary

Provides information that supports the examination and comparison of academic performance across courses.

View 3: Student Enrollment Summary

Provides an organized summary of student course enrollment information.

View 4: Lecturer Course Assignment

Provides information about lecturers and the courses assigned to them.

View 5: Academic Grade Distribution

Provides a summary of the distribution of academic grades.

The views improve the organization of database queries and demonstrate how PostgreSQL views can support reporting and information retrieval.

9. PostgreSQL Triggers

Triggers are database objects that automatically execute trigger functions when specified database events occur.

EduResults implements two meaningful triggers to demonstrate database automation and accountability.

9.1 Trigger One – Automatic Enrollment Status Update

The first trigger is attached to the results table.

It operates after a result record is inserted or its result status is updated.

The trigger function checks whether the examination result has been published. When the specified condition is satisfied, the corresponding enrollment record is automatically updated to Completed.

This reduces the need for a separate manual update of the enrollment status.

The implementation was tested using an examination-result record. The verification query showed a result status of Published and a corresponding enrollment status of Completed.

9.2 Trigger Two – Examination Result Audit Trail

The second trigger is designed to provide an audit trail for examination-result changes.

It is attached to the results table and executes after INSERT or UPDATE operations.

The trigger function records relevant examination-result changes in the result_audit table.

For updates, the audit mechanism captures information such as old and new examination scores, old and new grades, the operation performed, the timestamp, and the database user.

This provides a record of changes and supports accountability and traceability in examination-result management.

The audit mechanism is designed to record INSERT and UPDATE operations.

10. Stored Procedure

EduResults implements a PostgreSQL stored procedure called:

register_student_for_course

The stored procedure is designed to process student course registration.

It accepts the necessary registration information, including the student number, course code, academic year, and semester.

The procedure processes the registration operation by locating the relevant student, course, and academic session and creating the corresponding enrollment record.

This reduces the need to manually execute multiple SQL statements whenever a student is registered for a course.

Stored Procedure Testing

The procedure was executed using the following test registration information:

* Student Number: LUCT2026007
* Course Code: CSC101
* Academic Year: 2026/2027
* Semester: 1

The execution returned the notification:

Student registration processed successfully.

A subsequent verification query joined the students, courses, academic_sessions, and enrollments tables to confirm that the registration had been processed.

The verification output returned the registered student, Mohamed Jalloh, together with the course CSC101, the academic year 2026/2027, Semester 1, and the enrollment status Registered.

This demonstrates the successful execution and verification of the stored procedure.

11. Database Testing and Verification

Testing was carried out using pgAdmin 4 to establish whether the database structures and implemented PostgreSQL features performed their intended functions.

The testing process covered:

1. Execution of SQL queries.
2. Verification of relational database operations.
3. Testing of INNER JOIN, LEFT JOIN, and RIGHT JOIN queries.
4. Creation and execution of database views.
5. Testing of the automatic enrollment-status trigger.
6. Testing of the examination-result audit trigger.
7. Execution of the student course-registration stored procedure.
8. Verification of the resulting enrollment records.

The testing process provided evidence that the database features were functioning as designed for the tested records.

12. Database Backup and Source Code Management

A PostgreSQL database backup was created to preserve the EduResults database and its contents.

The backup was generated through pgAdmin 4 using the PostgreSQL backup facility.

The project also includes an SQL source-code file containing the database implementation scripts.

These files provide two important forms of project preservation:

SQL Source Code (.sql)

Contains the SQL statements used to create and implement the database structures and features.

PostgreSQL Backup (.backup)

Contains a database backup that can be used to restore the database in a compatible PostgreSQL environment.

GitHub is used to host the project files and maintain an accessible copy of the project source code.

13. Project Significance

The EduResults project demonstrates how relational database technology can support academic information management.

Its significance includes:

* Improved organization of student academic information.
* Structured storage of student and course records.
* Efficient retrieval of related academic information.
* Simplified reporting through database views.
* Automated enrollment-status management.
* Improved examination-result accountability through audit records.
* Reusable student registration operations through stored procedures.
* Preservation of database work through source-code management and backup.

The project also provides practical experience in database development, SQL programming, PostgreSQL administration, and database testing.

14. Limitations and Future Improvements

Although EduResults demonstrates important database management features, it is primarily a database-level academic project.

The current implementation focuses on relational database design, SQL queries, views, triggers, stored procedures, and database operations.

Possible future improvements could include:

1. Developing a web-based user interface for students, lecturers, and administrators.
2. Introducing secure user authentication and role-based access control.
3. Developing an online student registration portal.
4. Creating automated academic transcripts and result reports.
5. Introducing additional reporting and performance-analysis features.
6. Integrating notifications for published examination results.
7. Expanding the audit system to support additional database operations.

These improvements could transform EduResults into a more comprehensive academic information management platform.

15. Conclusion

EduResults demonstrates the practical application of PostgreSQL in developing a relational database for student examination and result management.

The project integrates eight related database tables and demonstrates the use of primary keys, foreign keys, advanced SQL queries, JOIN operations, views, triggers, and stored procedures.

Through its automated enrollment-status update, examination-result audit mechanism, and student registration procedure, the database illustrates how PostgreSQL features can be applied to solve practical academic information-management problems.

The implementation and testing process provided practical experience in database design, SQL development, database administration, and information retrieval.

Overall, EduResults represents a practical demonstration of database development principles and the use of advanced PostgreSQL features in an educational environment.



16. Project Information

Project Name: EduResults – Student Examination and Result Management System

Database Management System: PostgreSQL 18

Database Administration Tool: pgAdmin 4

Programming Language: SQL and PL/pgSQL

Project Type: Individual Academic Database Development Project

Course: DCOMP 114 – Database Systems

Institution: Limkokwing University of Creative Technology, Sierra Leone

Academic Project Period: September 2026 – February 2027

Repository: EduResults-Student-Database-System

Developer: Marcushia Marcus-Bangura



17. Project Files

The repository is intended to contain the following project materials:

File	Description
eduresults.sql	Complete PostgreSQL SQL source code
Eduresult.backup	PostgreSQL database backup
EduResults_Technical_Report.pdf	Technical project documentation
README.md	Project overview and documentation

18. How to Restore the Database

To restore the EduResults database using pgAdmin 4:

1. Install PostgreSQL and open pgAdmin 4.
2. Connect to your PostgreSQL server.
3. Create a new database named eduresults_db.
4. Right-click the database and select Restore.
5. Select the Eduresult.backup file.
6. Choose the appropriate backup format, depending on how the backup was created.
7. Start the restoration process.
8. Refresh the database and inspect the restored tables, views, functions, and procedures.

Alternatively, the SQL source-code file can be opened in the pgAdmin Query Tool and executed in the appropriate database, subject to the script’s organization and contents.



EduResults – Organizing Academic Records Through Relational Database Technology.
