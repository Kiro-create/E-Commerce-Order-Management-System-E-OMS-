## 📄 E-Commerce Order Management System (E-OMS)

| Name                | Assigned Department / Role               |
| ------------------- | ---------------------------------------- |
| _Ali Tamer_         | Team Leader / Sales & Order Verification |
| _Abdelrahman Amr_   | Customer Support & Reporting             |
| _Kirollos Raafat_   | Logistics & Shipping                     |
| _Omar Mohammed_     | Inventory Management                     |
| _Abdelrahman Ahmed_ | Finance & Payment                        |

---

## 🌐 _Overview_

This project designs an integrated **Order Management System (E-OMS)** for _E-Market Inc._, an online retailer offering electronics, apparel, and household products.  
The system connects major departments — _Sales, Finance, Inventory, Logistics,_ and _Customer Support_ — while integrating with external partners such as _payment gateways, suppliers,_ and _courier services_.

The goal is to model and automate the full **order lifecycle** — from order placement to final delivery — applying _Systems Analysis and Design_ principles to improve coordination, accuracy, and efficiency.

---

## ⚙️ _System Description_

When a customer places an order, the system automatically records the **date of receipt** and generates a **unique Order ID**.  
The process begins with **Order Verification (Sales)**, where the system validates order details, product data, and customer information. If everything is correct, it moves on to the next step; otherwise, the order is cancelled and the customer is notified.

Next is **Payment Processing (Finance)**. The Finance module securely sends payment details to the gateway for authorization. Once approved, the system confirms the payment to the customer. Failed payments automatically trigger order cancellation.

Following payment, the **Inventory Department** checks product availability. If items are in stock, they’re reserved for packaging; if not, a **replenishment request** is sent to suppliers to restock.

After confirming item availability, the **Logistics Department** plans the shipment. It determines delivery routes, selects an appropriate courier, and assigns both a tracking number and estimated delivery date.

Finally, **Sales and Logistics** handle the completion phase — generating a detailed invoice covering product and shipping costs. The customer receives their order summary and tracking information, while **Customer Support** manages any post-delivery issues to ensure satisfaction and feedback handling.

---

## 🎯 _System Goals_

- Automate and streamline the entire order process
    
- Ensure accuracy and synchronization between departments
    
- Strengthen coordination with external partners
    
- Offer customers real-time order tracking and updates
    
- Provide management with integrated reports and analytics
    

---

## 💡 _Key Features_

- Online product catalog & order placement
    
- Automated order validation & payment verification
    
- Real-time inventory tracking & reservation
    
- Courier integration with shipment planning
    
- Email/SMS notifications for every order stage
    
---

## 👥 _Target Users & Stakeholders_

|Category|Stakeholders|Responsibilities|
|---|---|---|
|_External – Operational_|Customers|Place orders, make payments, track deliveries|
|_Internal – Operational_|Sales, Warehouse, Support|Manage orders, inventory, and customer communication|
|_Internal – Executive_|Management, Admins|Monitor operations, analyze sales, and oversee performance|
|_External – Partners_|Payment Gateways, Couriers, Suppliers|Handle payments, shipping, and stock replenishment|

---

## 🧩 _Problem & Value_

**Problem:**  
Conventional e-commerce systems use disconnected tools, leading to data duplication, communication gaps, and stock errors.

**Value:**  
E-OMS centralizes processes, minimizes manual work, improves coordination, and provides real-time visibility, reducing delays and increasing operational efficiency.

---

## 📌 _Project Scope & Limitations_

**Scope Includes:**

- End-to-end order management
    
- Payment verification & invoicing
    
- Inventory tracking & shipment scheduling
    
- Returns & refunds workflow
    

**Limitations:**

- Excludes marketing or recommendation systems
    
- Focuses only on **core order management**, excluding accounting or HR modules
    
- Courier delivery, supplier management, and payment authorization depend on **external partners’ systems** — outside E-OMS’s control
    