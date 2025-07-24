# 🚗 Car Showroom Management System – ServiceNow

A low-code ServiceNow application to manage car inventory and customer bookings. Built using Studio with custom tables, UI Actions, reference fields, and business logic.

## 🔧 Features
- Car Inventory management
- Booking system with status updates
- "Confirm Booking" UI Action with server-side scripting
- Real-time status change in inventory

## 🧪 Tech Stack
- Platform: ServiceNow Developer Instance
- Tools: Studio, Table Designer, Scripting (GlideRecord), UI Actions

## 📸 Screenshots
See `/screenshots` folder

## 🗂️ Project Details
See `app_description.md` and `project_structure.txt`
## Car Showroom Management System – Description

This app manages cars available for sale and allows users to book them. Once a booking is confirmed, the car's status automatically changes to "Booked". Admin roles can create/view/edit records. Built using Agile principles.


##project_structure
Tables:
- Car Inventory (Fields: Car Name, Brand, Model, Price, Transmission, Status)
- Booking (Fields: Customer Name, Car, Booking Date, Status)

Modules:
- Car Inventory (List + Form)
- Bookings (List + Form)

UI Actions:
- Confirm Booking (Changes Booking status and updates Car status)

Relationships:
- Booking.car → reference to Car Inventory
ServiceNow apps are cloud-based and cannot be directly exported as working code.
This repo provides structure, screenshots, and proof of development.
