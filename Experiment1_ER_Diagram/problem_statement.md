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

# ER Diagram Submission - Eesha Ranka

## Scenario Chosen:
Hospital Database

## ER Diagram:

![image](https://github.com/user-attachments/assets/0d0fdc4d-ca02-440d-b49b-d83e00ef81ef)


## Entities and Attributes:
```
- Patient -  ID, Name, Phoneno, Gender, DOB, Address
- Doctor - ID,Name,Phone,Specialist, Workschedule
- Department - ID, Name,Head
- Appointment - ID,Date,Time,Reason
- MedicalRecord - ID,Testresults,treatment,medications
- Billing - ID,Amt,Status,
- Payment - ID, paidamt, Date,Method
```
  
## Relationships and Constraints:
```
1.Patient consults Doctor 
Cardinality: Many-to-Many (M:N) 
Participation: Total participation from Patient side, partial from Doctor side

2. Doctor manages Department
Cardinality: One-to-One (1:1) or One-to-Many (1:N)
Participation: Partial participation from Doctor side

3. Patient makes Appointment
Cardinality: One-to-Many (1:N)
Participation: Total participation from Appointment side

4.Doctor enters MedicalRecord
Cardinality: One-to-Many (1:N)
Participation: Total participation from MedicalRecord side

5.Appointment generates MedicalRecord
Cardinality: One-to-One (1:1)
Participation: Total participation from both Appointment and MedicalRecord sides

6.Billing has Appointment
Cardinality: One-to-One (1:1) or One-to-Many (1:N)
Participation: Total participation from Billing side

7.Payment PaidBy Billing
Cardinality: One-to-One (1:1)
Participation: Total participation from Payment side
```

## Extension (Prerequisite / Billing):
```
Billing Modeling Explanation:
Billing entity is associated with the Appointment (via "Has" relationship).
Each appointment results in Billing, where:
    Billing keeps track of the total Amount (Amt) and Status (whether paid or unpaid).
Billing has a connection with Payment through "PaidBy" relationship:
    Payment stores paid amount, payment date, and method (cash, card, etc.).
Payment is optional until the patient pays.
Constraints ensure:
Every billing must be associated with exactly one payment record.
Status is updated based on the payment completion (if full paid, status is "Paid"; else "Pending").

```

## Design Choices:
```
Entities like Patient, Doctor, Department, Appointment, MedicalRecord, Billing, and Payment were chosen because they represent the core operations of a hospital — handling patients, services, and payments.

Relationships like Consult, Manages, Makes, Enters, Generates, Has, and PaidBy model the real-world interactions between patients, doctors, appointments, medical records, and billing/payment processes.

Assumptions made:

Every appointment generates a medical record.
Billing is always linked to an appointment.
Each billing must have exactly one payment.
Departments must have a managing doctor.
Patients must consult at least one doctor, but doctors may or may not have patients yet.
```


## RESULT
The ER diagram for the Hospital Management System was successfully created, identifying key entities, attributes, and relationships.
