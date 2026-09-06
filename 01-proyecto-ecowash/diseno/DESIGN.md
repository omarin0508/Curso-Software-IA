# EcoWash - UI/UX Design Specification

Version: 1.0

---

# Overview

**EcoWash** is a web application for managing eco-friendly vehicle washing services. The platform allows customers to register, select a vehicle wash service, review service details, calculate costs, choose a payment method, manage requests, receive notifications, and view their service history.

The system supports two main roles:

- Customer
- Administrator

The design should communicate:

- Sustainability
- Cleanliness
- Trust
- Simplicity
- Operational clarity
- Professional service management

The interface should remain modern, calm, and efficient. Avoid flashy elements, excessive gradients, and unnecessary animations.

The experience should feel comparable to:

- Airbnb
- Stripe Dashboard
- Linear
- Notion
- Shopify Admin

---

# Product Vision

EcoWash should make eco-friendly vehicle washing easy to request, manage, and track. Customers should understand available services, prices, schedules, payment options, and request status without needing assistance. Administrators should be able to manage service demand, staff availability, coverage zones, pricing, request status, and completed service reports from a clear operational interface.

The product vision is to provide a trustworthy digital experience for coordinating sustainable vehicle washing services while keeping every interaction simple, transparent, and responsive.

---

# Design Philosophy

EcoWash should prioritize clarity over decoration. Every page should help users complete a practical task, such as booking a wash, reviewing a request, assigning staff, updating service pricing, or checking completed service activity.

The design should be:

- Minimal
- Modern
- Spacious
- Consistent
- Mobile-first
- Accessible
- Trustworthy
- Environmentally conscious

The interface should avoid visual noise and use simple layouts, clear labels, predictable controls, and visible feedback for important actions.

---

# Brand Identity

EcoWash should feel clean, responsible, and dependable. The brand identity should support the concept of sustainable vehicle care without relying on decorative excess.

Brand attributes:

- Fresh
- Reliable
- Practical
- Environmentally aware
- Service-oriented
- Transparent

Visual direction:

- Use green tones to reinforce sustainability.
- Use light backgrounds to communicate cleanliness.
- Use simple iconography related to vehicles, water, scheduling, staff, payments, and reports.
- Use soft shadows and rounded corners to keep the interface approachable.
- Keep dashboards structured and efficient for repeated administrative use.

---

# Customer Experience Goals

Customers should be able to:

- Register securely.
- Log in securely.
- Recover a forgotten password.
- Update profile information.
- Update customer information securely.
- Select a vehicle washing service.
- View service details before booking.
- Calculate the service cost.
- View available time slots.
- Choose a payment method.
- Confirm a service request.
- Receive a generated receipt.
- Cancel a request when allowed.
- Reschedule a request when allowed.
- View request history.
- Rate a completed service.
- Submit feedback.
- Receive relevant notifications.

The customer experience should reduce uncertainty by making prices, schedules, request status, payment details, and service outcomes visible at the right moment.

---

# Administrator Experience Goals

Administrators should be able to:

- Manage pending service requests.
- Update request status.
- Assign staff to service requests.
- Manage staff availability.
- View available time slots.
- Manage the service catalog and pricing.
- Manage coverage zones.
- Review completed service reports.
- Monitor request activity from the dashboard.

The administrator experience should support operational speed, accuracy, and accountability. Interfaces should be organized for scanning, filtering, assigning, updating, and reporting.

---

# Information Architecture

Customer navigation:

- Dashboard
- Book Service
- My Requests
- Request History
- Notifications
- Profile
- Settings
- Logout

Administrator navigation:

- Dashboard
- Pending Requests
- Schedule
- Staff Assignments
- Staff Availability
- Services and Pricing
- Coverage Zones
- Completed Reports
- Customers
- Notifications
- Settings
- Logout

Authentication pages:

- Registration
- Login
- Password Recovery

Shared pages:

- Request Details
- Receipt
- Error Pages

---

# Trust and Transparency Principles

EcoWash should make service information clear before a customer confirms a request.

The interface should always show:

- Selected service
- Service details
- Estimated cost
- Selected date and time slot
- Payment method
- Current request status
- Receipt information after confirmation

For operational actions, administrators should see enough context to make accurate decisions, including request details, customer information, coverage zone, assigned staff, staff availability, and current status.

Destructive or disruptive actions, such as cancellation or major request changes, should require confirmation.

---

# Business Rules

The interface must support the following business rules:

- Customers must register or log in before creating a service request.
- Customers must be able to recover access through password recovery.
- Customers must be able to update their profile and customer information securely.
- Customers must select a service before viewing the final cost.
- Cost calculation must be shown before request confirmation.
- Customers must select a payment method before confirming a request.
- A receipt must be generated after a confirmed request.
- Customers must be able to cancel a request when cancellation is available.
- Customers must be able to reschedule a request when rescheduling is available.
- Customers must be able to view their request history.
- Customers must be able to rate and provide feedback for completed services.
- Customers must receive notifications about relevant request activity.
- Administrators must be able to manage pending requests.
- Administrators must be able to update request status.
- Administrators must be able to assign staff to requests.
- Administrators must be able to manage staff availability.
- Available time slots must be visible during scheduling.
- Administrators must be able to manage services and pricing.
- Administrators must be able to manage coverage zones.
- Administrators must be able to review completed service reports.

---

# Color Palette

## Background

Primary background:

```
#f5f4f0
```

Use this color for:

- Application background
- Page sections
- Dashboard background

---

## Primary Color

```
#0c3024
```

Use this color for:

- Primary buttons
- Sidebar
- Navigation
- Icons
- Active states

---

## Primary Button Text

```
#c1eeb3
```

Use this color only for text inside dark buttons.

---

## Text Color

```
#025d3e
```

Use this color for:

- Headings
- Paragraphs
- Labels
- Links
- Icons

---

## Neutral Colors

Border:

```
#d8ddd7
```

Cards:

```
#ffffff
```

Muted text:

```
#6f7d76
```

Placeholder:

```
#95a19a
```

Divider:

```
#e8ebe7
```

---

## Status Colors

Success:

```
#4CAF50
```

Warning:

```
#F4B400
```

Danger:

```
#D93025
```

Info:

```
#2196F3
```

---

# Typography

Use:

```
Poppins
```

Fallback:

```
sans-serif
```

Hierarchy:

H1:

- 36px
- Bold

H2:

- 30px
- SemiBold

H3:

- 24px
- SemiBold

H4:

- 20px
- Medium

Body:

- 16px
- Regular

Small:

- 14px

Caption:

- 12px

Line height:

- 150%

Never justify text.

---

# Border Radius

Buttons:

- 10px

Cards:

- 16px

Inputs:

- 10px

Dialogs:

- 20px

Badges:

- 999px

---

# Shadows

Cards:

```
0 4px 16px rgba(0,0,0,.06)
```

Dialogs:

```
0 10px 40px rgba(0,0,0,.12)
```

Dropdowns:

```
0 6px 18px rgba(0,0,0,.10)
```

---

# Spacing

Use an 8px spacing system.

Allowed spacing values:

```
4
8
12
16
20
24
32
40
48
64
80
96
```

---

# Buttons

## Primary Button

Background:

```
#0c3024
```

Text:

```
#c1eeb3
```

Height:

- 48px

Padding:

- 16px 24px

Hover:

- Slightly lighter background

Active:

- Slightly darker background

Radius:

- 10px

Usage examples:

- Book Service
- Confirm Request
- Save Changes
- Assign Staff
- Generate Report

---

## Secondary Button

Background:

- Transparent

Border:

- 1px solid #0c3024

Text:

- #025d3e

Usage examples:

- View Details
- Reschedule
- Download Receipt

---

## Text Button

Background:

- Transparent

Border:

- None

Text:

- #025d3e

Usage examples:

- Cancel
- Edit
- Forgot Password

---

# Inputs

Height:

- 48px

Background:

- White

Border:

- 1px solid #d8ddd7

Focus:

- 2px outline using:

```
#0c3024
```

Error:

- Border using:

```
#D93025
```

Labels must always appear above fields.

Include helper text when appropriate, especially for password recovery, secure customer information updates, payment method selection, and scheduling.

---

# Cards

Cards are used for:

- Vehicle wash services
- Active requests
- Scheduled requests
- Completed requests
- Customer information
- Staff assignments
- Coverage zones
- Dashboard metrics
- Completed service reports

Style:

- Background: White
- Radius: 16px
- Padding: 24px
- Shadow: Soft

---

# Icons

Use outline icons.

Preferred library:

- Lucide

Examples:

- Car
- Droplets
- Calendar
- Clock
- User
- Users
- Map Pin
- Receipt
- Credit Card
- Bell
- Check
- X
- Rotate Ccw
- Star
- Settings
- Search
- Chart
- Shield
- Menu

---

# Layout

Maximum content width:

- 1440px

Desktop:

- Sidebar + content
- Sidebar width: 280px
- Content: Flexible

Mobile:

- Top navigation
- Hamburger menu
- Bottom spacing: 32px

Layouts should support quick scanning of request status, available time slots, service prices, staff assignment, and completed service activity.

---

# Navigation

Customer sidebar items:

- Dashboard
- Book Service
- My Requests
- Request History
- Notifications
- Profile
- Settings
- Logout

Administrator sidebar items:

- Dashboard
- Pending Requests
- Schedule
- Staff Assignments
- Staff Availability
- Services and Pricing
- Coverage Zones
- Completed Reports
- Customers
- Notifications
- Settings
- Logout

Active items should use:

- Dark background
- Rounded shape

---

# Authentication

Authentication pages should be simple, secure, and direct.

Registration should include:

- Name
- Email
- Phone
- Password
- Confirm password
- Primary action to create an account

Login should include:

- Email
- Password
- Primary action to sign in
- Password recovery link

Password recovery should include:

- Email input
- Recovery instructions
- Confirmation feedback after submission

All authentication flows should use clear validation, visible errors, and secure wording.

---

# Profile Management

Customers should be able to update their profile and customer information securely.

Profile sections:

- Personal information
- Contact information
- Password
- Saved customer details

Primary actions:

- Save Changes
- Update Password

The interface should confirm successful updates and clearly explain validation errors.

---

# Dashboard

Customer dashboard:

- Greeting
- Quick statistics
- Upcoming scheduled service
- Active request status
- Recent requests
- Recommended next action
- Notifications summary

Administrator dashboard:

- Pending requests
- Requests scheduled today
- Completed services
- Staff assignments
- Staff availability summary
- Coverage zone activity
- Revenue summary
- Recent activity
- Completed service report summary

Dashboards should emphasize the most time-sensitive actions first.

---

# Homepage

Hero section:

- Visual direction: Clean vehicle wash imagery with an eco-friendly tone
- Headline: Eco-Friendly Vehicle Washing Made Simple
- Subtitle: Book, manage, and track vehicle wash services from one clean platform.
- CTA: Book a Wash
- Secondary CTA: View Services

Following sections:

- Benefits
- How It Works
- Popular Wash Services
- Coverage Zones
- Customer Feedback
- FAQ
- Footer

The homepage should explain the service clearly and guide customers toward booking without overwhelming them.

---

# Booking Flow

Step 1:

- Select vehicle wash service

Step 2:

- View service details
- Review included service information
- Confirm selected service

Step 3:

- View available time slots
- Choose date
- Choose time slot

Step 4:

- Calculate cost
- Review estimated total

Step 5:

- Select payment method:
  - Cash
  - SINPE
  - Card

Step 6:

- Confirm request
- Show unique request number
- Show estimated cost
- Show selected payment method
- Show schedule summary
- Generate receipt

The booking flow should highlight the current step and allow customers to review important details before confirmation.

---

# Service Cards

Each vehicle wash service card contains:

- Service icon or illustration
- Service name
- Short description
- Estimated duration
- Starting price
- Included service details
- View Details button
- Book Service button

Service cards should help customers compare available options quickly.

---

# Service Catalog

The service catalog presents all available vehicle washing services.

Customer-facing catalog information:

- Service name
- Description
- Estimated duration
- Starting price
- Service details
- Availability status

Administrator catalog management:

- Create service
- Read service details
- Update service
- Deactivate service
- Manage pricing
- Manage service duration
- Manage service status

Pricing information should be clear, current, and visible before booking.

---

# Request Details

Show:

- Request number
- Status badge
- Selected service
- Service details
- Date
- Time slot
- Coverage zone
- Assigned staff
- Estimated price
- Payment method
- Receipt access
- Customer comments
- Timeline
- Cancellation action when available
- Rescheduling action when available
- Rating and feedback action after completion

Request details should provide a complete view of the service request for both customers and administrators, adapted to each role.

---

# Scheduling

Scheduling should make available time slots easy to understand.

Customer scheduling view:

- Available dates
- Available time slots
- Selected date and time
- Rescheduling option when available

Administrator scheduling view:

- Daily schedule
- Pending requests
- Assigned staff
- Staff availability
- Time-slot availability
- Request status

Scheduling should prevent confusion by clearly distinguishing available, selected, unavailable, and completed time slots.

---

# Staff Assignment

Administrators should be able to assign staff to service requests based on availability.

Assignment information:

- Request number
- Customer
- Selected service
- Coverage zone
- Date
- Time slot
- Staff availability
- Assigned staff
- Current status

The interface should support pending request management, staff assignment, and request status updates from the same operational context.

---

# Payment Methods

Customers should select a payment method before confirming a request.

Supported payment methods:

- Cash
- SINPE
- Card

Payment selection should clearly show the selected method in the booking summary and request details.

---

# Receipts

A receipt must be generated after a confirmed request.

Receipt information:

- Receipt number
- Request number
- Customer
- Selected service
- Date
- Time slot
- Estimated cost
- Payment method
- Request status

Customers should be able to access the receipt from the confirmation screen and request details.

---

# Request History

Customers should be able to view previous and current service requests.

Request history should include:

- Request number
- Service name
- Date
- Status
- Estimated cost
- Payment method
- Receipt access when available
- Rating status when applicable

Filtering or search may be used where the request list becomes long.

---

# Cancellation

Customers should be able to cancel a request when cancellation is available.

Cancellation experience:

- Show the selected request.
- Explain that cancellation affects the scheduled service.
- Require confirmation before cancellation.
- Show success or error feedback after the action.
- Update the request status.

Cancellation should never happen without explicit confirmation.

---

# Rescheduling

Customers should be able to reschedule a request when rescheduling is available.

Rescheduling experience:

- Show the current date and time slot.
- Show available new time slots.
- Require confirmation before applying the change.
- Update the request details after confirmation.
- Notify the customer about the updated schedule.

Rescheduling should keep the selected service, cost information, and payment method visible for context.

---

# Ratings and Feedback

Customers should be able to rate and provide feedback for completed services.

Feedback fields:

- Rating
- Optional comments

Feedback should be available only after a service is completed. The interface should confirm when feedback has been submitted.

---

# Completed Service Reports

Administrators should be able to review completed service reports.

Reports should include:

- Completed services
- Completion dates
- Assigned staff
- Service types
- Coverage zones
- Revenue summary
- Customer ratings
- Customer feedback

Reports should support operational review and service quality analysis without introducing unsupported automation.

---

# Coverage Zones

Coverage zones define where EcoWash services are available.

Customer-facing coverage information:

- Available service zones
- Zone selection during booking when required
- Coverage zone shown in request details

Administrator coverage management:

- View coverage zones
- Add coverage zone
- Edit coverage zone
- Deactivate coverage zone

Coverage zones should be presented clearly so customers understand whether service is available for their area.

---

# Status Badges

Use the following status badge colors:

- Pending: Yellow
- Assigned: Blue
- Completed: Green
- Cancelled: Red

Status badges should appear in dashboards, request details, request history, tables, and administrator workflows.

---

# Administrator Pages

## Customers

Include:

- Table
- Search
- Filters
- Pagination
- Customer details
- Secure customer information review
- Actions:
  - Edit
  - Deactivate

---

## Services

Include:

- Service catalog
- CRUD
- Pricing
- Duration
- Details
- Status

---

## Assignments

Include:

- Calendar view
- Daily view
- Pending requests
- Staff availability
- Available time slots
- Staff assignment
- Request status updates

---

## Reports

Include:

- Completed service reports
- Revenue
- Completed services
- Staff assignments
- Coverage zones
- Customer ratings
- Customer feedback
- Date range
- Export PDF
- Export Excel

---

# Tables

Tables should include:

- Rounded corners
- Alternating row hover
- Sticky header
- Search bar
- Filters
- Pagination
- Responsive behavior

Use tables for:

- Pending requests
- Customers
- Service catalog
- Staff availability
- Staff assignments
- Coverage zones
- Completed service reports
- Request history

---

# Notifications

Use toast notifications and notification lists for important request activity.

Placement and behavior:

- Top right for toast notifications
- Auto dismiss after 4 seconds
- Persistent notification history in the notifications page

Notification types:

- Success
- Warning
- Info
- Danger

Customer notification examples:

- Request confirmed
- Request status updated
- Request cancelled
- Request rescheduled
- Receipt generated
- Feedback submitted

Administrator notification examples:

- New pending request
- Staff assigned
- Request status updated
- Service completed

---

# Dialogs

Dialog types:

- Confirmation
- Cancel request
- Reschedule request
- Assign staff
- Update request status
- Generate receipt
- Submit feedback
- Deactivate service
- Deactivate coverage zone

Style:

- Radius: 20px

Dialogs should clearly explain the action and provide a safe way to cancel before applying changes.

---

# Animations

Keep animations subtle.

Maximum duration:

- 250ms

Use:

- Fade
- Scale
- Slide

Avoid bouncing animations.

Animations should support feedback, navigation, and state changes without distracting from service management tasks.

---

# Accessibility

Follow WCAG AA guidelines.

Requirements:

- Minimum contrast ratio
- Keyboard navigation
- Visible focus indicators
- Screen reader labels
- Large click targets
- Minimum touch target: 44x44px

Accessibility should apply to authentication, booking, scheduling, request management, tables, dialogs, notifications, and reports.

---

# Responsive Breakpoints

Mobile:

- 360px

Tablet:

- 768px

Laptop:

- 1024px

Desktop:

- 1280px

Large desktop:

- 1536px

The customer experience should remain easy to complete on mobile screens. Administrator pages should remain readable and usable across tablet and desktop layouts.

---

# Components Needed

- Navigation bar
- Sidebar
- Footer
- Hero
- Authentication forms
- Service card
- Service catalog
- Booking wizard
- Cost summary
- Time-slot selector
- Request timeline
- Schedule calendar
- Staff assignment panel
- Staff availability table
- Statistic cards
- Tables
- Status badges
- Toast notifications
- Notification dropdown
- Modal
- Drawer
- Accordion
- FAQ
- Profile card
- Search bar
- Date picker
- Pagination
- Breadcrumb
- Receipt view
- File download button
- Report charts
- Rating input
- Feedback form
- Empty states
- Loading skeletons

---

# Empty States

Empty states should include:

- Illustration
- Friendly message
- Primary action

Examples:

- No requests yet
- No available time slots
- No notifications
- No services available
- No completed reports
- No coverage zones

Empty states should guide users toward the next valid action without implying unavailable functionality.

---

# Error Pages

Include the following error pages:

- 403
- 404
- 500

Use friendly illustrations and concise recovery actions.

Examples:

- Return to dashboard
- Go back
- Try again

---

# General UX Rules

- Never overload screens.
- Keep forms short and split them into logical steps.
- Always display feedback after user actions.
- Prevent accidental destructive actions with confirmation dialogs.
- Show loading states for asynchronous operations.
- Highlight the current step in multi-step processes.
- Use consistent spacing and typography throughout the application.
- Make all primary actions immediately visible.
- Ensure every important action is achievable within three clicks whenever possible.
- Design all pages to be fully responsive and touch-friendly.
- Maintain visual consistency between Customer and Administrator interfaces while adapting available functionality according to each role.
- Keep service names, request statuses, payment methods, and coverage zone labels consistent across the application.
- Show cost, schedule, and payment information before final request confirmation.
- Keep administrator workflows optimized for scanning, filtering, assigning, and updating requests.
