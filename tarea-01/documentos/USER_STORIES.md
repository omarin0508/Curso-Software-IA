# User Stories

## Introduction

This document contains the user stories implemented for the web application for carpet and sofa cleaning service management. These user stories correspond to the functionalities registered in Jira and describe the expected value, users, and acceptance criteria for each backlog item.

---

# EC-29 — Upload Item Photos

As a customer,

I want to upload photos of my carpet or sofa before requesting the cleaning service,

so that the cleaning staff can evaluate the condition of the item before providing the service.

Acceptance Criteria

AC-01
The system must allow customers to upload up to five photos for each service request.

AC-02
The system must accept JPG, JPEG, and PNG image formats.

AC-03
Uploaded photos must remain associated with the corresponding service request until the service is completed.

---

# EC-30 — Service Inspection Checklist

As a staff member,

I want to complete a service inspection checklist before starting the cleaning process,

so that I can verify the condition of the carpet or sofa and record relevant observations.

Acceptance Criteria

AC-01
The system must provide a predefined inspection checklist before the service begins.

AC-02
The staff member must be able to mark each inspection item as completed.

AC-03
The completed checklist must be stored with the corresponding service request.

---

# EC-31 — Pickup Confirmation

As a staff member,

I want to confirm when a carpet or sofa has been picked up from the customer's location,

so that the customer and the company can track the service process accurately.

Acceptance Criteria

AC-01
The system must allow the staff member to confirm the pickup of the item.

AC-02
The pickup date and time must be recorded automatically.

AC-03
The pickup confirmation must be associated with the corresponding service request.

---

# EC-32 — Cleaning Supplies Inventory

As an administrator,

I want to manage the inventory of cleaning supplies,

so that I can ensure the necessary products are available before each service.

Acceptance Criteria

AC-01
The system must allow the administrator to register cleaning supplies.

AC-02
The system must allow updating the available quantity of each cleaning supply.

AC-03
The inventory information must be available for consultation at any time.

---

# EC-33 — Low Supply Alert

As an administrator,

I want to receive an alert when a cleaning supply reaches a low stock level,

so that I can restock it before it affects scheduled services.

Acceptance Criteria

AC-01
The system must allow a minimum stock level to be defined for each cleaning supply.

AC-02
The system must generate an alert when the available quantity is equal to or lower than the defined minimum level.

AC-03
The alert must identify the cleaning supply and its current available quantity.

---

# EC-34 — Cleaning Equipment Maintenance

As an administrator,

I want to schedule and record maintenance for cleaning equipment,

so that the equipment remains in good working condition and service quality is maintained.

Acceptance Criteria

AC-01
The system must allow the administrator to register maintenance activities for cleaning equipment.

AC-02
The system must record the maintenance date and the equipment involved.

AC-03
The maintenance history must be available for future reference.

---

# EC-35 — Customer Notification Preferences

As a customer,

I want to choose how I receive service notifications,

so that I can be informed about my service through my preferred communication method.

Acceptance Criteria

AC-01
The system must allow the customer to select one or more notification methods (email or SMS).

AC-02
The selected notification preferences must be saved to the customer's profile.

AC-03
The system must use the selected notification method when sending service updates.

---

## Summary

These user stories were developed to complement the project backlog and maintain consistency with the functional requirements and the tickets registered in Jira.
