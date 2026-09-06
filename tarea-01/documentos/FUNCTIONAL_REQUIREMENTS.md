# Functional Requirements

## Introduction

This document defines the functional requirements implemented for the carpet and sofa cleaning service administration web application. Each requirement is derived from the user stories created in Jira and describes the expected behavior of the system from a functional perspective.

## Functional Requirements

| ID    | Requirement                                                                                          | Priority | Related Jira Story |
|-------|------------------------------------------------------------------------------------------------------|----------|--------------------|
| FR-01 | The system shall allow customers to upload photos of carpets or sofas before requesting the service. | High     | EC-29              |
| FR-02 | The system shall allow staff members to complete an inspection checklist before starting the cleaning service. | High | EC-30         |
| FR-03 | The system shall allow staff members to confirm the pickup of carpets or sofas from the customer's location. | High | EC-31          |
| FR-04 | The system shall allow administrators to manage the inventory of cleaning supplies.                  | High     | EC-32              |
| FR-05 | The system shall notify administrators when cleaning supplies reach the minimum stock level.          | High     | EC-33              |
| FR-06 | The system shall allow administrators to register and track maintenance activities for cleaning equipment. | High | EC-34           |
| FR-07 | The system shall allow customers to configure their preferred notification method.                   | High     | EC-35              |

## Requirement Details

**FR-01 – Upload Item Photos**
Customers must be able to attach one or more photos of the items to be cleaned prior to submitting a service request. This allows staff to assess the condition of the carpet or sofa before scheduling the pickup.

**FR-02 – Service Inspection Checklist**
Staff members must complete a standardized checklist when inspecting items upon arrival. This ensures every service follows a consistent quality process and provides a documented record of the item's initial state.

**FR-03 – Pickup Confirmation**
Staff members must register a confirmation event when carpets or sofas are collected from the customer's premises. This creates an auditable timestamp that initiates the service tracking workflow.

**FR-04 – Cleaning Supplies Inventory**
Administrators must be able to add, update, and remove cleaning supply records within the system. Maintaining an accurate inventory prevents service interruptions caused by missing or insufficient materials.

**FR-05 – Low Supply Alert**
The system must automatically trigger a notification to administrators whenever a supply item falls at or below its defined minimum threshold. This proactive alert enables timely restocking and avoids operational delays.

**FR-06 – Cleaning Equipment Maintenance**
Administrators must be able to log maintenance events for each piece of cleaning equipment, including dates, type of service, and responsible technician. Tracking this history helps prevent unexpected equipment failures.

**FR-07 – Customer Notification Preferences**
Customers must be able to choose how they receive communications from the system, such as email or SMS. Respecting customer preferences improves satisfaction and ensures relevant updates are delivered through the desired channel.

## Summary

These functional requirements directly support the user stories created in Jira (EC-29 through EC-35) and maintain full consistency with the scope defined for the project. Together, they cover customer-facing features, staff operational workflows, and administrative management capabilities required to run the carpet and sofa cleaning service effectively.
