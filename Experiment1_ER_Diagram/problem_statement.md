# Experiment 1: Entity-Relationship (ER) Diagram
## REG NO 212222060086
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

# ER Diagram Submission - Jaisri J

## Scenario Chosen:
University / Hospital (choose one)

## ER Diagram:
![Screenshot (4)](https://github.com/user-attachments/assets/e38878cb-3120-417a-b347-2cb9e314475a)


## Entities and Attributes:
Patient: Name, Age, Gender, Address, Mobile_no

Doctor: Doc_Id, Name, Mobile_no

Treatment: Treatment_name, Cost

Test: Test_no, Test_id, Test Name, Description

Illness: Illness Name
...

## Relationships and Constraints:
Consults (Patient–Doctor): Many-to-Many, Partial Participation

Undergoes (Patient–Treatment): Many-to-Many, Partial Participation

Performs (Doctor–Treatment): Many-to-Many, Partial Participation

Prescribes (Doctor–Test): One-to-Many, Partial Participation

Diagnosed_with (Patient–Illness): Many-to-Many, Partial Participation
...

## Extension (Prerequisite / Billing):
Billing can be added as a separate entity linked to Patient and Treatment/Test, including attributes like Bill_ID, Amount, Payment Status.

Prerequisite may not apply directly but can be modeled if treatments/tests depend on other tests.

## Design Choices:
Separated entities based on hospital domain concepts: Patient, Doctor, Treatment, Test, Illness for clarity.

Many-to-many relationships capture complex real-world interactions, like patients consulting multiple doctors or undergoing multiple treatments.

Test entity includes detailed attributes for better diagnostic information.

Illness entity helps in categorizing and recording patient diagnoses.
## RESULT
The ER model for Hospital Management effectively captures core entities, their attributes, and the complex relationships among patients, doctors, treatments, tests, and illnesses. This design reflects realistic hospital operations and provides a solid foundation for database implementation and management.


