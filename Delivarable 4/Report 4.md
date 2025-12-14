
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
