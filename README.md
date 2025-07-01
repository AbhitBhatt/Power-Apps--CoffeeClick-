# Power-Apps--CoffeeClick-

# ☕ Coffee Machine Procurement System

An end-to-end enterprise-grade solution built using **Microsoft Power Platform**, simulating a real-world coffee machine vending and procurement workflow. This project leverages **Canvas Apps, Model-Driven Apps, Dataverse**, and **Business Process Flows** to create a seamless user experience from machine selection to order processing.

---

## 🔧 Technologies Used
- **Power Apps (Canvas App)**
- **Power Apps (Model-Driven App)**
- **Dataverse**
- **Business Process Flow (BPF)**
- **Office365 Users Connector**

---

## 📱 Canvas App – Coffee Machine Simulator

- Built a user-friendly vending machine UI
- Vertical gallery for selecting **machine types**
- Horizontal gallery for browsing & **comparing machine models**
- Checkbox-based **compare feature** with `CompareList` collection
- Integrated **Edit Form** to create orders with prefilled fields:
  - Machine Name
  - Price
  - Approver (auto-fetched using Office365)
  - Requested By
  - Request Date (auto-filled)

---

## 🗃️ Dataverse – `MachineOrder` Table

Stores all machine order data with the following columns:
- `Machine Name`
- `Price`
- `Requested By`
- `Approval Status`
- `Request Date`
- `Approver`
- `Comments`
- `Estimated Ship Date` (Calculated with Business Rule)
- `Approved Date`
- `Department Contribution` (Formula: `Price * 0.1`)
- Additional process fields:
  - `Capital Approved` (Yes/No)
  - `Machine Received` (Yes/No)
  - `Machine Configured` (Yes/No)
  - `Send Survey` (Yes/No)
  - `Supplier Order ID`
  - `Machine Delivered` (Yes/No)

---

## 🧭 Model-Driven App – `MachineProcurement`

- Navigation pane includes a group titled `Orders` linked to the `MachineOrder` table
- Designed for internal business teams to review, update, and track machine orders

---

## 🔁 Business Process Flow – `Machine Procurement Process`

5 Stages defined:
1. **Machine Requested**  
   - Fields: Request Date, Approval Status, Price

2. **Place Order**  
   - Fields: Estimated Ship Date, Supplier Order ID (required)

3. **Receive Machine**  
   - Field: Machine Received

4. **Configure Machine**
   - Fields: Machine Configured, Send Survey

5. **Capital Approved** *(Conditional)*  
   - Only triggered if Price > ₹10,000  
   - Field: Capital Approved

---

## 🚀 Features & Highlights
- End-to-end low-code solution for a real-world procurement scenario
- Full integration with Dataverse for backend data management
- Uses Office365Users to fetch manager email for approval
- Business rule auto-sets ship date (`Approved Date + 14 days`)
- Separate **Success Screen** with `LastSubmit` reference to show confirmation
- Clean navigation back to the home screen

---

## 📸 Demo Screenshots

_(Include demo video or screenshots here for visual context)_

---

## 📂 Folder Structure

```plaintext
📁 PowerPlatform-CoffeeMachine
├─ 📄 README.md
├─ 📄 AppDesign (Canvas App JSON Export)
├─ 📄 ModelDrivenAppDesign (XML or app link)
├─ 📄 BusinessProcessFlowConfig
└─ 📄 DataFiles (Machines.xlsx, MachineType.xlsx)
