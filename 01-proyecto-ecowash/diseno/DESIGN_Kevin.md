# ECOWASH — DESIGN.md

**Version:** 2.0 — Unified Design Specification

## 1. Product Overview

ECOWASH is a responsive web application for a professional home cleaning service focused on carpets, sofas, mattresses, and related upholstered household items.

The experience should communicate:
- Cleanliness
- Trust
- Professionalism
- Freshness
- Simplicity
- Eco-conscious service

The application serves two primary roles:
1. Customer
2. Administrator

The UI must be easy to understand for users with little or no technical experience. A customer should be able to complete a service request in under 5 minutes.

---

## 2. Brand Intelligence

### Brand Philosophy

ECOWASH believes that cleanliness goes beyond appearance.

A clean experience creates confidence. A clean interface reduces stress. A clean workflow saves time. Technology should quietly support the customer instead of demanding attention.

Every interaction should feel natural, lightweight, and human.

### Brand Personality

ECOWASH communicates like a friendly professional.

The product should feel:
- Calm
- Honest
- Helpful
- Responsible
- Modern
- Approachable
- Organized
- Detail-oriented

The product should never feel:
- Aggressive
- Loud
- Cold
- Overdesigned
- Childish
- Overly futuristic
- Unnecessarily corporate

### Core Design Principles

#### 1. Simplicity First

Every screen should have one clear purpose. Remove information or controls that do not help the user complete that purpose.

#### 2. Freshness

Use generous whitespace and avoid compressed layouts. The interface should feel breathable, clean, and visually calm.

#### 3. Trust Through Clarity

Prices, dates, addresses, payment methods, service details, and request status must remain visible at the moment they matter.

#### 4. Human Experience

Users should always understand:
- Where they are
- What they are doing
- What happens next

#### 5. Attention to Detail

Spacing, typography, alignment, feedback, validation, and consistency must reinforce confidence.

### Visual Inspiration

The visual language may draw inspiration from:
- Scandinavian minimalism
- Sustainable consumer brands
- Modern SaaS products
- Apple-like simplicity
- Airbnb
- Linear
- Stripe Dashboard
- Notion
- Shopify Admin

Use these only as quality references. Do not imitate their branding or produce a generic ecommerce interface.


---

## 3. Design Direction

Create a modern, clean, calm, and professional interface.

Visual style:
- Minimal and spacious
- Soft rounded corners
- Clear visual hierarchy
- Light neutral backgrounds
- Green brand accents
- Accessible contrast
- Simple line icons
- Large, readable form controls
- Friendly but professional
- Avoid excessive gradients, decorative effects, or visual clutter

Use cards to group related information such as services, appointments, request history, summaries, and admin statistics.

---

## 4. Color System

### Core Colors

| Token | Color | HEX | Usage |
|---|---|---|---|
| Background | Warm Off-White | `#f5f4f0` | Main page background |
| Primary | Deep Eco Green | `#0c3024` | Primary buttons, active navigation, key icons |
| Secondary | Soft Eco Green | `#c1eeb3` | Secondary buttons, selected cards, badges, highlights |
| Foreground | Dark Forest | `#025d3e` | Main text, headings, navigation text |

### Supporting Colors

Use the core palette as much as possible. Supporting colors should remain subtle.

- Surface / cards: `#ffffff`
- Soft surface: `#eef5ef`
- Border: `#d9dfd9`
- Muted text: `#5f7069`
- Primary button text: `#c1eeb3`
- Secondary button text: `#025d3e`
- Success: `#2f7d4a`
- Warning: `#a66a16`
- Error: `#b42318`

Do not use pure black for regular text. Use `#025d3e`.

---

## 5. Typography

Use **Poppins** as the primary typeface. Use Inter, system-ui, and sans-serif as fallbacks.

Hierarchy:
- Display / Hero: 48–56px, 700
- H1: 40px, 700
- H2: 30–32px, 700
- H3: 22–24px, 600
- Body Large: 18px, 400
- Body: 16px, 400
- Small: 14px, 400
- Button: 16px, 600
- Label: 14–16px, 600

Text color: `#025d3e`.

Maintain generous line-height and strong readability.

---

## 6. Layout & Spacing

Use an 8px spacing system.

Common spacing:
- 4px — very small gap
- 8px — compact
- 16px — standard
- 24px — section internal spacing
- 32px — component separation
- 48px — section separation
- 64–96px — major landing-page sections

Desktop content max-width: approximately 1200–1280px.

Responsive breakpoints:
- Mobile: 360px+
- Tablet: 768px+
- Desktop: 1024px+
- Large desktop: 1440px+

The website must remain functional and visually correct from 360px to 1920px.

---

## 7. Component Style

### Buttons

Primary:
- Background: `#0c3024`
- Text: `#c1eeb3`
- Border: none
- Radius: 10–12px
- Height: 44–48px
- Font weight: 600

Secondary:
- Background: `#c1eeb3`
- Text: `#025d3e`
- Radius: 10–12px

Outline:
- Transparent background
- Border: 1px solid `#0c3024`
- Text: `#0c3024`

Destructive actions:
- Do not visually compete with the primary action.
- Use subtle red styling for cancellation or destructive confirmation.

### Inputs

- White or very light surface
- 1px neutral border
- 10px radius
- Minimum height: 44px
- Clear labels above fields
- Visible focus state using `#0c3024`
- Error text displayed directly below the field
- Do not rely only on color to communicate errors

### Cards

- Background: `#ffffff`
- Border: 1px solid `#d9dfd9`
- Radius: 14–16px
- Subtle shadow only when needed
- Padding: 20–24px

### Status Badges

Requests may have:
- Pendiente
- Asignada
- Completada
- Cancelada

Use compact pill badges with text labels. Never communicate status using color alone.

### Icons

Use a consistent simple outline icon family such as Lucide.
Recommended icons:
- User
- LogIn
- Sofa
- Bed
- Layers
- Calendar
- Clock
- MapPin
- Receipt
- CreditCard
- Banknote
- Smartphone
- Star
- Bell
- History
- UserRoundCheck
- FileText
- BarChart3
- Settings
- LogOut

---

## 8. Global Navigation

### Public Header

Left:
- ECOWASH logo

Center/right:
- Inicio
- Servicios
- ¿Cómo funciona?
- Cobertura
- Contacto

Actions:
- Iniciar sesión — secondary/outline
- Solicitar servicio — primary

On mobile, collapse navigation into a menu.

### Customer Dashboard Navigation

Items:
- Inicio
- Solicitar servicio
- Mis solicitudes
- Historial
- Mi perfil
- Notificaciones
- Cerrar sesión

### Administrator Navigation

Items:
- Dashboard
- Solicitudes
- Solicitudes de hoy
- Encargados
- Disponibilidad
- Clientes
- Servicios y precios
- Zonas de cobertura
- Reportes
- Configuración
- Cerrar sesión

---

## 9. Public Website Screens

### 8.1 Home / Landing Page

Hero:
- Strong headline about professional home upholstery cleaning
- Short supporting text
- Primary CTA: “Solicitar servicio”
- Secondary CTA: “Ver servicios”
- Professional visual related to carpet/sofa cleaning

Service cards:
1. Alfombras
2. Sillones
3. Colchones

Each card:
- Icon/image
- Service title
- Short description
- “Ver detalles”

How it works:
1. Selecciona el servicio
2. Indica los detalles
3. Elige fecha y hora
4. Recibe tu servicio

Additional sections:
- Why choose ECOWASH
- Coverage
- Customer ratings/testimonials
- CTA banner
- Footer

Footer:
- Logo
- Navigation
- Contact
- Terms/privacy
- Copyright

---

## 10. Authentication

### 9.1 Registration

Fields:
- Nombre completo
- Correo electrónico
- Teléfono
- Dirección
- Contraseña
- Confirmar contraseña

The address should be validated against the service coverage area.

Actions:
- Crear cuenta
- “¿Ya tienes una cuenta? Inicia sesión”

Provide clear validation and error feedback.

### 9.2 Login

Fields:
- Correo electrónico
- Contraseña
- Show/hide password

Actions:
- Iniciar sesión
- ¿Olvidaste tu contraseña?
- Crear cuenta

The same login supports customer and administrator roles, redirecting each role to the appropriate dashboard.

### 9.3 Forgot Password

Flow:
1. Enter email
2. Send recovery instructions
3. Confirmation state
4. Reset password form

---

## 11. Customer Experience

### 10.1 Customer Dashboard

Welcome section:
- “Hola, [Nombre]”
- Short summary

Quick action:
- Large “Solicitar servicio” CTA

Summary cards:
- Solicitudes pendientes
- Solicitudes asignadas
- Servicios completados

Recent requests list:
- Request number
- Service
- Date
- Estimated cost
- Status
- View details

---

## 12. Service Request Flow

Use a step-by-step flow rather than one long form.

Progress indicator:
1. Servicio
2. Detalles
3. Fecha
4. Pago
5. Confirmación

### Step 1 — Select Service

Cards:
- Alfombra
- Sillón
- Colchón

Selected card:
- Background/accent: `#c1eeb3`
- Strong visible selected state

### Step 2 — Service Details

Fields dynamically adapt to service.

Include:
- Tipo de artículo
- Cantidad
- Tamaño
- Características
- Observaciones

Show estimated price summary as information is entered.

### Step 3 — Date & Time

Calendar/date selector.
Only show available times.

Display:
- Selected date
- Selected time
- Availability status

### Step 4 — Payment Method

Options:
- Efectivo
- SINPE Móvil
- Tarjeta

Use selectable cards with icons.

For card payments, clearly communicate secure processing. Full card numbers must never be stored by ECOWASH.

### Step 5 — Review & Confirm

Summary:
- Customer
- Address
- Service
- Quantity/size
- Observations
- Date/time
- Payment method
- Estimated cost

Primary CTA:
- Confirmar solicitud

After confirmation:
- Success state
- Unique request number
- View request
- Return to dashboard

---

## 13. Request Detail

Header:
- “Solicitud #XXXX”
- Status badge

Sections:
- Servicio
- Fecha y hora
- Dirección
- Cost
- Payment method
- Assigned worker, when applicable
- Observations

Actions depend on state.

Before assignment/start:
- Reprogramar
- Cancelar solicitud

Assigned:
- No cancellation/reprogramming if business rules prevent it

Completed:
- Descargar comprobante
- Calificar servicio

---

## 14. Reschedule Request

Show:
- Current date/time
- New available date
- New available time
- Confirmation summary

Clearly warn that the change will replace the existing schedule.

After success:
- Confirmation message
- Updated request detail

The system must retain the original and new dates for traceability.

---

## 15. Cancel Request

Use a confirmation modal.

Content:
- Clear warning
- Request number
- Service/date
- Optional cancellation reason

Actions:
- Mantener solicitud — safe/default
- Cancelar solicitud — destructive

Cancellation is available only before the service is assigned or started.

---

## 16. Customer History

Title:
“Historial de servicios”

Filters:
- Status
- Date range
- Service type

Each item must clearly show:
- Date
- Service
- Estimated/final cost
- Status

Users should be able to identify date, cost, and status quickly.

---

## 17. Rating & Review

Available only after a service is completed.

Elements:
- 1–5 star rating
- Comment textarea
- Character counter: 0/200
- Submit button

Prevent comments above 200 characters.

Success state:
“Gracias por compartir tu experiencia.”

---

## 18. Customer Profile

Sections:
- Información personal
- Contacto
- Dirección
- Seguridad

Editable:
- Name
- Phone
- Address

Email may be displayed separately depending on account rules.

Actions:
- Guardar cambios
- Cancelar

---

## 19. Notifications

Notification center with:
- Status changed to Asignada
- Status changed to Completada

Each notification:
- Icon
- Short message
- Date/time
- Link to request

Unread notifications should have a subtle highlighted background.

---

# ADMIN EXPERIENCE

## 20. Admin Dashboard

Create a professional operations dashboard.

Top metrics:
- Solicitudes de hoy
- Pendientes
- Asignadas
- Completadas
- Ingresos del período

Main areas:
- Today’s requests
- Upcoming services
- Availability overview
- Recent activity

Use simple charts only where they add clear value.

---

## 21. Requests Management

Table columns:
- ID
- Cliente
- Servicio
- Fecha
- Hora
- Costo
- Encargado
- Estado
- Acciones

Filters:
- Date
- Status
- Service
- Worker

Search:
- Request ID
- Customer

Actions:
- Ver detalle
- Asignar encargado
- Actualizar estado

---

## 22. Today’s Requests

Prioritize operational clarity.

Display today’s pending requests in a clean list/table.

Show:
- Time
- Customer
- Service
- Address
- Estimated duration/cost if available
- Status
- Assigned worker

Primary actions should be easy to reach.

---

## 23. Assign Worker

Modal or side panel.

Show:
- Request summary
- Date/time
- Available workers

Each worker:
- Name
- Availability
- Existing schedule indicator

Do not allow assignment when the selected worker already has an overlapping service.

After assignment:
- Status automatically becomes “Asignada”
- Customer receives notification

---

## 24. Request Status Management

Status flow:
Pendiente → Asignada → Completada

Use clear confirmation before marking a request completed.

When completed:
- Receipt becomes available
- Customer can rate service
- Status notification is sent

---

## 25. Worker Availability

Calendar/schedule interface.

Admin can:
- Select worker
- Add available hours
- Edit availability
- View occupied periods

Views:
- Day
- Week

Use clear differentiation between:
- Disponible
- Ocupado
- Servicio asignado

---

## 26. Customer Management

Customer list:
- Name
- Email
- Phone
- Address
- Number of services
- Actions

Customer detail:
- Basic information
- Service history
- Edit information

Only authorized administrators can edit customer information.

---

## 27. Services & Pricing Catalog

Admin can manage:
- Alfombra
- Sillón
- Colchón
- Future service types

For each service:
- Name
- Description
- Available sizes
- Base prices
- Active/inactive status

Actions:
- Crear
- Editar
- Desactivar

If a service has active requests associated with it, do not allow deletion. Offer “Desactivar” instead.

---

## 28. Coverage Areas

Admin screen to manage areas/districts served by ECOWASH.

Table/list:
- Zone/district
- Status
- Actions

Actions:
- Add coverage area
- Edit
- Activate/deactivate

Customer addresses should be checked against this configuration.

---

## 29. Reports

Report filters:
- Start date
- End date
- Service type
- Worker

Summary:
- Total completed services
- Total income
- Services by worker

Table:
- Date
- Request
- Customer
- Service
- Worker
- Amount

Export actions:
- Exportar PDF
- Exportar Excel

---

## 30. Service Receipt

Available after service completion.

Receipt should include:
- ECOWASH branding
- Receipt/request number
- Customer name
- Service
- Service details
- Date
- Cost
- Payment method
- Assigned worker if appropriate

Primary action:
- Descargar PDF

The PDF must be clean and readable on desktop and mobile devices.

---

## 31. Empty States

Design intentional empty states.

Examples:
- “Aún no tienes solicitudes.”
- “No hay servicios pendientes para hoy.”
- “No encontramos resultados con estos filtros.”
- “No tienes notificaciones nuevas.”

Each empty state should include:
- Simple icon
- Short explanation
- Relevant CTA when applicable

---

## 32. Feedback States

### Success

Use concise confirmation:
- Solicitud creada correctamente
- Cambios guardados
- Servicio reprogramado
- Solicitud cancelada
- Encargado asignado

### Error

Errors should:
- Explain what happened
- Tell the user what to do next
- Appear near the relevant action/field

### Loading

Use:
- Skeleton loaders for lists/cards
- Button loading indicators for actions
- Avoid blocking the entire screen unnecessarily

---

## 33. Accessibility

Follow WCAG-oriented design practices.

Requirements:
- Strong text/background contrast
- Minimum 16px body text where practical
- Minimum 44×44px interactive targets
- Keyboard-accessible navigation
- Visible focus states
- Labels for every input
- Do not use placeholders as the only label
- Semantic headings
- Accessible error messages
- Icons must have labels/tooltips where meaning is not obvious
- Status cannot depend on color alone

---

## 34. Responsive Behavior

### Desktop
- Full navigation
- Multi-column layouts
- Admin tables
- Dashboard cards

### Tablet
- Reduced columns
- Collapsible navigation
- Cards may use 2-column grids

### Mobile
- Single-column layout
- Hamburger/menu drawer
- Full-width primary CTAs
- Tables convert to stacked cards where necessary
- Forms use full width
- Sticky bottom CTA may be used in the service-request flow

No horizontal overflow should occur at 360px width.

---

## 35. UX Rules

1. A customer should complete a service request in no more than 5 minutes.
2. Always show the estimated cost before confirmation.
3. Always show the selected date before confirmation.
4. Clearly show the current request status.
5. Do not allow unavailable dates/times to be selected.
6. Do not allow cancellation/reprogramming after assignment when restricted by the business rule.
7. Always confirm destructive actions.
8. Never expose another customer’s information.
9. Use plain, human-readable language.
10. Keep primary actions visually consistent.
11. Avoid unnecessary steps.
12. Preserve entered information when navigating between request steps.
13. Show immediate feedback after important actions.
14. Validate forms inline whenever possible.

---

## 36. Recommended Stitch Screen Set

Generate a coherent responsive design system and the following screens:

### Public
1. Landing page
2. Services
3. Login
4. Registration
5. Forgot password

### Customer
6. Customer dashboard
7. New service request — Service selection
8. New service request — Details
9. New service request — Date/time
10. New service request — Payment
11. New service request — Review
12. Request confirmation
13. Request detail
14. Reschedule request
15. Customer history
16. Rating/review
17. Customer profile
18. Notifications

### Admin
19. Admin dashboard
20. Requests management
21. Today’s requests
22. Request detail
23. Assign worker
24. Worker availability
25. Customer management
26. Customer detail/edit
27. Services and pricing
28. Coverage areas
29. Reports
30. Receipt preview

---

## 37. Stitch Generation Direction

When generating ECOWASH screens, maintain the same visual system across every page.

Use:
- `#f5f4f0` as the dominant application background.
- `#0c3024` for primary actions, active states, navigation emphasis, and important brand elements.
- `#c1eeb3` for secondary actions, soft highlights, selected cards, and supporting accents.
- `#025d3e` as the primary foreground/text color.
- White cards over the warm background.
- Rounded corners around 12–16px.
- Restrained shadows.
- Generous whitespace.
- Accessible typography.
- Simple outline icons.
- Responsive layouts from 360px to 1920px.

The final product should feel like a trustworthy professional home-service platform rather than a generic ecommerce site. Prioritize clarity, booking speed, operational visibility, accessibility, and confidence throughout the experience.

---

## 38. Detailed Design Tokens

### Border Radius

- Buttons: 10–12px
- Cards: 16px
- Inputs and selects: 10px
- Dialogs: 20px
- Badges and pills: 999px

### Shadows

Prefer borders over shadows. Shadows must remain restrained.

Cards:

```css
0 4px 16px rgba(12, 48, 36, 0.06)
```

Dialogs:

```css
0 10px 40px rgba(12, 48, 36, 0.12)
```

Dropdowns:

```css
0 6px 18px rgba(12, 48, 36, 0.10)
```

### Motion

Animations must support comprehension rather than decoration.

- Duration: 150–250ms
- Easing: ease-out
- Allowed transitions: fade, short slide, subtle scale
- Avoid bounce, parallax, continuous motion, and decorative loading effects
- Respect reduced-motion preferences

### Component Inventory

Build reusable variants for:
- Public navigation bar
- Customer navigation
- Administrator sidebar
- Mobile drawer
- Footer
- Hero
- Service card
- Selectable service card
- Booking wizard
- Progress indicator
- Cost summary
- Request card
- Request timeline
- Calendar
- Time-slot selector
- Worker availability block
- Statistic card
- Data table
- Mobile data card
- Status badge
- Toast
- Alert
- Modal
- Side panel
- Accordion
- FAQ
- Profile card
- Notification item
- Search bar
- Filter bar
- Date picker
- Pagination
- Breadcrumb
- Receipt preview
- Download button
- Chart
- Empty state
- Error state
- Loading skeleton

### Error Pages

Create friendly and consistent screens for:
- 403 — Access denied
- 404 — Page not found
- 500 — Unexpected error

Each screen should contain:
- Simple illustration or outline icon
- Human-readable explanation
- Safe recovery action
- Link to return to the dashboard or home page

---

## 39. Functional Design Mapping

The following rules connect the UI directly to the functional requirements.

### RF-01 — Customer Registration

- Keep the form short and structured.
- Validate fields inline.
- Validate the address against coverage areas.
- Preserve entered information after validation errors.

### RF-02 — Login

- Request only email and password.
- Include password visibility and password recovery.
- Redirect users according to their role.

### RF-03 — Profile Management

- Clearly distinguish editable and read-only information.
- Confirm saved changes.
- Revalidate coverage when the address changes.

### RF-04 — Service Details

- Prefer recognizable service cards, images, and plain language.
- Adapt fields to the selected object type.
- Group quantity, size, characteristics, and observations logically.

### RF-05 — Password Recovery

- Use the fewest reasonable steps.
- Reassure the user after recovery instructions are sent.
- Avoid exposing whether an email belongs to an account.

### RF-06 — Cancel Request

- Explain eligibility and consequences.
- Require confirmation.
- Use a secondary safe action as the default.

### RF-07 — Cost Calculation

The estimate is a visual focal point. Always show:
- Service
- Size
- Quantity
- Unit price
- Subtotal
- Estimated total

### RF-08 — Confirm Service

Before confirmation, summarize:
- Customer
- Address
- Service details
- Date and time
- Estimated cost
- Payment method

After confirmation, show the unique request number.

### RF-09 — Service Receipt

- Make the receipt professional, readable, and easy to download.
- Use a standard PDF layout.
- Keep branding restrained.

### RF-10 — Worker Availability

- Prioritize calendar clarity.
- Make available, occupied, and assigned states immediately distinguishable.
- Do not depend on color alone.

### RF-13 — Customer History

Date, cost, and status must be visually scannable within seconds.

### RF-14 — Request Status

Use the same labels, badge styles, and status order throughout the application:
- Pendiente
- Asignada
- Completada
- Cancelada

### RF-15 — Customer Editing

Administrator editing screens must prioritize readability, authorization, and clear save feedback.

### RF-16 — Requests of the Day

Prioritize today's operational information and make key actions immediately reachable.

### RF-17 — Worker Assignment

- Do not allow unavailable workers to be selected.
- Explain schedule conflicts.
- Automatically change the request to “Asignada” after success.

### RF-18 — Notifications

Use reassuring, natural language. Link each notification to the relevant request.

### RF-19 — Services and Prices

- Use structured cards or compact tables.
- Support create, edit, and deactivate.
- Block deletion when active requests exist.

### RF-20 — Reports

- Make totals visually prominent.
- Use charts as support, not as replacements for data.
- Provide PDF and XLSX export.

### RF-21 — Rating

- Make five stars immediately tappable and keyboard accessible.
- Keep the comment optional.
- Enforce the 200-character limit.

### RF-22 — Coverage Areas

Provide immediate validation and plain-language results for supported and unsupported areas.

### RF-23 — Rescheduling

Display original and new dates together. Preserve change history for traceability.

### RF-24 — Payment Method

Use recognizable icons for:
- Efectivo
- SINPE Móvil
- Tarjeta

Keep the selected method visible during review and confirmation.

---

## 40. Non-Functional Design Mapping

### Performance

- Display loading indicators immediately.
- Use skeletons for lists and dashboards.
- Avoid unnecessary media and animation.
- Keep primary flows lightweight.

### Accessibility

- Meet WCAG AA contrast requirements.
- Use minimum 44×44px touch targets.
- Support keyboard navigation.
- Use visible focus states and semantic labels.

### Availability

- Empty, maintenance, and error states must explain what happened and what the user can do next.

### Maintainability

- Reuse components and variants.
- Avoid one-off patterns.
- Keep tokens centralized and consistent.

### Privacy and Security

- Visually separate sensitive information.
- Mask information where appropriate.
- Require confirmation for sensitive actions.
- Never expose another customer's data.
- Never store or display a full card number.

### Usability

A customer with no technical experience should complete a request in under five minutes.

### Scalability

- Paginate large datasets.
- Keep tables readable with high record volume.
- Provide filtering and search.
- Convert tables to cards on narrow screens.

### Reliability

- Prevent duplicate submissions.
- Disable controls while an action is processing.
- Always confirm success or explain failure.
- Reject worker schedule conflicts.

### Interoperability

Generated PDF and XLSX documents must preserve layout and readability across common platforms.

---

## 41. Voice and Copywriting

Write like a helpful professional.

Preferred:
- “Tu solicitud fue enviada correctamente.”
- “Tu servicio está programado.”
- “Todo está listo.”
- “Este horario ya no está disponible. Selecciona otro.”
- “No encontramos solicitudes con estos filtros.”

Avoid:
- “Operación ejecutada correctamente.”
- “Proceso completado.”
- Technical stack traces
- Internal system terminology
- Blaming language

Copy rules:
- Use short sentences.
- Prefer active voice.
- Explain the next action.
- Use consistent terminology.
- Use “solicitud” for a booking request and “servicio” for the work performed.
- Use Spanish interface copy throughout the product.

---

## 42. Design Review Checklist

Every screen should answer “yes” to the following:

- Does it feel clean and calm?
- Is the primary action obvious?
- Can a new user understand the purpose within 10 seconds?
- Are price, date, status, and address visible when relevant?
- Is the layout spacious without wasting space?
- Does it communicate trust?
- Is it accessible by keyboard?
- Are focus and error states visible?
- Does it work at 360px without horizontal overflow?
- Are destructive actions confirmed?
- Does the screen use existing components and tokens?
- Does the experience feel environmentally responsible without relying on visual clichés?

If any answer is “no,” revise the screen.

---

## 43. Final Stitch Instruction

Treat this document as the single source of truth for every ECOWASH screen.

Generate a coherent, responsive product—not isolated mockups. All screens must share the same:
- Color tokens
- Typography
- Spacing
- Radius
- Button hierarchy
- Form patterns
- Status language
- Navigation structure
- Feedback behavior
- Accessibility standards

The final experience should make users think:

> “Esto se ve limpio.”

> “Esto se siente confiable.”

> “Sé exactamente qué hacer.”

The interface should disappear behind the task. Prioritize clarity, booking speed, scheduling confidence, operational visibility, and consistent feedback.

