

---

### Table 1: Event Decomposition Technique 



| Event (Trigger)                              | Type           | Use Case                                          | Actor                      |
| :------------------------------------------- | :------------- | :------------------------------------------------ | :------------------------- |
| **Customer submits order**                   | External Event | **Place Online Order** (US 7)                     | Customer                   |
| **Order details require verification**       | State Event    | **Verify Order Details** (US 1)                   | Sales Staff                |
| **Customer submits payment details**         | External Event | **Process Customer Payment** (US 4)               | Customer, Finance staff    |
| **Payment Gateway returns status code**      | External Event | **Handle Payment Authorization Response** (US 11) | Payment Gateway            |
| **Order receives payment confirmation**      | State Event    | **Reserve Inventory** (US 2)                      | Inventory Staff            |
| **Inventory Staff initiates catalog update** | External Event | **Manage Product Catalog** (US 3)                 | Inventory Staff            |
| **Stock level drops below reorder point**    | State Event    | **Send Replenishment Request** (US 10)            | Supplier System            |
| **Inventory confirms order is packaged**     | State Event    | **Plan Shipment** (US 5)                          | Logistics Staff            |
| **Shipment manifest requires transmission**  | State Event    | **Transmit Shipment Manifest** (US 12)            | Courier / Delivery Company |
| **Customer requests order status**           | External Event | **Track Order Status** (US 8)                     | Customer                   |
| **Customer submits return request**          | External Event | **Initiate Return Request** (US 9)                | Customer                   |
| **Customer Support Agent needs history**     | External Event | **Look Up Order History** (US 6)                  | Customer Support Agent     |
| **Time to generate management reports**      | Temporal Event | **Generate Management Reports** (US 13)           | Manager / Executive        |
| **System Administrator updates permissions** | External Event | **Manage User Permissions** (US 14)               | System Administrator       |

***

### Table 2: Use Case Description



| Use Case                                  | Description                                                                                                                                                                                      |
| :---------------------------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Place Online Order**                    | Allows the Customer to browse the product catalog, add items to a cart, confirm delivery details, and submit the order, resulting in the automatic generation of a unique Order ID.              |
| **Verify Order Details**                  | Allows the Sales module to automatically verify order details, product data, and customer information to ensure order accuracy before transition to the payment stage.                           |
| **Process Customer Payment**              | Enables the Finance module to securely handle customer payment details by requesting authorization from integrated gateways to ensure error-free billing and compliance with security standards. |
| **Handle Payment Authorization Response** | Receives the status code (Success or Failure) from the external Payment Gateway and updates the order status accordingly, completing the transaction authorization process.                      |
| **Reserve Inventory**                     | Upon successful payment confirmation, the system automatically checks real-time stock levels, decreases the available count, and marks the items as reserved for the specific order.             |
| **Manage Product Catalog**                | Allows authorized Inventory Staff to add, update, or delete products and their descriptions to maintain an up-to-date and accurate product catalog visible to customers.                         |
| **Send Replenishment Request**            | When a product's stock level falls below a defined reorder point, the E-OMS automatically transmits a request to the designated Supplier System to expedite restocking.                          |
| **Plan Shipment**                         | Allows the Logistics staff to finalize shipment details, including determining routes and selecting a courier, in preparation for delivery.                                                      |
| **Transmit Shipment Manifest**            | Communicates accurate customer delivery address and the unique tracking number to the external Courier System to optimize route planning and ensure timely pickup.                               |
| **Track Order Status**                    | Allows the Customer to access the order tracking interface using their tracking ID to view the current operational status (e.g., Shipped, Delivered) and the estimated delivery date.            |
| **Initiate Return Request**               | Allows the Customer to submit a request for a return or refund via the designated system interface, ensuring the initiation of the returns and refunds workflow.                                 |
| **Look Up Order History**                 | Allows the Customer Support Agent to search for and access a complete history of a customer's orders, status, and associated return/refund requests to reduce resolution time.                   |
| **Generate Management Reports**           | Provides Managers and Executives with integrated analytical and summary reports displaying current data on Key Performance Indicators (KPIs) to aid in business decisions.                       |
| **Manage User Permissions**               | Allows the System Administrator to manage user roles and specific access permissions for staff to enforce system security and maintain data integrity.                                           |



