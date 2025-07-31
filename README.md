# 🏥 Appointment, Diagnosis, and Invoicing System for Individual Clinics

> ℹ️ **Note:** If login requires a verification code, please contact [zheng.wang0911@gmail.com](mailto:zheng.wang0911@gmail.com)

This project implements a real-world **PaaS-based system** for a small branch clinic of a large healthcare group using **Salesforce Force.com**.  
It solves key operational problems—**patient registration, appointment booking, medical diagnosis, referral, and invoicing**—in a cost-effective, scalable, and automated manner.

---

## 🔧 Project Problem

Clinic A is one of several small clinics operated by a large group. It offers basic GP consultation, referral, and treatment services, but lacks standalone finance and HR departments.

The clinic needed a lightweight, integrated solution to:

- Manage patient registration and appointment booking  
- Streamline diagnosis and referral workflows  
- Automate invoice creation and apply patient discounts  
- Assign role-specific access for Admin, Doctor, Duty Manager, and Group Manager  
- Support workflow automation, validation, and approval without writing custom code  

---

## 📊 System Analysis & Data Modeling

- **Dataflow Mapped**: From patient entry to appointment, diagnosis, and billing  
- **Entity Design**: `Patient`, `Appointment`, `Diagnosis`, `Referral`, `Invoice`, `DiscountApproval`  
- **Relationships**:
  - `Lookup`: Patient ↔ Appointment
  - `Master-Detail`: Appointment ↔ Diagnosis, Invoice ↔ Discount Approval
- **Validation Rules**: Enforced for fields such as Medicare number, DOB, appointment time, and invoice amount

---

## 🧩 System Features

| Module                | Functionality                                                                 |
|-----------------------|------------------------------------------------------------------------------|
| 🧑‍⚕️ Patient & Appointment | Admin registers patient, books doctor appointment, with validation enforced     |
| 📋 Diagnosis & Referral   | Doctor completes diagnosis; may issue referral with auto-filled information |
| 💰 Invoicing & Discount   | Admin generates invoice, discount approval flow triggered automatically     |
| 📥 Discount Workflow      | Task-based approval for Duty or Group Manager based on discount level       |
| 📬 Notifications          | Email alerts & task assignments auto-generated for each step                |

---

## 🔐 Role-Based Access Control

- **Admin**: Full access to patient, appointment, and invoice modules; read-only for discount info  
- **Doctor**: Access to appointments, diagnosis records, and referrals  
- **Duty Manager**: Approves standard discounts; read access to all modules  
- **Group Manager**: Approves 100% discounts; oversees multi-clinic data  

---

## 🔄 Workflow Automation (No-Code)

> Powered by Salesforce Flow

- New patient triggers review task and confirmation email  
- Appointment creation assigns tasks to the Admin and the Doctor  
- Diagnosis completion triggers invoice task for Admin  
- Discounts trigger email & task notification to the appropriate manager  

---

## 📺 Prototype UI (Force.com)

- Customized homepage tabs: *Create New*, *Calendar*, *Tasks*, *Approvals*  
- Role-based layout and tab visibility  
- Validation built into record screens for real-time data enforcement  
