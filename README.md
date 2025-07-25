# 🚗 Car Showroom Management System (ServiceNow)

This project is a **ServiceNow-based Car Showroom Management System** developed using the **Service Portal**, **Flow Designer**, **Widgets**, and **Update Sets**. It allows users to view, book, and manage car inventories in a structured, role-based access system.

---

## 🌐 Project Modules

### 1. **Car Inventory Management**
- Custom Table: `Car Inventory`
- Fields:
  - Car Name
  - Brand
  - Variant
  - Year of Manufacture
  - Fuel Type
  - Available Stock
  - Price
  - Status (Available/Sold)
  - Description (Car details)

### 2. **Car Booking**
- Booking table stores user car booking data.
- Flow Designer automates stock update when a car is booked.

### 3. **Flow Designer Automation**
- Trigger: Booking record is inserted.
- Actions:
  - Look up the selected car using **Car sys_id**.
  - Decrease the stock count (`Available Stock`) by 1.
  - Update the status if stock reaches 0.

### 4. **Service Portal**
- Portal Name: `Liki's Car Showroom Portal`
- Users can:
  - View all available cars.
  - See car details like name, brand, price, status.
- Widgets used:
  - **Car Inventory Widget**: Displays available cars dynamically using GlideRecord.

### 5. **Widgets**
- Widget: `Car Inventory`
- Technologies:
  - Client Script (JavaScript)
  - Server Script (GlideRecord)
  - HTML (for dynamic car display)

### 6. **Update Set**
- All configurations packaged in an update set.
- Exported to XML for migration.

---

## 🛠 Technologies Used

- **ServiceNow Studio**
- **Flow Designer**
- **Service Portal Designer**
- **Widgets (HTML + JS + Server Script)**
- **Update Sets**
- Optional: Role-based Access Control (RBAC)

---

## 🖥️ Widget Code Snippets

### Server Script (Car Inventory Widget)
```javascript
(function() {
  var gr = new GlideRecord('x_your_scope_car_inventory');
  gr.addQuery('status', 'available');
  gr.query();

  data.cars = [];
  while (gr.next()) {
    data.cars.push({
      name: gr.getValue('car_name'),
      brand: gr.getValue('brand'),
      price: gr.getValue('price'),
      status: gr.getValue('status')
    });
  }
})();
