
## I. User Stories (Functional Requirements)

---

### 1. Internal – Operational Stakeholders

These stakeholders (Sales, Finance, Inventory, Logistics, and Customer Support Employees) interact with the system regularly to perform daily operations.

|**Role**|**Goal**|**Benefit**|
|---|---|---|
|**Sales Staff**|I want to **automatically verify order details, product data, and customer information**|so that I can **prevent data duplication and ensure order accuracy** before moving to payment.|
|**Inventory Staff**|I want to **automatically reserve items in stock** for confirmed orders|so that I can **ensure availability and prevent stock errors** during fulfillment.|
|**Inventory Staff**|I want to **add, update, or delete products and their descriptions**|so that I can **maintain an up-to-date and accurate product catalog**.|
|**Finance Staff**|I want the system to **securely process payments through integrated gateways**|so that I can **ensure error-free billing and compliance with security standards (S1)**.|
|**Logistics Staff**|I want to **generate a tracking ID and estimated delivery date** for a processed shipment|so that I can **streamline shipment planning and provide prompt customer updates**.|
|**Customer Support Agent**|I want to **access a complete history of customer orders and return requests**|so that I can **efficiently track issue status and reduce resolution time**.|

---

### 2. External – Operational Stakeholders

The primary external operational stakeholders are the **Customers** (End Users).

|**Role**|**Goal**|**Benefit**|
|---|---|---|
|**Customer**|I want to **browse the product catalog and place an online order**|so that I can **purchase desired products easily and securely**.|
|**Customer**|I want to **track my order status in real-time**|so that I can **know the exact location and expected delivery time** of my items.|
|**Customer**|I want to **request a return or refund for a delivered item**|so that I can **ensure my satisfaction and complete the returns and refunds workflow**.|

---

### 3. External – Partner Stakeholders

External partners include Suppliers, Payment Gateways, and Courier/Delivery Companies.

|**Role**|**Goal**|**Benefit**|
|---|---|---|
|**Supplier System**|I want to **automatically receive a replenishment request** when E-Market's stock is low|so that I can **expedite restocking and minimize product unavailability for customers**.|
|**Payment Gateway**|I want to **send payment authorization confirmation back to the Finance module quickly**|so that I can **process transactions efficiently and confirm the order for the customer**.|
|**Courier / Delivery Company**|I want to **automatically receive the finalized shipment manifest and accurate delivery details** from the Logistics module|so that I can **optimize route planning and ensure timely pickup** of the customer's order.|

---

### 4. Internal – Executive Stakeholders

These stakeholders (Management and System Administrators) monitor operations and define strategic metrics.

|**Role**|**Goal**|**Benefit**|
|---|---|---|
|**Manager / Executive**|I want to **view integrated analytical and summary reports**|so that I can **monitor sales performance, track KPIs, and oversee system performance**.|
|**System Administrator**|I want to **manage user roles and specific access permissions** for all staff|so that I can **enforce system security (S1) and maintain data integrity**.|

---

## II. Acceptance Criteria (E-OMS)

### 1. Internal – Operational Stakeholders

|**User Story**|**Acceptance Criteria (Given-When-Then Format)**|
|---|---|
|**US 1 (Sales Staff):**|**Given:** A customer has placed an order and the order details are available. **When:** The Sales module completes the automated Order Verification process. **Then:** The system checks product data and customer information validity; **And** if valid, the status updates to 'Awaiting Payment'; **Else** the order is automatically cancelled, and the customer is notified.|
|**US 2 (Inventory Staff - Reservation):**|**Given:** An order has successfully received payment confirmation. **When:** The Inventory module receives the order confirmation; **Then** the system checks real-time stock levels; **And** if in stock, the system automatically decreases the available stock count and marks the item(s) as reserved for that unique Order ID.|
|**US 3 (Inventory Staff - Catalog):**|**Given:** The Inventory Staff is logged in with authorized permissions. **When:** The staff submits a modification (add, update, or delete) to a product's details (name, description, or price). **Then:** The system saves the changes immediately and validates the required fields; **And** the updated product details are instantly reflected in the Online Product Catalog viewable by customers.|
|**US 4 (Finance Staff):**|**Given:** The order status is 'Awaiting Payment' and customer payment details are passed securely. **When:** The Finance module requests authorization from the integrated payment gateway. **Then:** The payment gateway returns a status code (Success or Failure); **And** the system confirms or cancels the order based on the response; **And** all data handling associated with the transaction meets industry security standards (S1).|
|**US 5 (Logistics Staff):**|**Given:** The Inventory team has confirmed the order is packaged and ready for shipment. **When:** The Logistics staff finalizes shipment planning (e.g., selects courier/route). **Then:** The system successfully communicates with the external Courier Service to generate a unique tracking ID; **And** the estimated delivery date is calculated and assigned to the order.|
|**US 6 (Customer Support Agent):**|**Given:** A Customer Support Agent enters a customer ID or Order ID into the Support module. **When:** The system executes the search request. **Then:** The system displays all historical orders, their current status, and the current status of any associated returns/refunds workflow; **And** the agent can update the issue status to reflect actions taken until resolution.|

### 2. External – Operational Stakeholders (Customer)

|**User Story**|**Acceptance Criteria (Given-When-Then Format)**|
|---|---|
|**US 7 (Customer - Placement):**|**Given:** I have added item(s) to the cart, provided complete delivery and contact details. **When:** I confirm the order and submit payment details. **Then:** The system automatically generates a unique Order ID; **And** the order status is set to 'Processing/Verification'; **And** I receive an immediate order confirmation notification (Email/SMS).|
|**US 8 (Customer - Tracking):**|**Given:** My order has been shipped and I have the unique tracking ID. **When:** I access the order tracking interface using the unique tracking ID. **Then:** The system displays the current operational status (e.g., Shipped, In Transit, Delivered); **And** the estimated delivery date is visible.|
|**US 9 (Customer - Returns):**|**Given:** I have received the order and the current date is within the allowed return window. **When:** I submit a return request via the designated system interface. **Then:** The system logs the request in the Customer Support module; **And** I receive an automated confirmation (Email/SMS) acknowledging the initiation of the returns process.|

### 3. External – Partner Stakeholders

|**User Story**|**Acceptance Criteria (Given-When-Then Format)**|
|---|---|
|**US 10 (Supplier System):**|**Given:** The Inventory module identifies a product stock level has fallen below the defined reorder point (a state event). **When:** The system registers the low-stock state change. **Then:** The E-OMS automatically transmits a replenishment request to the designated Supplier System; **And** the request includes the required quantity and product details.|
|**US 11 (Payment Gateway):**|**Given:** The E-OMS Finance module sends a secure payment request. **When:** The Payment Gateway authorizes the transaction (success or failure). **Then:** The Gateway returns the final status code to the E-OMS; **And** the entire payment authorization process (P1) is completed and reflected in the E-OMS.|
|**US 12 (Courier/Delivery Company):**|**Given:** The order has been assigned a tracking ID and is marked 'Ready for Pickup' by Logistics. **When:** The Logistics module transmits the shipment manifest to the Courier System. **Then:** The manifest successfully includes the accurate customer delivery address and the unique tracking ID; **And** the Courier System acknowledges receipt of the manifest data.|

### 4. Internal – Executive Stakeholders

|**User Story**|**Acceptance Criteria (Given-When-Then Format)**|
|---|---|
|**US 13 (Manager / Executive):**|**Given:** The Manager logs into the system with appropriate permissions. **When:** They select the "Analytical and Summary Reports" dashboard. **Then:** The system displays current, integrated data (accurate across Sales, Inventory, and Finance) on key performance indicators (KPIs); **And** the reports generate within a specified performance threshold.|
|**US 14 (System Administrator):**|**Given:** The System Administrator accesses the User Management panel. **When:** They modify the access permissions associated with a specific staff role (e.g., Logistics Staff). **Then:** The user associated with that role can immediately access only the system functions defined by the updated permissions; **And** all changes to permissions are logged securely by the system.|

---

## III. User Story Verification

### 1. Project Context and Objectives (E-OMS)

The project involves designing an integrated **E-OMS** for E-Market Inc.. The system must model and automate the **full order lifecycle**—from product catalog to final delivery.

- **Core Problem:** The project aims to overcome operational inefficiencies arising from reliance on **disconnected tools**, which currently cause **data duplication, communication gaps, and stock errors**.
    
- **Primary Goal:** To **automate and streamline the entire order process**, **ensure accuracy and synchronization between departments**, and **strengthen coordination with external partners**.
    
- **Stakeholders:** Analysis focused on four key stakeholder categories: **Internal Operational Staff** (Sales, Finance, Inventory, etc.), **External Operational Customers**, **External Partners** (Couriers, Suppliers), and **Executive Stakeholders** (Management, Admins).
    

### 2. Systems Analysis Activity and Techniques Used

Our activities align with the Systems Development Lifecycle (SDLC), specifically **Core Process 3: Discover and Understand Details** (System Analysis-Requirements Engineering), where identifying requirements is critical.

- **Technique:** We applied the **User Story** technique, which is favored by highly agile system development methodologies. User stories document **functional requirements** quickly and less formally.
    
- **Format:** All functional requirements were written using the standard template: **"As a `<role>` I want to `<goal>` so that `<benefit>`"**.
    
- **Acceptance Criteria:** For each story, we defined **Acceptance Criteria** (using the Given-When-Then format). These criteria identify the features that must be present at completion and serve as a **contract between the developers and the users**.
    

### 3. Verification of Effectiveness

We verified the effectiveness of the generated user stories and Acceptance Criteria based on the rules outlined in the sources:

- **User Story Verification:** Each story was confirmed to be effective because it:
    
    - **Covers a small chunk of functionality**.
        
    - **Delivers value on its own**.
        
    - Is written in a **simple way** to be **understood by everyone**.
        
    - **Does not include the solution or heavy technical information**.
        
- **Criteria Verification:** The Acceptance Criteria were verified to clarify exceptions and ensure the user story was defined at an appropriate level of analysis, defining the necessary observable outcome and expected results.
# 3. Event Decomposition

## 3.1 Perfect Technology Assumption

Under the Perfect Technology Assumption, the system is considered to operate in an ideal environment where all hardware, software, networks, and external systems function flawlessly. Therefore, technical or system-level events are excluded from the event decomposition because they do not represent business-driven requirements.

### Excluded Events (Not Business Events)
- System login, authentication, or session handling  
- System errors, crashes, or recovery operations  
- Network delays, timeouts, or reconnection logic  
- Automatic database backups or internal database operations  
- Internal system monitoring or performance tracking  
- Automatic retries for failed technical operations  
- Server maintenance or deployment-related tasks  

These events do not contribute to business processes and therefore are not included in the use case model. Only events triggered by users, external systems, internal business states, or time-based business rules are considered.


## 3.2 Event–Use Case Mapping

| Event (Trigger)                            | Type           | Use Case Triggered                 |
| ------------------------------------------ | -------------- | ---------------------------------- |
| Customer submits order                     | External Event | Place Online Order (US7)           |
| Customer submits payment details           | External Event | Process Customer Payment (US4)     |
| Inventory Staff initiates catalog update   | External Event | Manage Product Catalog (US3)       |
| Inventory confirms order is packaged       | State Event    | Plan Shipment (US5)                |
| Customer requests order status             | External Event | Track Order Status (US8)           |
| Customer submits return request            | External Event | Initiate Return Request (US9)      |
| Customer Support Agent needs order history | External Event | Look Up Order History (US6)        |
| **Time to generate management reports**    | Temporal Event | Generate Management Reports (US13) |
| System Administrator updates permissions   | External Event | Manage User Permissions (US14)     |

# 3.3 Brief Use Case Descriptions

| #   | Use Case Name               | ID   | Brief Description                                                                 |
| --- | --------------------------- | ---- | --------------------------------------------------------------------------------- |
| 1   | Place Online Order          | US7  | Customer builds order; system validates details and generates Order ID.           |
| 2   | Manage Product Catalog      | US3  | Inventory Staff adds, edits, or removes products from the catalog.                |
| 3   | Process Customer Payment    | US4  | System securely validates, authorizes, and records payment; updates order status. |
| 4   | Plan Shipment               | US5  | Logistics Staff plans and prepares shipment once items are packaged.              |
| 5   | Look Up Order History       | US6  | Customer Support Agent retrieves a customer’s complete order history.             |
| 6   | Track Order Status          | US8  | Customer checks the current status of their order using a tracking ID.            |
| 7   | Initiate Return Request     | US9  | Customer submits a request to return or refund an order.                          |
| 8   | Generate Management Reports | US13 | System generates periodic management and KPI reports.                             |
| 9   | Manage User Permissions     | US14 | Administrator updates system user roles and permissions.                          |

---

# 4. Include and Extend Relationships

### «include» Relationships (Mandatory)
These use cases ALWAYS require the included ones to complete their process.

| Base Use Case | Included Use Case | Relationship | Description |
|---------------|------------------|--------------|-------------|
| Place Online Order (US7) | Process Customer Payment (US4) | «include» | Payment must be processed as part of placing an order. |
| Place Online Order (US7) | Reserve Inventory (US2) | «include» | Items must be reserved after an order is placed. |
| Process Customer Payment (US4) | Handle Payment Authorization Response (US11) | «include» | Payment processing requires gateway authorization handling. |
| Reserve Inventory (US2) | Send Replenishment Request (US10) | «include» | Stock reservation triggers replenishment when levels are low. |
| Plan Shipment (US5) | Transmit Shipment Manifest (US12) | «include» | Planning shipment requires transmitting the manifest. |
| Generate Management Reports (US13) | Manage User Permissions (US14) | «include» | Report access requires checking user permissions. |

---

### «extend» Relationships (Optional / Conditional)
These use cases activate ONLY under certain conditions.

| Base Use Case | Extending Use Case | Relationship | Condition / Description |
|---------------|--------------------|--------------|--------------------------|
| Verify Order Details (US1) | Track Order Status (US8) | «extend» | If verification requires status lookup. |
| Verify Order Details (US1) | Handle Payment Authorization Response (US11) | «extend» | If payment authorization must be rechecked. |
| Initiate Return Request (US9) | Track Order Status (US8) | «extend» | To check order status before return approval. |
| Plan Shipment (US5) | Track Order Status (US8) | «extend» | Shipping planning may require checking order progress. |
| Transmit Shipment Manifest (US12) | Generate Management Reports (US13) | «extend» | Manifest updates may trigger report generation. |
| Look Up Order History (US6) | Generate Management Reports (US13) | «extend» | Order history lookup may optionally generate a report. |


# 6. UML Use Case Diagram

![[UseCaseDiagram.jpg]]

## Primary Use Cases

### Use Cases
- Place Online Order (US7)
- Verify Order Details (US1)
- Reserve Inventory (US2)
- Manage Product Catalog (US3)
- Process Customer Payment (US4)
- Plan Shipment (US5)
- Look Up Order History (US6)
- Track Order Status (US8)
- Initiate Return Request (US9)
- Send Replenishment Request (US10)
- Handle Payment Authorization Response (US11)
- Transmit Shipment Manifest (US12)
- Generate Management Reports (US13)
- Manage User Permissions (US14)

---

## Actors
- Customer  
- Sales Staff  
- Finance Staff  
- Inventory Staff  
- Logistics Staff  
- Customer Support Agent  
- System Administrator  
- Payment Gateway  
- Supplier System  
- Delivery Company  
- Manager / Executive  


## Key Relationships (Textual)

### **Actor → Use Case Relationships**
- **Customer** interacts with: *Place Online Order*, *Track Order Status*, *Initiate Return Request*, and indirectly with *Look Up Order History*.
- **Sales Staff** triggers: *Verify Order Details*.
- **Finance Staff** performs: *Process Customer Payment*.
- **Payment Gateway** interacts with: *Handle Payment Authorization Response*.
- **Inventory Staff** operates: *Reserve Inventory* and *Manage Product Catalog*.
- **Supplier System** responds to: *Send Replenishment Request*.
- **Logistics Staff** performs: *Plan Shipment*.
- **Courier / Delivery Company** receives: *Transmit Shipment Manifest*.
- **Customer Support Agent** uses: *Look Up Order History*.
- **System Administrator** maintains: *Manage User Permissions*.
- **Manager / Executive** views: *Generate Management Reports*.

---

### **Use Case → Use Case Relationships**

#### **Include (Mandatory)**
- *Place Online Order* **includes** *Verify Order Details*.
- *Place Online Order* **includes** *Process Customer Payment*.
- *Process Customer Payment* **includes** *Handle Payment Authorization Response*.
- *Reserve Inventory* **includes** *Send Replenishment Request* when stock is low.
- *Plan Shipment* **includes** *Transmit Shipment Manifest*.

#### **Extend (Optional / Conditional)**
- *Initiate Return Request* **extends** *Look Up Order History* when verification is needed.
- *Track Order Status* **extends** processes such as *Verify Order Details* and *Plan Shipment* in conditional scenarios.
- *Transmit Shipment Manifest* **extends** *Generate Management Reports* when reporting is triggered.


# 7. Jira Project Management Evidence

![[image.png]]
![[Pasted image 20251116172733.png]]

# 8. GitHub Evidence

Repository Link: [https://github.com/Kiro-create/E-Commerce-Order-Management-System-E-OMS-](https://github.com/Kiro-create/E-Commerce-Order-Management-System-E-OMS-)

(Repository referenced in project documentation; contains source files, user stories, and system vision documentation.)

# 9. Conclusion

## Conclusion

The E-Commerce Order Management System (E-OMS) was successfully analyzed using a structured event-driven approach. Through the Event Decomposition Technique, all external, state, and temporal triggers were identified and mapped to their corresponding use cases, ensuring full coverage of system functionality. The identification of primary actors and their interactions with the system clarified the operational boundaries and responsibilities within the business process.

The include and extend relationships between use cases provided a clear understanding of mandatory sub-processes and optional or conditional behaviors, enabling a modular and maintainable system design. Brief use case descriptions further summarized the functional requirements, ensuring that each system behavior is well-defined and aligned with user and organizational needs.

Overall, this analysis establishes a complete, well-structured foundation for system design and development. It ensures traceability from events to use cases, supports accurate requirement modeling, and provides a solid basis for future stages, including detailed specifications, UML modeling, implementation, and testing.
