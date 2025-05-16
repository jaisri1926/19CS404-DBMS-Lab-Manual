# Experiment 1: Entity-Relationship (ER) Diagram

## 🎯 Objective:
To understand and apply the concepts of ER modeling by creating an ER diagram for a real-world application.

## 📚 Purpose:
The purpose of this workshop is to gain hands-on experience in designing ER diagrams that visually represent the structure of a database including entities, relationships, attributes, and constraints.

---

## 🧪 Choose One Scenario:

### 🔹 Scenario 1: University Database
Design a database to manage students, instructors, programs, courses, and student enrollments. Include prerequisites for courses.

**User Requirements:**
- Academic programs grouped under departments.
- Students have admission number, name, DOB, contact info.
- Instructors with staff number, contact info, etc.
- Courses have number, name, credits.
- Track course enrollments by students and enrollment date.
- Add support for prerequisites (some courses require others).

---

### 🔹 Scenario 2: Hospital Database
Design a database for patient management, appointments, medical records, and billing.

**User Requirements:**
- Patient details including contact and insurance.
- Doctors and their departments, contact info, specialization.
- Appointments with reason, time, patient-doctor link.
- Medical records with treatments, diagnosis, test results.
- Billing and payment details for each appointment.

---

## 📝 Tasks:
1. Identify entities, relationships, and attributes.
2. Draw the ER diagram using any tool (draw.io, dbdiagram.io, hand-drawn and scanned).
3. Include:
   - Cardinality & participation constraints
   - Prerequisites for University OR Billing for Hospital
4. Explain:
   - Why you chose the entities and relationships.
   - How you modeled prerequisites or billing.

# ER Diagram Submission - Student Name

## Scenario Chosen:
University / Hospital (choose one)

## ER Diagram:


## Entities and Attributes:
Student: Reg no, Student name, Department
Faculty: Faculty Id, Faculty name, Dept
Course: Course code, Course name, Department
ERP: Faculty name, Course details, Slots
Login: Login user, User_id, Password
...

## Relationships and Constraints:
Enroll (Student–Course): Many-to-Many, Partial Participation
Teaches (Faculty–Student): Many-to-Many, Partial Participation
Assign (Course–ERP): One-to-Many, Total Participation from Course
Has (Login–ERP): One-to-One, Total Participation


...

## Extension (Prerequisite / Billing):
-Prerequisite can be modeled using a recursive relationship on the Course entity.
Billing can be introduced as a separate entity linked with Student and Course via a PaysFor relationship, with attributes like Amount and Payment Status.

## Design Choices:
Separate entities were used for better clarity and modularity.
The ERP entity was introduced as a central system managing course, faculty, and scheduling data.
Relationships reflect real-world academic interactions (e.g., enrollment, teaching).
Login entity ensures user-specific access control to ERP.
## RESULT
The concepts of Entity-Relationship (ER) modeling were understood and successfully applied by creating an ER diagram for a real-world application. The diagram effectively represents entities such as Student, Faculty, Course, ERP, and Login, along with their attributes and relationships. This ER model demonstrates the structure and interactions within an academic ERP system.
