
---

### Table 1: Event Decomposition Technique 

| Event (Trigger)                              | Type           | Use Case                                | Actor                   |
| :------------------------------------------- | :------------- | :-------------------------------------- | :---------------------- |
| **Customer submits order**                   | External Event | **Place Online Order** (US 7)           | Customer                |
| **Customer submits payment details**         | External Event | **Process Customer Payment** (US 4)     | Customer, Finance staff |
| **Inventory Staff initiates catalog update** | External Event | **Manage Product Catalog** (US 3)       | Inventory Staff         |
| **Inventory confirms order is packaged**     | State Event    | **Plan Shipment** (US 5)                | Logistics Staff         |
| **Customer requests order status**           | External Event | **Track Order Status** (US 8)           | Customer                |
| **Customer submits return request**          | External Event | **Initiate Return Request** (US 9)      | Customer                |
| **Customer Support Agent needs history**     | External Event | **Look Up Order History** (US 6)        | Customer Support Agent  |
| **Time to generate management reports**      | Temporal Event | **Generate Management Reports** (US 13) | Manager / Executive     |
| **System Administrator updates permissions** | External Event | **Manage User Permissions** (US 14)     | System Administrator    |

***

### Table 2: Use Case Description

| Use Case                        | Description                                                                                                                                                                                                                                                                                               |
| :------------------------------ | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Place Online Order**          | The customer selects products from the catalog, adds them to the shopping cart, provides delivery details, and the system automatically verifies product availability, pricing, and customer information for accuracy before generating a unique Order ID and preparing the order for payment processing. |
| **Process Customer Payment**    | The system securely processes the customer’s chosen payment method by validating details, confirming authorization, verifying funds, recording the transaction, and updating the order status upon success.                                                                                               |
| **Manage Product Catalog**      | Authorized Inventory Staff manage the catalog by adding, updating, or deleting products, while the system tracks inventory, reserves stock for orders, and automatically sends replenishment requests to the Supplier System when stock falls below the reorder point.                                    |
| **Plan Shipment**               | The Logistics Staff finalizes shipment details—including courier selection, delivery routes, and pickup scheduling—and the system automatically sends the shipment manifest with the customer’s address and tracking number to the external Courier System for timely, accurate delivery.                 |
| **Track Order Status**          | Allows the Customer to access the order tracking interface using their tracking ID to view the current operational status (e.g., Shipped, Delivered) and the estimated delivery date.                                                                                                                     |
| **Initiate Return Request**     | Allows the Customer to submit a request for a return or refund via the designated system interface, ensuring the initiation of the returns and refunds workflow.                                                                                                                                          |
| **Look Up Order History**       | Allows the Customer Support Agent to search for and access a complete history of a customer's orders, status, and associated return/refund requests to reduce resolution time.                                                                                                                            |
| **Generate Management Reports** | Provides Managers and Executives with integrated analytical and summary reports displaying current data on Key Performance Indicators (KPIs) to aid in business decisions.                                                                                                                                |
| **Manage User Permissions**     | Allows the System Administrator to manage user roles and specific access permissions for staff to enforce system security and maintain data .                                                                                                                                                    |



