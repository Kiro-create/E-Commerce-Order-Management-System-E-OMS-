
## Step 1 — Identify candidate nouns (source: use cases, system vision, technical reports, user stories)

Customer, Order, Order ID, Product, Product Description, Price, Inventory, InventoryItem, Warehouse, Stock Level, Replenishment Request, Supplier, Payment, Payment Authorization, Payment Gateway, Invoice, Shipment, Tracking Number, Courier, Order Status, Return Request, Refund, Customer Support Agent, Staff, SalesStaff, FinanceStaff, InventoryStaff, LogisticsStaff, SupportAgent, Report, KPI, Address, Delivery Details, OrderItem, Quantity, Transaction, Notification (system output).

---

## Step 2 — Refine and classify nouns (Include / Exclude / Research)

Use the textbook decision questions: is it a unique thing the system needs to remember; is it in scope; does the system need to store multiple instances; is it merely an output or attribute?

|Noun|Decision|Short rationale (trace to project file)|
|---|---|---|
|Customer|**Include**|Appears as primary actor for orders/returns.|
|Order|**Include**|Core transaction; generated Order ID on placement.|
|OrderItem|**Include**|Represents items within Order (quantity, price).|
|Product|**Include**|Managed in catalog; used in verification and inventory.|
|InventoryItem|**Include**|Tracks stock levels and reservations.|
|Warehouse|**Include**|Location for stored inventory.|
|binLocation|**Exclude (attribute)**|No bin management use case; keep as attribute if needed.|
|Supplier|**Include**|Receives replenishment requests.|
|ReplenishmentRequest|**Include**|Triggered when stock low.|
|Payment|**Include**|Payment processing and authorization flows present.|
|Payment Gateway|**Exclude (external actor)**|External system, not a stored domain class.|
|Invoice|**Include**|Generated after payment; appears in scope.|
|Shipment|**Include**|Logistics plans shipments and assigns tracking.|
|Courier|**Include**|External delivery partner referenced in shipment flow.|
|ReturnRequest|**Include**|Customer returns/refunds workflow (US9).|
|Refund|**Exclude (process/attribute)**|Handled within ReturnRequest or Payment status.|
|Staff (abstract)|**Include**|Multiple staff roles appear as actors.|
|SalesStaff / FinanceStaff / InventoryStaff / LogisticsStaff / SupportAgent|**Include**|Domain role specializations (actors).|
|Report|**Include**|Management reporting use case (US13).|
|Notification (Email/SMS)|**Exclude (system output)**|Output/event, not persistent domain class.|
|ProductCatalog|**Exclude**|Catalog referenced conceptually; project stores Product instances only.|

---

## Step 3 — Produce final domain class list (confirmed from project files)

Customer; Order; OrderItem; Product; InventoryItem; Warehouse; Supplier; ReplenishmentRequest; Payment; Invoice; Shipment; Courier; ReturnRequest; Staff (abstract) and subclasses (SalesStaff, FinanceStaff, InventoryStaff, LogisticsStaff, SupportAgent); Report.


---

## Step 4 — For each included class: candidate key attributes (tabular)

| Domain class             | Key attributes (candidates)                                                                 |
| ------------------------ | ------------------------------------------------------------------------------------------- |
| **Customer**             | customerId {key}, fullName, email, phone, defaultAddress                                    |
| **Order**                | orderId {key}, orderDate, status, totalAmount, customerId (FK)                              |
| **OrderItem**            | orderItemId {key}, orderId (FK), productId (FK), quantity, unitPrice, lineTotal             |
| **Product**              | productId {key}, sku, name, description, price, category                                    |
| **InventoryItem**        | inventoryId {key}, productId (FK), warehouseId (FK), quantityOnHand, reorderPoint, status   |
| **Warehouse**            | warehouseId {key}, name, location                                                           |
| **Supplier**             | supplierId {key}, name, contactInfo                                                         |
| **ReplenishmentRequest** | requestId {key}, productId (FK), supplierId (FK), quantity, requestDate, status             |
| **Payment**              | paymentId {key}, orderId (FK), amount, method, authorizationCode, status, paymentDate       |
| **Invoice**              | invoiceId {key}, orderId (FK), invoiceDate, total, tax, shippingCharges                     |
| **Shipment**             | shipmentId {key}, orderId (FK), courierId (FK), trackingNumber, shipDate, estimatedDelivery |
| **Courier**              | courierId {key}, name, contactInfo, apiEndpoint                                             |
| **ReturnRequest**        | returnId {key}, orderId (FK), reason, requestDate, status                                   |
| **Staff (abstract)**     | staffId {key}, fullName, role                                                               |
| **Report**               | reportId {key}, type, generatedDate, parameters                                             |

(Attributes kept minimal — only those explicitly supported or implied by project files.)

---

## Step 5 — Preliminary relationships, type, and multiplicity (tabular)


|From|To|Relationship type|Multiplicity (From → To)|Rationale / trace|
|---|---|---|---|---|
|Customer|Order|association|Customer `1` → Order `0..*`|Customer places many orders.|
|Order|OrderItem|**composition**|Order `1` _—_ OrderItem `1..*`|Order owns its items; items don't exist without order.|
|OrderItem|Product|association|OrderItem `*` → Product `1`|Each order line refers to a product.|
|Product|InventoryItem|aggregation|Product `1` o-- `0..*` InventoryItem|Inventory entries reference products.|
|Warehouse|InventoryItem|association|Warehouse `1` → InventoryItem `0..*`|Warehouse stores inventory records.|
|InventoryItem|ReplenishmentRequest|association|InventoryItem `1` → ReplenishmentRequest `0..*`|Low stock triggers replenishment.|
|ReplenishmentRequest|Supplier|association|ReplenishmentRequest `*` → Supplier `1`|Requests are sent to supplier.|
|Order|Payment|association|Order `1` → Payment `0..*`|Multiple payment attempts/records possible.|
|Order|Invoice|association|Order `1` → Invoice `1..1`|Invoice generated per order (adjust if split invoicing used).|
|Order|Shipment|association|Order `1` → Shipment `0..*`|Allow split shipments.|
|Shipment|Courier|association|Shipment `*` → Courier `1`|Courier assigned to each shipment.|
|Order|ReturnRequest|association|Order `1` → ReturnRequest `0..*`|Returns reference orders.|
|Staff|Report|association|Staff `0..*` → Report `0..*`|Staff generate or request reports.|
|Staff (abstract)|SalesStaff, FinanceStaff, InventoryStaff, LogisticsStaff, SupportAgent|generalization|—|Role specializations for actor mapping.|

---

Step 7 — Class Diagram

![[Class Diagram 1.png]]