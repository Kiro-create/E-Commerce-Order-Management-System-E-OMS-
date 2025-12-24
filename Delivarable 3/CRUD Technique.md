# **CRUD Technique Applied to Final Use Cases**


# **1. Final Validated Use Case List**

After applying the CRUD Technique and removing non-actor-goal use cases, the final set of valid use cases is:

1. **Place Online Order**
    
2. **Process Customer Payment**
    
3. **Manage Product Catalog**
    
4. **Plan Shipment**
    
5. **Track Order Status**
    
6. **Initiate Return Request**
    
7. **Look Up Order History**
    
8. **Generate Management Reports**
    
9. **Manage User Permissions**
    

---

# **2. Use Cases Removed or Merged**

## **Merged Use Cases**

The following use cases were **merged** because they do not represent independent goals of any actor. Instead, they are **internal system responsibilities** that logically fall under larger, actor-driven use cases.

| **Removed / Merged Use Case**    | **Merged Into**                                                                                       | **Reason for Merge                                                                                                                                                      |
| -------------------------------- | ----------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Handle Payment Authorization** | **Process Customer Payment**                                                                          | Authorization is part of the internal payment workflow (communicating with the payment gateway, confirming funds). No actor starts this step manually.                  |
| **Verify Order Details**         | **Place Online Order**                                                                                | The system automatically checks product availability, addresses, totals, and customer data during order placement. Customers do not trigger a separate "verify" action. |
| **Reserve Inventory**            | **Manage Product Catalog** _(inventory logic)_ + **Place Online Order / Process Payment** _(trigger)_ | Inventory reservation happens automatically when an order is placed/paid. It is not a user request and does not appear as a standalone goal.                            |
| **Send Replenishment Request**   | **Manage Product Catalog**                                                                            | Replenishment is automatic when stock is low. No staff explicitly triggers “send supplier request” as a separate use case.                                              |
| **Transmit Shipment Manifest**   | **Plan Shipment**                                                                                     | Sending the shipment manifest to the courier system is part of the shipment planning workflow. No actor initiates this step independently.                              |

---

## **Removed Use Cases (Invalid Actor-Goal Use Cases)**

The following were removed because they do **not** represent goals initiated by a human actor. They are **system-maintenance or internal process steps**, not true use cases:

- Verify Order Details
    
- Reserve Inventory
    
- Send Replenishment Request
    
- Transmit Shipment Manifest
    
- Handle Payment Authorization
    

All remaining use cases are valid actor-goal interactions.

---

# **3. CRUD Analysis by Data Entity**

The CRUD validation for each major domain entity.

---

## **3.1 Entity: Order**

|CRUD Operation|Related Use Cases|
|---|---|
|**Create**|Place Online Order|
|**Read**|Track Order Status, Look Up Order History, Generate Management Reports|
|**Update**|Place Online Order, Process Customer Payment, Plan Shipment|
|**Delete/Archive**|Initiate Return Request|

---

## **3.2 Entity: Payment**

|CRUD Operation|Related Use Cases|
|---|---|
|**Create**|Process Customer Payment|
|**Read**|Look Up Order History, Generate Management Reports|
|**Update**|Process Customer Payment (status update)|
|**Delete/Archive**|Initiate Return Request (refund resolution)|

---

## **3.3 Entity: Inventory Item**

|CRUD Operation|Related Use Cases|
|---|---|
|**Create**|Manage Product Catalog|
|**Read**|Place Online Order, Generate Management Reports|
|**Update**|Manage Product Catalog (edit), Place Online Order / Process Payment (stock reduction)|
|**Delete/Archive**|Manage Product Catalog|

---

## **3.4 Entity: Shipment**

|CRUD Operation|Related Use Cases|
|---|---|
|**Create**|Plan Shipment|
|**Read**|Track Order Status|
|**Update**|Plan Shipment (manifest, courier, routing updates)|
|**Delete/Archive**|Not Applicable|

---

## **3.5 Entity: User / Staff Permissions**

|CRUD Operation|Related Use Cases|
|---|---|
|**Create**|Manage User Permissions|
|**Read**|Manage User Permissions|
|**Update**|Manage User Permissions|
|**Delete/Archive**|Manage User Permissions|

---

## **3.6 Entity: Product Catalog**

|CRUD Operation|Related Use Cases|
|---|---|
|**Create**|Manage Product Catalog|
|**Read**|Place Online Order, Generate Management Reports|
|**Update**|Manage Product Catalog|
|**Delete/Archive**|Manage Product Catalog|

---