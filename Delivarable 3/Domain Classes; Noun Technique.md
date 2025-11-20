### 1 — Step 1: Identify all candidate nouns

Candidate noun: Customer, Order, Order ID, Cart, Product, Product Catalog, Product Description, Price, Inventory, InventoryItem, Stock level, Replenishment Request, Supplier, Supplier System, Payment, Payment Gateway, Payment Authorization, Invoice, Shipment, Tracking Number, Courier, Shipment Manifest, Logistics, Warehouse, Inventory Bin, Order Status, Return Request, Refund, Customer Support Agent, Staff, User, Role, Manager, Report, KPI, Notification (Email/SMS), User Permissions, Session, Invoice, Payment Method, Address, Delivery Details, Package, OrderItem, Quantity, InvoiceLine, Transaction

### 2 — Step 2 & 3: Refine list — decide Include / Exclude / Research

| **Noun**                                                                                          | **Decision**                                             | **Rationale**                                                                                   |
| ------------------------------------------------------------------------------------------------- | -------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| **Customer**                                                                                      | **Include**                                              | Core actor; system stores many customers                                                        |
| **Order**                                                                                         | **Include**                                              | Core business transaction; Order ID generated                                                   |
| **OrderItem**                                                                                     | **Include**                                              | Represents product lines in an Order (quantity, price)                                          |
| **Product**                                                                                       | **Include**                                              | Appears in catalog; has attributes (name, price, desc)                                          |
| **ProductCatalog**                                                                                | **Include**                                              | Catalog entity for product listings                                                             |
| **InventoryItem**                                                                                 | **Include**                                              | Tracks stock and states (low, out)                                                              |
| **Supplier / SupplierSystem**                                                                     | **Include**                                              | Replenishment requests sent to suppliers                                                        |
| **Payment / PaymentGateway**                                                                      | **Include**                                              | Authorized payment interactions; external actor                                                 |
| **Invoice**                                                                                       | **Include**                                              | System generates invoices                                                                       |
| **Shipment / Tracking / Courier / ShipmentManifest**                                              | **Include**                                              | Logistics entities; tracking numbers assigned                                                   |
| **ReturnRequest / Refund**                                                                        | **Include**                                              | Customer returns workflow tracked                                                               |
| **Staff (abstract) / SalesStaff / InventoryStaff / FinanceStaff / LogisticsStaff / SupportAgent** | **Include (Staff as superclass)**                        | Actors with role-specific privileges; model as Staff superclass with specialized subclasses     |
| **Warehouse / InventoryBin**                                                                      | **Include (Warehouse + bins compose inventory storage)** | Needed to model inventory composition                                                           |
| **Notification (Email/SMS)**                                                                      | **Research**                                             | Often modeled as system operation or output, not stored as independent entity — mark for review |
| **Session / Login / Password**                                                                    | **Exclude for domain model (platform control)**          | Out of scope per perfect-technology assumption (handle later).                                  |
| **KPI / Report**                                                                                  | **Include (Report as generated artifact)**               | Reports derive from domain data; include Report class with generation temporal event            |
| **Package**                                                                                       | **Research**                                             | May be an attribute of Shipment or an aggregate class depending on business rules               |

### 3 — Step 4: For included nouns, identify key attributes (tabular)

| **Domain class**         | **Key attributes (candidate)**                                                                          |
| ------------------------ | ------------------------------------------------------------------------------------------------------- |
| **Customer**             | `customerId` {key}, `fullName`, `email`, `phone`, `defaultAddress`, `registrationDate`                  |
| **Order**                | `orderId` {key}, `orderDate`, `status`, `totalAmount`, `paymentStatus`, `customerId` (FK)               |
| **OrderItem**            | `orderItemId` {key}, `orderId` (FK), `productId` (FK), `quantity`, `unitPrice`, `lineTotal`             |
| **Product**              | `productId` {key}, `sku`, `name`, `description`, `price`, `weight`, `dimensions`, `category`            |
| **ProductCatalog**       | `catalogId` {key}, `name`, `effectiveFrom`, `effectiveTo` (could be logical grouping of Products)       |
| **InventoryItem**        | `inventoryId` {key}, `productId` (FK), `warehouseId` (FK), `quantityOnHand`, `reorderPoint`, `status`   |
| **Warehouse**            | `warehouseId` {key}, `name`, `location`                                                                 |
| **InventoryBin**         | `binId` {key}, `warehouseId` (FK), `binLocation`, `capacity`                                            |
| **Supplier**             | `supplierId` {key}, `name`, `contactInfo`, `leadTime`                                                   |
| **ReplenishmentRequest** | `requestId` {key}, `productId` (FK), `quantity`, `requestDate`, `status`, `supplierId` (FK)             |
| **Payment**              | `paymentId` {key}, `orderId` (FK), `amount`, `method`, `authorizationCode`, `status`, `paymentDate`     |
| **Invoice**              | `invoiceId` {key}, `orderId` (FK), `invoiceDate`, `total`, `tax`, `shippingCharges`                     |
| **Shipment**             | `shipmentId` {key}, `orderId` (FK), `courierId` (FK), `trackingNumber`, `shipDate`, `estimatedDelivery` |
| **Courier**              | `courierId` {key}, `name`, `apiEndpoint`, `contactInfo`                                                 |
| **ReturnRequest**        | `returnId` {key}, `orderId` (FK), `reason`, `requestDate`, `status`                                     |
| **Report**               | `reportId` {key}, `type`, `generatedDate`, `parameters`                                                 |

### 4 — Step 5: Relationships, type, and multiplicity (table)

| **From**         | **To**                                                                     | **Relationship type**                     | **Multiplicity (From → To)**                    | **Notes / rationale**                                                                                    |
| ---------------- | -------------------------------------------------------------------------- | ----------------------------------------- | ----------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| Customer         | Order                                                                      | association                               | Customer `1` .. `*` → Order `0..*`              | One customer places many orders; an Order must have 1 Customer                                           |
| Order            | OrderItem                                                                  | composition                               | Order `1` → OrderItem `1..*`                    | Order composed of OrderItems (cannot exist independently)                                                |
| OrderItem        | Product                                                                    | association (association class semantics) | OrderItem `1` → Product `1`                     | OrderItem links to a single Product; Product can appear in many OrderItems                               |
| Product          | InventoryItem                                                              | aggregation                               | Product `1` → InventoryItem `0..*`              | InventoryItems are instances/stock entries for a Product; parts of inventory (can exist separately)      |
| InventoryItem    | Warehouse                                                                  | composition                               | Warehouse `1` → InventoryItem `0..*`            | Inventory items belong to a Warehouse (composition if an inventory record is meaningful only in context) |
| Product          | Supplier                                                                   | association                               | Supplier `1..*` → Product `0..*`                | Supplier supplies many products; a product can have multiple potential suppliers                         |
| InventoryItem    | ReplenishmentRequest                                                       | association                               | InventoryItem `1` → ReplenishmentRequest `0..*` | When stock below reorderPoint create requests                                                            |
| Order            | Payment                                                                    | association                               | Order `1` → Payment `0..*`                      | An order can have multiple payment attempts/records; usually one successful payment                      |
| Order            | Invoice                                                                    | association                               | Order `1` → Invoice `1..*`                      | Invoice(s) generated per order                                                                           |
| Order            | Shipment                                                                   | association                               | Order `1` → Shipment `0..*`                     | An order may be split into multiple shipments                                                            |
| Shipment         | Courier                                                                    | association                               | Shipment `1` → Courier `1`                      | Courier assigned for shipment                                                                            |
| Staff (abstract) | SalesStaff / InventoryStaff / FinanceStaff / LogisticsStaff / SupportAgent | generalization                            | Staff ← subclasses                              | Staff is superclass; role-specific subclasses inherit                                                    |
| Report           | Manager                                                                    | association (temporal)                    | Report `1` → Manager `0..*`                     | Managers request/receive reports; generation is a temporal event                                         |

### 5 — Step 6: Present domain model class diagram.

![[domain model class diagram.png]]
