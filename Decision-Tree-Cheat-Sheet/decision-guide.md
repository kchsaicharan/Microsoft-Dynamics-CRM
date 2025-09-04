Decision Guide for Dynamics 365 / Power Platform Customizations
🎯 Purpose
This guide helps decide the best approach (OOB, automation, customization, or code) when implementing business requirements. Always follow the OOB → Low-code → Code priority order.
________________________________________
🪜 Priority Ladder (When to Choose What)
1.	Out-of-the-box (OOB) features – maintainable, upgrade-safe, minimal code.
    o	Business Rules
    o	Business Process Flows (BPF)
    o	Formula / Calculated / Rollup fields
2.	Low-code automation
    o	Power Automate Flows (preferred)
    o	Classic Workflows (legacy, avoid if possible)
3.	Client-side customization
    o	JavaScript (real-time form logic beyond Business Rules)
4.	Server-side customization
    o	Plugins (complex business logic, enforce rules securely)
    o	Custom Workflow Activities (rare, when Power Automate not suitable)
5.	Custom UI/UX
    o	PCF Controls (for visualization, input enhancements)
________________________________________
📌 Feature Decision Table
Requirement_Type          	            Best_Option	                Avoid / Notes
Simple field calculations	              Formula column (preferred)	Avoid workflows for this
Aggregating child records	              Rollup fields (if simple)	  Use plugin if performance issues
Guiding users through a process	        Business Process Flow	      Don’t overcomplicate with Power Automate
Show/hide fields, simple validations	  Business Rules	            Use JS only if rules too complex
Complex form logic (real-time)	        Client-side JavaScript	    Ensure performance on forms
Cross-system automation / approvals	    Power Automate Flows	      Classic workflows are deprecated
Enforcing business rules securely	      Server-side Plugin	        Avoid client-side for critical rules
Custom UI elements (maps, sliders)	    PCF Controls	              Use only if OOB controls can’t handle
Sending emails / notifications	        Power Automate	            Avoid workflows
High-performance, synchronous logic	    Plugin	                    Ensure optimized code
________________________________________
🚦 Rules of Thumb
•	✅ Always start with OOB features – less maintenance.
•	✅ Power Automate > Workflows – modern, cloud-friendly, integrates well.
•	✅ Client-side JS for UI only – don’t enforce business rules here.
•	✅ Plugins for business-critical logic – secure & reliable.
•	✅ PCF only if absolutely needed – custom UI adds complexity.
________________________________________
🛠️ Example Scenarios
1.	Auto-calculate Age from DOB → Formula field.
2.	Total number of open cases per customer → Rollup field.
3.	Hide Address fields if "Country" ≠ Ireland → Business Rule.
4.	Send approval email when Opportunity > €10,000 → Power Automate Flow.
5.	Validate Tax Number format before save → JavaScript.
6.	Block record creation if duplicate exists → Plugin.
7.	Show progress bar for completion → PCF Control.
