# osTicket Usage & Workflow Lab

## Overview

This repository details a lab designed to simulate common help desk ticket lifecycles using osTicket. It explores agent and user roles, permissions based on departments, and connects these actions to real-world IT support practices.

## Objective

To gain practical experience with osTicket workflows, understand ticket management procedures, and learn how to handle various support scenarios.

## Prerequisites

* A working osTicket instance (as installed previously).
* Configured Agents (Jane - SysAdmins, John - Support).
* Configured Users (Karen, Ken).
* Configured Departments (SysAdmins, Support).
* Configured SLAs (Sev-A, Sev-B, Sev-C).
* Configured Help Topics (Business Critical Outage, Personal Computer Issues, etc.)

## Access URLs

* **Admin/Agent Login:** `http://localhost/osTicket/scp`
* **End User Portal:** `http://localhost/osTicket`

## Steps for creating Tickets and Handling them

First access the **End User Portal** at the URL above
![image](https://github.com/user-attachments/assets/7f628488-a083-41e7-b9c1-0adf9e0475fd)

### 1. Ticket Workflow: Scenario 1 - Critical Outage (Mobile Banking)

* **a. Ticket Creation (End User)**
    * Create a ticket as a Guest (set registration as not required in previous project).
    * Click **Open a New Ticket**.
    * Select the most relevant Help Topic (e.g., "Business Critical Outage" if configured).
    * Set the Issue Summary/Subject to relevant details simulating what a End User would likely say
    * ![image](https://github.com/user-attachments/assets/d0e1fe5d-f561-4d04-a7dc-0d92260bc350)
    * Note: A lot of time End Users choose the incorrect topics so if you want you can choose "Report a Problem" to simulate that as shown above
* **b. Initial Triage (Agent: John - Support Dept)**
    * Log in to the **Agent Panel** as Agent **John** (Support Agent created before).
    * Locate the newly created ticket in the 'Open Tickets' queue nuder the Tickets tab
    * ![image](https://github.com/user-attachments/assets/69e8666f-71c1-4fef-85b7-013b5f941c9f)
    * Observe the initial ticket properties: Priority, Department, SLA, and Assigned To status.
    * ![image](https://github.com/user-attachments/assets/47ca2dc1-29d9-42b4-8a0c-19b29128ccce)
    * Notice that everything is mostly set to default and can be changed by the Agent(if permissions granted)
    * The Agent can guage the seriousness of the situation and set the appropriate SLA and Assign to appropriate Team
    * If it seems a critical issue its best to contact the End User directly for more information
* **c. Ticket Categorization & Escalation (Agent: John)**
    * While viewing the ticket as John, change the **SLA Plan** to Sev-A.
    * Change the **Department** to SysAdmins.
    * Add an internal note or reply (e.g., "Escalating to SysAdmins due to critical outage report.").
    * Save Changes.
* **d. Visibility Check (Agent: John)**
    * After reassigning the ticket to 'SysAdmins', attempt to find or view the ticket again using John's account. Note that John should no longer be able to see or access this ticket.
* **e. Ticket Resolution (Agent: Jane - SysAdmins Dept)**
    * Log in to the **Agent Panel** as Agent **Jane**.
    * Locate the escalated ticket in the queues accessible to the 'SysAdmins' department.
    * Simulate work by adding internal notes and replies to the user.
    * Change the ticket status to **Resolved** or **Closed**.

### 2. Ticket Workflow: Scenario 2 - Software Issue (Adobe Upgrade)

* **a. Ticket Creation (End User)**
    * Access the **End User Portal** and create a **New Ticket**.
    * Select a relevant Help Topic (e.g., "Software Request" or "Personal Computer Issues").
    * Set the Subject to: "Accounting department needs Adobe upgrade, broken."
    * Submit the ticket.
* **b. Triage & Categorization (Agent: John)**
    * Log in to the **Agent Panel** as **John** and locate the new ticket.
    * Observe the initial ticket properties.
    * Set the **SLA Plan** to Sev-B and the **Department** to Support. Save Changes.
* **c. Resolution (Agent: John)**
    * As John, simulate work on the ticket (e.g., adding notes about checking licenses and scheduling a remote session).
    * Change the ticket status to **Resolved** or **Closed**.

### 4. Ticket Workflow: Scenario 3 - Hardware Issue (CFO Laptop)

* **a. Ticket Creation (End User)**
    * Access the **End User Portal** and create a **New Ticket**.
    * Select a relevant Help Topic (e.g., "Equipment Request" or "Personal Computer Issues").
    * Set the Subject to: "CFO’s laptop will no longer turn on."
    * Submit the ticket.
* **b. Triage & Categorization (Agent: John)**
    * Log in to the **Agent Panel** as **John** and locate the new ticket.
    * Observe the initial ticket properties.
    * Set the **SLA Plan** to Sev-B and the **Department** to Support. Save Changes.
* **c. Resolution (Agent: John)**
    * As John, simulate work on the ticket (e.g., noting contact with the CFO and dispatching a technician).
    * Change the ticket status to **Resolved** or **Closed**.

### 5. Exploring Permissions & Department Visibility

* Log in to the **Agent Panel** as **John**.
* Open one of the tickets John previously resolved.
* Edit the ticket properties and change the **Department** to SysAdmins. Save Changes. Observe that the ticket is no longer visible to John.
* Log in to the **Admin Panel**.
* Navigate to `Admin Panel -> Agents -> Agents -> Select Agent 'John' -> Access`.
* In the "Extended Access" section, grant **View** access to the SysAdmins Department for John. Save Changes.
* Log back in to the **Agent Panel** as **John**.
* Locate the ticket that was moved to SysAdmins. Observe that John can now see the ticket but likely cannot modify it.

### 6. Final Ticket Resolution

* Ensure all test tickets created during the lab are set to a final state (Resolved or Closed) by logging in as the appropriate agent (Jane for SysAdmins, John for Support, or an Admin).

### 7. Real-World Considerations & Communication

* Most ticketing systems, including osTicket, have email integration. This allows for notifications to be sent to agents and users upon ticket updates, and users can often respond directly via email. Email can also be a method for new ticket creation.
* In real-world IT support, tickets are created through various channels: the user portal, phone calls (where agents create tickets), chat applications, email, web forms, and even in-person requests. It is crucial to create a ticket for every support interaction, regardless of how minor it seems. This practice enables workload tracking, helps identify recurring issues, builds a knowledge base, ensures accountability, tracks performance metrics (like SLA adherence), and ultimately demonstrates the value of the IT department.

### 8. Conclusion & Continued Practice

This lab provides a fundamental understanding of osTicket workflows. To further your knowledge:

* Explore and configure the email integration features of osTicket.
* Repeat this lab multiple times, aiming to perform the steps using a basic checklist to build intuition and practical skills.
* Understand that hands-on practice with tools like osTicket directly contributes to your technical skills, a core competency for various IT roles. Re-doing this lab will solidify your technical ability.
