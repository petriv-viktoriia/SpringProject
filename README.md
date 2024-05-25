# ELECTRONIC RECORD BOOK
Development of an electronic record book using web technologies. In this project, the Java programming language and its Spring Boot framework are used as the basis for the backend.

# FUNCTIONAL REQUIREMENTS
As a student, I want to be able to register using the organization's email.
As a student, I want to be able to log in with my email and password.
As a student, I want to be able to view my grades from different semesters.
As a student, I want to be able to edit my personal data.
As a student, I want to be able to recover my password if I lose it.
As a student, I want to be able to view information about courses from previous semesters.

As an professor, I want to be able to log in with my email and password.
As an professor, I want to be able to view the list of students enrolled in my courses.
As a professor, I want to be able to view the list of courses I teach.

As an administrator, I want to be able to add, edit, and delete student profiles.
As an administrator, I want to be able to view the list of students and the details of each profile.
As an administrator, I want to be able to create, edit, and delete courses.
As an administrator, I want to be able to add, edit, and delete professor profiles.
As an administrator, I want to be able to view the list of professors and the details of each profile.
As an administrator, I want to be able to generate and view student progress reports
As an administrator, I want to be able to create, edit and delete faculties.
As an administrator, I want to be able to create, edit, and delete majors.
As an administrator, I want to be able to add, edit, and delete profiles of professors.
As an administrator, I want to be able to send a warning message to all users regarding any actions with the system.

# SYSTEM BEHAVIOURS

**FOR STUDENTS**
**Registration:**
- **Action:** the student enters the e-mail address and password.
- **Result:** the system creates a record in the *`Contacts`* and *`Student`* tables.

**Login:**
- **Action:** the student enters the e-mail and password.
- **Result:** The system checks the data from the table *`Contacts`* and provides access to the personal account.

**Viewing grades for different semesters:**
- **Action:** the student selects a semester to view grades.
- **Result:** the system displays a list of student grades for the selected semester from the table *`Book`*.

**Editing personal data:**
- **Action:** the student edits his personal data.
- **Result:** The system updates the data in the table *`Student`*.

**Restore password:**
- **Action:** the student requests password recovery by entering his/her e-mail.
- **Result:** the system sends an email with instructions for password recovery.


**FOR PROFESSORS**
**Login:**
- **Action:** the teacher enters the e-mail and password.
- **Result:** The system checks the data from the table *`Contacts`* and provides access to the teacher's personal account.

**Viewing the list of students enrolled in courses:**
- **Action:** the teacher views the list of students.
- **Result:** the system displays the list of students from the *`Student`* and *`Book`* tables who are enrolled in the teacher's courses.

**View the list of courses taught by the teacher**
- **Action:** the teacher views the list of courses.
- **Result:** the system displays the list of subjects from the *`Subject`* table that the teacher teaches.


**FOR ADMINISTRATOR**

**Adding, editing, and deleting student profiles:**
- **Action:** the administrator adds, edits or deletes a student profile.
- **Result:** the system adds, edits, or deletes records in the *`Student`* and *`Contacts`* tables accordingly.

**Viewing the list of students and details of each profile:**
- **Action:** the administrator views the list of students and profile details.
- **Result:** the system displays the list of students and their profile details from the *`Student`* table.

**Creating, editing and deleting courses:**
- **Action:** the administrator adds, edits or deletes a course.
- **Result:** the system adds, edits, or deletes records in the *`Subject`* table accordingly.

**Adding, editing and deleting profiles of teachers:**
- **Action:** the administrator adds, edits or deletes a teacher profile.
- **Result:** the system adds, edits, or deletes records in the *`Contacts`* and *`Subject`* tables accordingly.

**Generate and view reports on student progress:**
- **Action:** the administrator generates and views reports.
- **Result:** the system displays reports from the *`Book`* and *`Student`* tables

**Sending warning messages to all users about actions with the system:**
- **Action:** the administrator sends a message to all users.
- **Result:** the system sends a notification to all users from the *`Contacts`* table.

**Creating, editing and deleting specialties:**
- **Action:** the administrator adds, edits or deletes a specialty.
- **Result:** the system adds, edits, or deletes records in the *`Specialty`* table accordingly.

**Creating, editing and deleting faculties:**
- **Action:** the administrator adds, edits or deletes a faculty.
- **Result:** the system adds, edits, or deletes records in the *`Specialty`* table accordingly.

**Generating and viewing reports on student progress:**
- :**Action:** the administrator generates and views reports.
- :**Result:** the system displays reports from the *`Book`* and *`Student`* tables.



### REST API ENDPOINTS FOR AN ELECTRONIC GRADEBOOK

# FOR STUDENTS
**Registration:**
- **Method:** `POST`
- **URL:** *`/students/register`*
- **Description:** Student registration using the organization's mail

**Login:**
- **Method:** `POST`
- **URL:** *`/students/login`*
- **Description:** Logging in using email and password

**View grades for different semesters:**
- **Method:** `GET`
- **URL:** *`/students/{number_book}/grades`*
- **Description:** View grades for different semesters

**Edit personal data:**
- **Method:** `PUT`
- **URL:** *`/students/{number_book}`*
- **Description:** Edit personal data

**Password recovery:**
- **Method:** `POST`
- **URL:** *`/students/password-reset`*
- **Description:** Restore password in case of its loss

**View information about subjects in previous semesters:**
- **Method:** `GET`
- **URL:** *`/students/{number_book}/subjects`*
- **Description:** View information about subjects in previous semesters


### FOR PROFESSOR
**Input:**
- **Method:** `POST`
- **URL:** *`/teachers/login`*
- **Description:** Log in using email and password

**View the list of students enrolled in courses:**
- **Method:** `GET`
- **URL:** *`/teachers/{teacher_id}/students`*
- **Description:** View the list of students enrolled in courses

**View the list of courses taught by the teacher:**
- **Method:** `GET`
- **URL:** *`/teachers/{teacher_id}/subjects`*
- **Description:** View the list of subjects taught by the teacher


# FOR ADMINISTRATOR
**Adding, editing and deleting student profiles:**
- **Method:** `POST`, `PUT`, `DELETE`
- **URL:** *`/admin/students`*
- **Description:** Add, edit, and delete student profiles

**View the list of students and details of each profile:**
- **Method:** `GET`
- **URL:** *`/admin/students`*
- **Description:** View the list of students and details of each profile

**Create, edit, and delete courses:**
- **Method:** `POST`, `PUT`, `DELETE`
- **URL:** *`/admin/subjects`*
- **Description:** Create, edit and delete courses

**Adding, editing, and deleting teacher profiles:**
- **Method:** `POST`, `PUT`, `DELETE`
- **URL:** *`/admin/teachers`*
- **Description:** Add, edit, and delete teacher profiles

**View the list of teachers and details of each profile:**
- **Method:** `GET`
- **URL:** *`/admin/teachers`*
- **Description:** View the list of teachers and details of each profile

**Generate and view student progress reports:**
- **Method:** `GET`
- **URL:** *`/admin/reports/grades`*
- **Description:** Generate and view student grades reports

**Create, edit, and delete faculties:**
- **Method:** `POST`, `PUT`, `DELETE`
- **URL:** *`/admin/faculties`*
- **Description:** Create, edit and delete faculties

**Create, edit, and delete specialties:**
- **Method:** `POST`, `PUT`, `DELETE`
- **URL:** *`/admin/specialties`*
- **Description:** Create, edit and delete specialties

**Sending warning messages to all users:**
- **Method:** `POST`
- **URL:** *`/admin/notifications`*
- **Description:** Sending warning messages to all users regarding actions with the system
