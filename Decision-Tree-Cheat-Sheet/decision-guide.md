# Decision Guide for Dynamics 365 / Power Platform Customizations
🎯 Purpose
This guide helps decide the best approach (OOB, automation, customization, or code) when implementing business requirements. Always follow the OOB → Low-code → Code priority order.
________________________________________
# 🪜 Priority Ladder (When to Choose What)
## 1.	Out-of-the-box (OOB) features – maintainable, upgrade-safe, minimal code.
    o	Business Rules
    o	Business Process Flows (BPF)
    o	Formula / Calculated / Rollup fields
## 2.	Low-code automation
    o	Power Automate Flows (preferred)
    o	Classic Workflows (legacy, avoid if possible)
## 3.	Client-side customization
    o	JavaScript (real-time form logic beyond Business Rules)
## 4.	Server-side customization
    o	Plugins (complex business logic, enforce rules securely)
    o	Custom Workflow Activities (rare, when Power Automate not suitable)
## 5.	Custom UI/UX
    o	PCF Controls (for visualization, input enhancements)
________________________________________
## 🚦 Rules of Thumb
•	✅ Always start with OOB features – less maintenance.
•	✅ Power Automate > Workflows – modern, cloud-friendly, integrates well.
•	✅ Client-side JS for UI only – don’t enforce business rules here.
•	✅ Plugins for business-critical logic – secure & reliable.
•	✅ PCF only if absolutely needed – custom UI adds complexity.
________________________________________
## 🛠️ Example Scenarios
1.	Auto-calculate Age from DOB → Formula field.
2.	Total number of open cases per customer → Rollup field.
3.	Hide Address fields if "Country" ≠ Ireland → Business Rule.
4.	Send approval email when Opportunity > €10,000 → Power Automate Flow.
5.	Validate Tax Number format before save → JavaScript.
6.	Block record creation if duplicate exists → Plugin.
7.	Show progress bar for completion → PCF Control.

________________________________________
________________________________________
________________________________________
# Limitation of Client-side Customizations
## Why Client-side Customizations Don’t Work on Imports

### Client-side customizations (JavaScript, Business Rules) only run when a record is interacted with in the form (UI).

    Example: You open a form, type in a value, and your JavaScript validation triggers on onChange or onSave.

### Imports, integrations, or API-based record creation bypass the UI.

    Example: Data Import Wizard, Excel Import, Power Automate creating records, or an external API integration → these don’t trigger client-side events.

So:

## ✅ Client-side works only when user interacts with form in UI.

## ❌ Client-side doesn’t work on imports / integrations / background processes.


