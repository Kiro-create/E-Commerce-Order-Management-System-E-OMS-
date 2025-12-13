
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

* Shipment Planning Dashboard
* Shipping Manifest Review Screen
---

## **Use Case 5: Track Order Status**

Required User Interfaces:

* Orders & Tracking Screen

---



# **1(b) SYSTEM INTERFACES (Automated Connections)**


---

## **Use Case 1: Place Online Order**

System Interfaces:
* **Product Database Interface** (read product info, pricing, stock)
* **Inventory System Interface** (reserve stock)
* **Customer Database Interface** (load saved addresses)
* **Order Database Interface** (create order record)
* **Email/SMS Notification Service** (send order confirmation)

---

## **Use Case 2: Process Customer Payment**

System Interfaces:

* **External Payment Gateway API** (authorization, charge, tokenization)
* **Fraud Detection Module** (optional)
* **Payment Database Interface** (save payment result)
* **Order System Interface** (update order status to “Paid”)

---

## **Use Case 3: Manage Product Catalog**

System Interfaces:

* **Product Database Interface** (create/update/delete products)
* **Inventory Database Interface** (update stock levels)
* **Supplier System Interface** (send replenishment requests when stock is low)

---

## **Use Case 4: Plan Shipment**

System Interfaces:

* **Shipment Database Interface** (create shipment record)
* **Courier API Interface** (send manifest, request tracking number)
* **Order System Interface** (update order status to “Shipped”)

---

## **Use Case 5: Track Order Status**

System Interfaces:

* **Order Database Interface** (retrieve status, history)
* **Courier Tracking API** (pull live tracking updates)
* **Notification System** (send shipping status updates)

---



# **Internal System Interfaces**

### **1. Customer Database Interface**

Handles CRUD operations for all customer-related data.
**Tables involved:** Customer

### **2. Order Database Interface**

Supports creation, update, and retrieval of customer orders and order items.
**Tables involved:** Order, Order_Item

### **3. Product & Inventory Database Interface**

Manages product details, pricing, availability, and stock levels.
**Tables involved:** Product, Inventory

### **4. Payment Database Interface**

Stores and updates payment transactions and verification results.
**Tables involved:** Payment

### **5. Shipment & Delivery Database Interface**

Handles shipment processing, delivery status updates, and assignment of tracking numbers.
**Tables involved:** Shipment, Delivery

### **6. Supplier Database Interface**

Used internally for referencing supplier details when stock replenishment is required.
**Tables involved:** Supplier

---

# **External System Interfaces**

### **7. Payment Gateway API**

Processes customer payments and returns authorization results.
**Exchanged Data:** Card/token data, transaction results

### **8. Supplier System API (Replenishment Requests)**

Automatically sends low-stock alerts or restocking requests to suppliers.
**Exchanged Data:** Product ID, stock level, quantity required

### **9. Courier Tracking & Manifest API**

Used for shipment planning, label generation, and tracking updates.
**Exchanged Data:** Delivery address, parcel details, tracking number, manifest

### **10. Notification System API (Email/SMS)**

Sends automated notifications such as order confirmations, payment receipts, and shipment updates.
**Exchanged Data:** Email content, phone numbers, status messages

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

# **ADMIN / STAFF MENU

Catalog Management
- View Product Catalog
- Add Product
- Edit Product
- Update Inventory

Shipment Planning
- View Orders Ready for Shipment
- Review Shipment Manifest

# **(a) storyboard**

![[storyboard.PNG]]