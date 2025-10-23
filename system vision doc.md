## System Vision Document: E-Commerce Order Management System (E-OMS)

### 1. Purpose (Problem Description)

The fundamental purpose of the E-OMS project is to overcome critical operational inefficiencies resulting from E-Market Inc.’s reliance on **conventional e-commerce systems that utilize disconnected tools**. This fragmented system approach currently leads to significant challenges, including **data duplication, communication gaps, and stock errors**.

The E-OMS is required to model and automate the **full order lifecycle—from order placement to final delivery**—by implementing an integrated system that connects major internal departments and external partners.

### 2. Scope (System Capabilities and Boundaries)

The E-OMS is designed as an **integrated system** connecting Sales, Finance, Inventory, Logistics, and Customer Support, and integrates with external entities such as suppliers, courier services, and payment gateways.

**Inclusions (Core Scope):** The project scope includes end-to-end order management, covering the entire lifecycle from placement through final delivery. Key capabilities are designed to handle:

- **Order Validation and Processing:** Automated recording and generation of a unique Order ID upon placement, followed by validation of details, product data, and customer information.
- **Financial Processing:** Secure payment handling, sending details to a gateway for authorization, and confirming payment (or triggering automatic cancellation upon failure). The system also handles the generation of detailed invoices.
- **Inventory and Logistics:** **Real-time inventory tracking and reservation**. If products are out of stock, a replenishment request is sent to suppliers. The system plans shipment, determines routes, selects a courier, and assigns a tracking number and estimated delivery date.
- **Customer Interaction:** Email/SMS notifications for every stage of the order process, and support for the **returns and refunds workflow**.

**Exclusions (Limitations):** The E-OMS project is strictly focused on core order management. It specifically **excludes marketing or recommendation systems**. It also **excludes accounting or Human Resources (HR) modules**. The functioning of courier delivery, supplier management, and payment authorization are reliant upon the stability and function of external partners’ systems, which are outside the control of the E-OMS.

### 3. Goals (Business Benefits)

The primary goals of the E-OMS are to centralize core processes and provide business value by:

1. **Increase Operational Efficiency:** The system is intended to **automate and streamline the entire order process** and **minimize manual work**, which will directly result in **reduced delays** and higher overall operational efficiency.
2. **Improve Data Accuracy and Coordination:** A critical goal is to **ensure accuracy and synchronization between departments** by resolving the communication gaps and data duplication challenges identified in the problem.
3. **Strengthen Partner Relations:** The system aims to **strengthen coordination with external partners** (including suppliers and couriers).
4. **Maximize Customer Experience:** The E-OMS goal is to **offer customers real-time order tracking and updates**, and ensure satisfaction through efficient handling of post-delivery issues.

---

_This System Vision Document serves as the foundational agreement for the E-Commerce Order Management System project, initiated during Core Process 1 of the Systems Development Lifecycle (SDLC)._