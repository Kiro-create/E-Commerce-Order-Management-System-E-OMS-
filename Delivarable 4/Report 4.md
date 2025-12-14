
# **PART 1 — Identify User & System Interfaces**

---

# **1(a) USER INTERFACES (All Screens the User Sees)**

---

## **Use Case 1: Place Online Order**

Required User Interfaces:

* Product Catalog Screen
* Product Details Screen
* Shopping Cart Screen
* Checkout Screen (shipping + billing info)

---

## **Use Case 2: Process Customer Payment**

Required User Interfaces:

* Payment Method Selection Screen & Payment Details Screen (card/PayPal/etc.), one screen
* Payment Authentication Screen (OTP or 3DS)
* Payment Result Screen (success/failure)

---

## **Use Case 3: Manage Product Catalog (Admin/Staff)**

Required User Interfaces:

* Product Management Dashboard
* Add & Edit Product Form one screen
* Inventory Management Screen

---

## **Use Case 4: Plan Shipment (Logistics Staff)**

Required User Interfaces:

* Shipping Manifest Review Screen
---

## **Use Case 5: Track Order Status**

Required User Interfaces:

* Orders & Tracking Screen

---

# **PART 2 — User Interface Design for Interfaces Identified in 1(a)**

---
# **(a) Menu Design**
---
## **Menu Grouping Table**
| **Menu Description**   | **Menu Choices (Use Cases)**                                                            | **Intended User(s)**    |
| ---------------------- | --------------------------------------------------------------------------------------- | ----------------------- |
| **Products**           | UC1: Place Online Order (Browse Products, View Details)                                 | Customer                |
| **Cart & Checkout**    | UC1: Place Online Order (View Cart, Checkout, Payment Flow)                             | Customer                |
| **Orders & Tracking**  | UC5: Track Order Status (View My Orders, Track Shipment, Order Details)                 | Customer                |
| **Catalog Management** | UC3: Manage Product Catalog (View Catalog, Add Product, Edit Product, Update Inventory) | Admin / Inventory Staff |
| **Shipment Planning**  | UC4: Plan Shipment (View Orders Ready for Shipment, Review Manifest)                    | Logistics Staff / Admin |
## **CUSTOMER MENU**

Products
- Browse Products
- View Product Details

Cart
- View Cart
	- Checkout
	    - Select Payment Method
	    - Enter Payment Details
	    - Authenticate Payment
	    - Payment Result

Orders
- View My Orders
- Track Shipment
- View Order Details

# **ADMIN / STAFF MENU**

Catalog Management
- View Product Catalog
- Add Product
- Edit Product
- Update Inventory

Shipment Planning
- View Orders Ready for Shipment
- Review Shipment Manifest

## **Part 2: Menu Design**
![Menu_Design1](Screenshots/Users_Menu_Design.png)

![Menu_Design2](Screenshots/Admin_Menu_Design.png)
# **(a) storyboard**

![Storyboard1](Storyboard/Storyboard1.png)
![Storyboard2](Storyboard/Storyboard2.png)
![Storyboard3](Storyboard/Storyboard3.png)
![Storyboard4](Storyboard/Storyboard4.png)
![Storyboard5](Storyboard/Storyboard5.png)

# **Figma UI Design**
![UI1](Figma_UI_Design/D1.png)
![UI2](Figma_UI_Design/D2.png)
![UI3](Figma_UI_Design/D3.png)
![UI4](Figma_UI_Design/D4.png)
![UI5](Figma_UI_Design/D5.png)
![UI6](Figma_UI_Design/D6.png)
![UI7](Figma_UI_Design/D7.png)
![UI8](Figma_UI_Design/D8.png)
![UI9](Figma_UI_Design/D9.png)
![UI10](Figma_UI_Design/D10.png)
![UI11](Figma_UI_Design/D11.png)
![UI12](Figma_UI_Design/D12.png)
![UI13](Figma_UI_Design/D13.png)

## **User Interface (UI) Design Specifications – Figma**

## 1. Layout Templates

### 1.1 Customer Interface Template

* **Top Navigation Bar**

  * Left: E‑Mart logo
  * Center: Primary navigation (Products, Orders)
  * Right: Search, Cart icon with badge, User profile
* **Main Content Area**

  * White background
  * Responsive grid for cards and forms
* **Footer (optional)**

  * System name and copyright

### 1.2 Admin / Staff Interface Template

* **Left Sidebar Navigation**

  * Admin Panel branding
  * Menu items grouped by responsibility (Catalog, Inventory, Shipment Planning, Orders)
* **Header Area**

  * Page title and contextual actions
* **Content Area**

  * Data tables, forms, and dashboards

### 1.3 System Entry Template (Login)

* Full‑screen layout
* Centered authentication panel
* No navigation menus visible

## 2. Color System

### 2.1 Brand & Primary Colors

* **E‑Mart Teal (Brand Accent):** `#6FAEB8`
* **Primary Action Blue:** `#2563EB`
* **Primary Action Hover:** `#1E3A8A`

### 2.2 Neutral Colors

* **Background Gray:** `#F3F4F6`
* **Surface White:** `#FFFFFF`
* **Border Gray:** `#D1D5DB`

### 2.3 Text Colors

* **Primary Text:** `#111827`
* **Secondary Text:** `#374151`
* **Placeholder / Disabled Text:** `#6B7280`

### 2.4 Semantic Colors

* **Success:** `#16A34A`
* **Warning:** `#F59E0B`
* **Error:** `#DC2626`
* **Info:** `#2563EB`

## 3. Typography

* **Font Family:** Inter (or equivalent modern sans‑serif)

| Usage               | Size    | Weight    |
| ------------------- | ------- | --------- |
| Page Titles         | 24–28px | Semi‑Bold |
| Section Headers     | 18–20px | Medium    |
| Body Text           | 14–16px | Regular   |
| Helper / Error Text | 12–14px | Regular   |

## 4. Spacing & Grid System

* **Base Unit:** 8px spacing system
* Common spacing values: 8px, 16px, 24px, 32px
* **Content max width:** 1200–1440px (desktop)
* **Card padding:** 16–24px
* **Form field spacing:** 16px vertical

## 5. Components & Properties

### 5.1 Buttons

**Primary Button**

* Background: `#2563EB`
* Text color: `#FFFFFF`
* Height: 44–48px
* Border radius: 8px
* Hover: darker blue
* Disabled: gray background

**Secondary Button**

* Background: `#FFFFFF`
* Border: `1px solid #D1D5DB`
* Text: `#111827`

### 5.2 Input Fields

* Height: 44px
* Border radius: 8px
* Border: `1px solid #D1D5DB`
* Focus border: `#2563EB`
* Error border: `#DC2626`

### 5.3 Cards

* Background: `#FFFFFF`
* Border radius: 12px
* Shadow: `0 4px 12px rgba(0,0,0,0.08)`
* Used for product items, summaries, and dialogs

### 5.4 Tables

* Header background: light gray
* Row hover: subtle gray highlight
* Status badges used for states

### 5.5 Badges / Status Indicators

| Status               | Color |
| -------------------- | ----- |
| In Stock / Success   | Green |
| Low Stock / Warning  | Amber |
| Out of Stock / Error | Red   |
| Processing / Info    | Blue  |

## 6. Icons

* Icon style: outline / minimal
* Source: Material Icons or similar
* Icon size: 16–20px
* Icons used for actions, status, and navigation only

## 7. Elevation & Shadows

| Level   | Usage                   | Shadow                        |
| ------- | ----------------------- | ----------------------------- |
| Level 1 | Cards                   | `0 4px 12px rgba(0,0,0,0.08)` |
| Level 2 | Modals / Focused panels | `0 8px 24px rgba(0,0,0,0.12)` |

## 8. Consistency Rules

* One active navigation item at a time
* System‑generated states are read‑only
* No role selection in shared interfaces
* Menus reflect user goals, not system steps

---
# **GitHub Evidence**

Repository Link: [https://github.com/Kiro-create/E-Commerce-Order-Management-System-E-OMS-](https://github.com/Kiro-create/E-Commerce-Order-Management-System-E-OMS-)
(All work, commits and pull requests are visible on GitHub.)

# **Jira Project Management Evidence**
![j1](Screenshots/Jira1.png)
![j2](Screenshots/Jira2.png)
![j3](Screenshots/Jira3.png)

# **Figma UI Design Link**
https://www.figma.com/design/yAJB9QUhfVv28Iwb8fxmp4/E-Mart-UI-Design?node-id=0-1&t=76Mp2CIZRsCdPkQF-1
# **Conclusion**
> This deliverable presented a complete and systematic user interface design for the E-Mart E-Commerce Order Management System (E-OMS), derived directly from the system’s analysis artifacts. The user interface design was based on the defined use cases, system sequence diagrams, activity flows, and system boundaries, ensuring consistency and traceability from requirements to interface design. All required user interfaces and system interfaces were first identified according to the core system functionalities. A structured menu grouping and hierarchy was then developed to reflect user goals, user roles, and system responsibilities, clearly separating customer-facing functionality from administrative and logistics operations. The final menu design follows a dialog-based interaction approach and avoids exposing internal processing steps as navigation options. For each selected use case, storyboards were created to illustrate the sequence of interactions between the user and the system, demonstrating how each interface supports the underlying business processes. These storyboards guided the creation of consistent, role-appropriate UI screens using a unified design system aligned with E-Mart branding and established usability principles. Special attention was given to enforcing role-based access, automation boundaries, and error prevention, including automated courier assignment, system-generated shipment batches, and conditional user interactions during checkout and payment processing. A shared Login interface was introduced as a system entry point, supporting both customers and staff while maintaining clear separation between user roles through system-controlled redirection.