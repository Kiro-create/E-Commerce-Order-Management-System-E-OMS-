The design and distribution of questionnaires are a crucial activity within **Core Process 3: Discover and Understand Details** (Systems Analysis-Requirements Engineering). Questionnaires are an effective **information-gathering technique** for collecting preliminary data from a **large number of operational stakeholders**.

For the E-Commerce Order Management System (E-OMS), the questionnaire is targeted at the **Internal Operational Stakeholders**—the employees who will regularly interact with the system—including personnel from Sales, Inventory Management, Logistics, Finance, and Customer Support.

The questions below utilize closed-ended, quantitative (scale), and open-ended formats, focusing on current pain points and future requirements across the major integrated workflows (Order Validation, Payment, Inventory, and Shipping).

---

# Operational User Questionnaire: E-Commerce Order Management System (E-OMS)

**Project:** E-Commerce Order Management System (E-OMS) **Purpose:** To gather detailed operational requirements, identify current system weaknesses (data duplication, communication gaps, stock errors), and define the necessary functional and non-functional requirements for the new E-OMS. **Target Audience:** Internal Operational Stakeholders (Sales, Finance, Inventory, Logistics, Customer Support, Catalog Management).

---

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

| Statement (Current State)                                                                                                                                      | 1 (SD) | 2 (D) | 3 (N) | 4 (A) | 5 (SA) |
| :------------------------------------------------------------------------------------------------------------------------------------------------------------- | :----- | :---- | :---- | :---- | :----- |
| **A. Data Duplication:** I frequently have to manually re-enter order details into multiple disconnected systems.                                              | [ ]    | [ ]   | [ ]   | [ ]   | [ ]    |
| **B. Communication Gaps:** It is difficult to get a real-time order status update from another department (e.g., Inventory asking Finance if payment cleared). | [ ]    | [ ]   | [ ]   | [ ]   | [ ]    |
| **C. Stock Errors:** Our current inventory data frequently conflicts with the physical stock count or causes fulfillment issues.                               | [ ]    | [ ]   | [ ]   | [ ]   | [ ]    |
| **D. Manual Work:** The time spent on manual administrative tasks significantly delays order processing.                                                       | [ ]    | [ ]   | [ ]   | [ ]   | [ ]    |

## SECTION III: Functional Requirements (System Capabilities)

Functional requirements define the activities the system must perform. Please answer the following based on the required E-OMS capabilities:

3. **Order Validation (Sales/Verification):** When validating an order, what percentage of necessary customer and product data is typically missing or inaccurate in the current system?
    - [ ] Less than 5%
    - [ ] 5%–15%
    - [ ] 16%–30%
    - [ ] More than 30%
4. **Product Catalog Management (If Applicable):** If you are responsible for adding products, what is the single most time-consuming step in defining a new product and its description?
    - ---
        
5. **Inventory Tracking & Reservation (Inventory/Warehouse):** How quickly do you need inventory levels to update after an item is reserved or replenished?
    - [ ] Immediately (Real-time)
    - [ ] Within 10 minutes
    - [ ] Within 1 hour
    - [ ] End of day
6. **Logistics & Shipping (Logistics):** What is the most common reason for shipment planning delays (e.g., incorrect customer address format, missing courier rate information, etc.)?
    - ---
        
7. **Customer Support (Support):** When managing returns and refunds, what information does the current system lack that would most improve resolution time?
    - ---
        

## SECTION IV: Non-Functional Requirements (FURPS+)

Non-functional requirements describe system characteristics, constraints, and performance goals. Please rate the importance of the following characteristics for the new E-OMS (1=Not Important, 5=Absolutely Critical):

|Requirement Type (FURPS+)|Characteristic|1 (NI)|2 (LI)|3 (M)|4 (I)|5 (AC)|
|:--|:--|:--|:--|:--|:--|:--|
|**Performance**|**P1:** The system must process payment authorization and update inventory reservation status within 5 seconds.|[ ]|[ ]|[ ]|[ ]|[ ]|
|**Reliability**|**R1:** The system must be available 24/7, with no unscheduled downtime.|[ ]|[ ]|[ ]|[ ]|[ ]|
|**Usability**|**U1:** The user interface (screens/reports) must be simple enough to require less than 1 hour of new user training per module.|[ ]|[ ]|[ ]|[ ]|[ ]|
|**Security**|**S1:** The system must meet all current industry standards for securely handling customer payment details (Finance).|[ ]|[ ]|[ ]|[ ]|[ ]|

8. **Open Feedback:** Please provide any additional suggestions regarding current processes or essential features the new E-OMS must include to make your job more efficient.
    - ---
