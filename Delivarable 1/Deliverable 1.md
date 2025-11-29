# System Vision Document: E-Commerce Order Management System (E-OMS)

### 1. Purpose (Problem Description)

The fundamental purpose of the E-OMS project is to overcome critical operational inefficiencies resulting from E-Market Inc.’s reliance on **conventional e-commerce systems that utilize disconnected tools**. This fragmented system approach currently leads to significant challenges, including **data duplication, communication gaps, and stock errors**. The E-OMS is required to model and automate the **full order lifecycle—from order placement to final delivery** —by implementing an integrated system that connects major internal departments and external partners.

### 2. Scope (System Capabilities and Boundaries)

The E-OMS is designed as an **integrated system** connecting Sales, Finance, Inventory, Logistics, and Customer Support, and integrates with external entities such as suppliers, courier services, and payment gateways. **Inclusions (Core Scope):** The project scope includes end-to-end order management, covering the entire lifecycle from placement through final delivery. Key capabilities are designed to handle:

- **Order Validation and Processing:** Automated recording and generation of a unique Order ID upon placement, followed by validation of details, product data, and customer information.
- **Financial Processing:** Secure payment handling, sending details to a gateway for authorization, and confirming payment (or triggering automatic cancellation upon failure). The system also handles the generation of detailed invoices.
- **Inventory and Logistics:** **Real-time inventory tracking and reservation**. If products are out of stock, a replenishment request is sent to suppliers. The system plans shipment, determines routes, selects a courier, and assigns a tracking number and estimated delivery date.
- **Product Catalog Management:** Authorized inventory staff can **add, update, or delete products**, including details such as product name, description, and price, ensuring an up-to-date product catalog.
- **Customer Interaction:** Email/SMS notifications for every stage of the order process, and support for the **returns and refunds workflow**.

**Exclusions (Limitations):** The E-OMS project is strictly focused on core order management. It specifically **excludes marketing or recommendation systems**. It also **excludes accounting or Human Resources (HR) modules**. The functioning of courier delivery, supplier management, and payment authorization are reliant upon the stability and function of external partners’ systems, which are outside the control of the E-OMS.

### 3. Goals (Business Benefits)

The primary goals of the E-OMS are to centralize core processes and provide business value by:

1. **Increase Operational Efficiency:** The system is intended to **automate and streamline the entire order process** and **minimize manual work**, which will directly result in **reduced delays** and higher overall operational efficiency.
2. **Improve Data Accuracy and Coordination:** A critical goal is to **ensure accuracy and synchronization between departments** by resolving the communication gaps and data duplication challenges identified in the problem.
3. **Strengthen Partner Relations:** The system aims to **strengthen coordination with external partners** (including suppliers and couriers).
4. **Maximize Customer Experience:** The E-OMS goal is to **offer customers real-time order tracking and updates**, and ensure satisfaction through efficient handling of post-delivery issues.

---
# Stakeholders Identification

| _Stakeholder Type_                    | _Stakeholder(s)_                        | _Role / Interest in the System_                                           | _Aspects of the System Important to Them_                                              |
| ------------------------------------- | --------------------------------------- | ------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| **External Operational Stakeholders** | _Sales Department_                      | Validates orders, checks customer and product information before payment. | Order accuracy, pricing validation, smooth transition to payment.                      |
|                                       | _Finance / Payment Department_          | Manages and authorizes customer payments and invoices.                    | Secure payment handling, error-free billing, gateway integration.                      |
|                                       | _Inventory / Warehouse Team_            | Tracks stock levels and manages product availability.                     | Real-time stock visibility, restocking alerts, reservation accuracy.                   |
|                                       | _Logistics Department_                  | Plans shipping, assigns couriers, updates delivery status.                | Shipment tracking, route optimization, delivery timing.                                |
|                                       | _Customer Support Team_                 | Handles customer inquiries, complaints, and return requests.              | Order history access, refund processing, communication tools.                          |
|                                       | _Customers (End Users)_                 | Place orders, make payments, track deliveries.                            | Easy checkout, accurate tracking, secure payments.                                     |
|                                       | _Suppliers / Vendors_                   | Provide products when inventory is low.                                   | Replenishment requests, delivery timelines, stock visibility.                          |
|                                       | _Payment Gateways (PayPal, Visa, etc.)_ | Process and verify online payments.                                       | API reliability, transaction speed, fraud protection.                                  |
|                                       | _Courier / Delivery Companies_          | Deliver products to customers.                                            | Accurate delivery info, updated manifests, timely pickups.                             |
| **Internal Stakeholders**             | _Developers / Technical Team_           | Build, maintain, integrate, and support the E-OMS system.                 | Clear requirements, defined APIs, consistent architecture, testability, deployability. |
| **External Executive Stakeholders**   | _Company Management / Executives_       | Use system reports for business and financial decision-making.            | KPI dashboards, reporting accuracy, cost visibility.                                   |
|                                       | _System Administrators_                 | Maintain E-Market’s user access and system configuration.                 | Stability, data integrity, permission control, monitoring tools.                       |

---
# Functional Requirements

1. **User Registration & Authentication**
    
    - Customers can register, log in, and manage their profiles securely.
    - Admins and staff have role-based access to specific system functions.
2. **Product Catalog & Order Placement**
    
    - Customers can browse products, view detailed descriptions, and add items to their cart.
    - The system allows customers to place online orders and automatically generates a unique Order ID.
3. **Order Verification**
    
    - The Sales module verifies order details, product availability, and customer information.
    - Invalid or incomplete orders are automatically cancelled, and customers are notified.
4. **Payment Processing**
    
    - The Finance module securely processes payments through integrated payment gateways.
    - Successful payments are confirmed automatically; failed transactions trigger order cancellation.
5. **Inventory Management**
    
    - Tracks stock levels in real time.
    - Automatically reserves items for confirmed orders.
    - Sends replenishment requests to suppliers when stock levels are low.
    - Authorized inventory staff can add, update, or delete products, including details such as product name, description, and price, ensuring an up-to-date product catalog.
6. **Logistics & Shipping**
    
    - Plans shipment routes and assigns courier services.
    - Generates tracking numbers and estimated delivery dates.
    - Updates order statuses (e.g., Processing, Shipped, Delivered).
7. **Order Notifications & Tracking**
    
    - Sends automated Email/SMS notifications at each order stage: confirmation, payment, shipment, and delivery.
    - Allows customers to track their orders in real time.
8. **Invoice & Reporting**
    
    - Generates detailed invoices including product, tax, and shipping details.
    - Provides analytical and summary reports for management insights.
9. **Customer Support & Returns**
    
    - Customers can report issues, request returns, or submit feedback.
    - The Support module tracks issue status and ensures follow-up until resolution.
10. **Integration with External Partners**
    
    - Integrates with external systems to support:
        - Payment Gateways for transaction authorization.
        - Courier Services for shipment tracking.
        - Suppliers for automatic restocking requests.
---
# Requirements Elicitation Techniques

| **Technique**                      | **Description**                                                                                                                                                                                                                      | **Justification / Why We Selected It**                                                                                                           |
| ---------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| **1. Interviews**                  | Conduct structured interviews with key stakeholders such as Sales, Finance, Inventory, Logistics, and Customer Support departments. Each department will explain its current workflow, challenges, and expectations from the system. | Interviews allow in-depth understanding of department-specific needs and uncover hidden requirements that might not appear in written documents. |
| **2. Questionnaires / Surveys**    | Distribute online surveys to a larger group of employees and customers to collect opinions about desired system features, usability, and performance expectations.                                                                   | Surveys reach a wider audience quickly, helping identify common requirements and priorities from many users.                                     |
| **3. Observation (Job Shadowing)** | Observe employees in departments like Sales, Inventory, and Logistics as they perform their daily tasks using current tools.                                                                                                         | Observation helps identify real-world pain points, inefficiencies, and user behavior that interviews alone might miss.                           |
| **4. Document Analysis**           | Review existing company reports, sales records, and order processing forms to identify the flow of information between departments.                                                                                                  | Provides factual data about current processes, inputs, and outputs, ensuring that system requirements are based on real business practices.      |
| **5. Brainstorming Sessions**      | Conduct internal team meetings to discuss proposed solutions and system features after collecting stakeholder input.                                                                                                                 | Encourages creativity, collaboration, and alignment between team members before finalizing the requirements.                                     |

---
# Interview Agendas
## 1. External Operational Stakeholder Interview Agenda

This agenda focuses on gathering detailed **Functional Requirements** and quantifying **current system pain points** from employees involved in the daily order workflow.

| Agenda Item Focus              | Interviewer(s) (Project Team Participant)            | Interviewee(s) (Stakeholder)         | Discussion Questions                                                                                                                                        | Source Context                                                                                                                                          |
| :----------------------------- | :--------------------------------------------------- | :----------------------------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Sales & Order Verification** | Ali Tamer (Team Leader / Sales & Order Verification) | Sales Staff                          | How accurately does the statement: "I frequently have to manually re-enter order details into multiple disconnected systems" reflect your current workflow? | The current problem is **data duplication** due to disconnected tools.                                                                                  |
| **Sales & Order Verification** | Ali Tamer (Team Leader / Sales & Order Verification) | Sales Staff                          | When validating an order, what percentage of necessary customer and product data is typically missing or inaccurate?                                        | The Sales module **verifies order details**.                                                                                                            |
| **Finance & Payment**          | Abdelrahman Ahmed (Finance & Payment)                | Finance Staff                        | What challenges exist today in ensuring **secure payment handling**, and what industry standards must the new system meet?                                  | Finance is interested in a **secure payment process**. The system must meet standards for securely handling customer payment details (**Security S1**). |
| **Inventory Management**       | Omar Mohammed (Inventory Management)                 | Inventory Staff                      | How quickly do you need inventory levels to update after an item is reserved or replenished?                                                                | The system requires **real-time inventory tracking and reservation**.                                                                                   |
| **Inventory Management**       | Omar Mohammed (Inventory Management)                 | Inventory Staff / Catalog Management | What is the single most time-consuming step in defining a new product and its description for the product catalog?                                          | Authorized inventory staff need the ability to **add, update, or delete products**.                                                                     |
| **Logistics & Shipping**       | Kirollos Raafat (Logistics & Shipping)               | Logistics Staff                      | What are the most common reasons for shipment planning delays (e.g., missing courier rate information, external system integration failures)?               | Logistics plans shipment. The system relies on **external partners’ systems** (couriers).                                                               |
| **Customer Support**           | Abdelrahman Amr (Customer Support & Reporting)       | Customer Support Agents              | When managing returns and refunds, what information does the current system lack that would most improve resolution time?                                   | Customer Support handles the **returns & refunds workflow**.                                                                                            |

## 2. External Executive Stakeholder Interview Agenda

This agenda focuses on high-level strategic alignment, **Non-Functional Requirements** (such as Reliability and Performance), and defining metrics for success.

| Agenda Item Focus           | Interviewer(s) (Project Team Participant)                                         | Interviewee(s) (Stakeholder) | Discussion Questions                                                                                                                                       | Source Context                                                                                                                      |
| :-------------------------- | :-------------------------------------------------------------------------------- | :--------------------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------- | :---------------------------------------------------------------------------------------------------------------------------------- |
| **Strategic Goal Metrics**  | Ali Tamer (Team Leader), Abdelrahman Amr (Reporting), Abdelrahman Ahmed (Finance) | Management / Executives      | How will we measure the success of the E-OMS goal to **increase operational efficiency** and minimize manual work after deployment?                        | A primary goal is to **increase operational efficiency** and **minimize manual work**.                                              |
| **Problem Validation**      | Ali Tamer (Team Leader), Abdelrahman Amr (Reporting), Abdelrahman Ahmed (Finance) | Management / Executives      | Which of the current problems—data duplication, communication gaps, or stock errors—causes the greatest financial risk or loss?                            | The fragmented system leads to data duplication, communication gaps, and stock errors.                                              |
| **Reporting Needs**         | Ali Tamer (Team Leader), Abdelrahman Amr (Reporting), Abdelrahman Ahmed (Finance) | Management / Executives      | What are the three most critical **Key Performance Indicators (KPIs)** you need to monitor daily or weekly using the system’s reports?                     | Executives use system reports for business decisions. The system must **provide management with integrated reports and analytics**. |
| **System Reliability (R1)** | Ali Tamer (Team Leader), Abdelrahman Amr (Reporting), Abdelrahman Ahmed (Finance) | Management / Executives      | How critical is system reliability, particularly the requirement for **24/7 availability** with no unscheduled downtime?                                   | **Reliability requirements (R1)** state the system must be available 24/7.                                                          |
| **Scope Management**        | Ali Tamer (Team Leader), Abdelrahman Amr (Reporting), Abdelrahman Ahmed (Finance) | Management / Executives      | What oversight mechanisms should be put in place to ensure the project focuses only on **core order management** and avoids expanding into excluded areas? | The project **excludes marketing or HR/accounting modules**.                                                                        |

---
### 3. Internal Stakeholder Interview Agenda

This agenda aligns the project team on architecture, technical constraints, and risk considerations.

| Agenda Item Focus                                                       | Interviewer(s)                 | Interviewee(s)              | Discussion Questions                                                                                                        | Purpose                                                          |
| :---------------------------------------------------------------------- | :----------------------------- | :-------------------------- | :-------------------------------------------------------------------------------------------------------------------------- | :--------------------------------------------------------------- |
| **Technical Architecture & Integration**                                | Team Leader                    | Developers / Technical Team | What integration constraints exist for suppliers, courier APIs, and payment gateways? What design standards must we follow? | Establish consistent architecture decisions.                     |
| **SDLC & Task Coordination**                                            | Team Leader                    | Development Team            | How should we divide tasks to ensure consistent progress? What risks (technical or scheduling) need mitigation?             | Internal alignment on planning and execution.                    |
| **Non-Functional Requirements (Performance, Security, Supportability)** | Team Leader / Senior Developer | Developers                  | What performance thresholds must be designed into the system? What security and audit controls do we need to implement?     | Ensures system design satisfies NFRs identified with the client. |

---
# Questionnaire

## SECTION I: Role and Workflow Context

1. **Your Primary Department/Role:** (Please select one)
    - [ ] Sales & Order Verification
    - [ ] Inventory Management / Warehouse
    - [ ] Logistics & Shipping
    - [ ] Finance & Payment
    - [ ] Customer Support
    - [ ] Product Catalog/Merchandise Management
2. **Your Specific Job Role/Title:** (e.g., Team Leader, Order Processing Clerk, Shipping Coordinator, Stock Supervisor): __________
3. **Estimate the percentage of your daily work that involves interacting with order-related data:**
    - [ ] 0–25%
    - [ ] 26–50%
    - [ ] 51–75%
    - [ ] 76–100%

## SECTION II: Current System Pain Points (Problem Description)

The E-OMS aims to solve problems arising from the use of disconnected tools, which lead to data duplication, communication gaps, and stock errors. Please rate your agreement with the following statements regarding current processes (1=Strongly Disagree, 5=Strongly Agree):

| Statement (Current State)                                                                                                                                      | 1 (SD) | 2<br>(D) | 3<br>(N) | 4<br>(A) | 5 (SA) |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------- | :----- | :------- | :------- | :------- | :----- |
| **A. Data Duplication:** I frequently have to manually re-enter order details into multiple disconnected systems.                                              | [ ]    | [ ]      | [ ]      | [ ]      | [ ]    |
| **B. Communication Gaps:** It is difficult to get a real-time order status update from another department (e.g., Inventory asking Finance if payment cleared). | [ ]    | [ ]      | [ ]      | [ ]      | [ ]    |
| **C. Stock Errors:** Our current inventory data frequently conflicts with the physical stock count or causes fulfillment issues.                               | [ ]    | [ ]      | [ ]      | [ ]      | [ ]    |
| **D. Manual Work:** The time spent on manual administrative tasks significantly delays order processing.                                                       | [ ]    | [ ]      | [ ]      | [ ]      | [ ]    |

## SECTION III: Functional Requirements (System Capabilities)

Functional requirements define the activities the system must perform. Please answer the following based on the required E-OMS capabilities:

3. **Order Validation (Sales/Verification):** When validating an order, what percentage of necessary customer and product data is typically missing or inaccurate in the current system?
    - [ ] Less than 5%
    - [ ] 5%–15%
    - [ ] 16%–30%
    - [ ] More than 30%
4. **Product Catalog Management (If Applicable):** If you are responsible for adding products, what is the single most time-consuming step in defining a new product and its description?
    - 
        
5. **Inventory Tracking & Reservation (Inventory/Warehouse):** How quickly do you need inventory levels to update after an item is reserved or replenished?
    - [ ] Immediately (Real-time)
    - [ ] Within 10 minutes
    - [ ] Within 1 hour
    - [ ] End of day
6. **Logistics & Shipping (Logistics):** What is the most common reason for shipment planning delays (e.g., incorrect customer address format, missing courier rate information, etc.)?
    - 
        
7. **Customer Support (Support):** When managing returns and refunds, what information does the current system lack that would most improve resolution time?
    - 
        

## SECTION IV: Non-Functional Requirements (FURPS+)

Non-functional requirements describe system characteristics, constraints, and performance goals. Please rate the importance of the following characteristics for the new E-OMS (1=Not Important, 5=Absolutely Critical):

|Requirement Type (FURPS+)|Characteristic|1 (NI)|2 (LI)|3 (M)|4 (I)|5 (AC)|
|:--|:--|:--|:--|:--|:--|:--|
|**Performance**|**P1:** The system must process payment authorization and update inventory reservation status within 5 seconds.|[ ]|[ ]|[ ]|[ ]|[ ]|
|**Reliability**|**R1:** The system must be available 24/7, with no unscheduled downtime.|[ ]|[ ]|[ ]|[ ]|[ ]|
|**Usability**|**U1:** The user interface (screens/reports) must be simple enough to require less than 1 hour of new user training per module.|[ ]|[ ]|[ ]|[ ]|[ ]|
|**Security**|**S1:** The system must meet all current industry standards for securely handling customer payment details (Finance).|[ ]|[ ]|[ ]|[ ]|[ ]|

8. **Open Feedback:** Please provide any additional suggestions regarding current processes or essential features the new E-OMS must include to make your job more efficient.
    

---
# Activity Diagram
![[ActivityDiagram1.jpg]]

---
# Screenshots from Jira & GitHub

## Jira
>Our team utilized Jira for the comprehensive organization and monitoring of Deliverable #1. We structured the project by creating a main Epic, Deliverable #1: System Analysis & Requirements, which served as a container for all related work. This Epic was broken down into User Stories, with each story corresponding to a major section of the technical report, such as the System Vision Document and Workflow Documentation. To ensure clear accountability and a granular breakdown of work, some stories were further divided into specific sub-tasks, which were then assigned to individual team members based on their project roles. Progress was actively monitored using our board, allowing the team leader to visually track tasks as they moved from To Do to In Progress and Done, ensuring all project goals were met on schedule.

![[Pasted image 20251025210805.png]]
![[image.webp]]

## GitHub
https://github.com/Kiro-create/E-Commerce-Order-Management-System-E-OMS-

![[Pasted image 20251025210935.png]]
![[Pasted image 20251025210955.png]]
![[Pasted image 20251025211021.png]]