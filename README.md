# osTicket Usage & Workflow 

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
    * While viewing the ticket as John, change the **SLA Plan** to Sev-A (critical level) by clicking the SLA status. Provide a reason such as `Massive impact as customers can't access online banking`
    * ![image](https://github.com/user-attachments/assets/6b0d17a7-bf12-4493-99ba-995f8b55c863)
    * Update the Help Topic if End User didn't choose the best one
    * ![image](https://github.com/user-attachments/assets/d1d5acd1-5959-4929-a188-b043be750c77)
    * Set the **Department** to handle the ticket(e.g Support).
    * Select approptiate Team or Agent to handle it (e.g Online Banking)
    * ![image](https://github.com/user-attachments/assets/8f1e8bf7-8726-4657-a4a8-6a79a1714eb0)
    * Note:: each update is posted in the Ticket Thread
    * ![image](https://github.com/user-attachments/assets/03d989aa-7957-459b-8835-91b06854ae2b)
    * Tranfer Department to SysAdmins as its high level ticket
    * ![image](https://github.com/user-attachments/assets/8c3459d6-64a4-401a-8400-9437fc49f52e)
    * Save Changes.
* **d. Visibility Check (Agent: John)**
    * After transferring the Department to 'SysAdmins', attempt to find or view the ticket again using John's account. Note that John should no longer be able to see or access this ticket (As he is not part of the Department or the Team).
* **e. Ticket Resolution (Agent: Jane - SysAdmins Dept)**
    * Now log in to the **Agent Panel** as Agent **Jane** (the SysAdmin we created) to work on the ticket to completion.
    * Locate the escalated ticket in the queues accessible to the 'SysAdmins' department.
    * ![image](https://github.com/user-attachments/assets/f2b38aa4-dc04-4da7-a450-0fd30111cc6c)
    * Simulate work by adding replies to the user to keep them updated.
    * Can write internal notes that are only visible to those who have access
    * ![image](https://github.com/user-attachments/assets/e745df8d-b463-49e7-9236-64947ddcad31)
    * ![image](https://github.com/user-attachments/assets/e14ecaa3-4887-4ffe-aa9c-8739b95af3fc)
    * Change the ticket status to **Resolved** or **Closed**.
    * ![image](https://github.com/user-attachments/assets/242deaa2-e577-422d-9b8c-09d8d5d1b73e)


### 2. Ticket Workflow: Scenario 2 - Software Issue (Adobe Upgrade)

* **a. Ticket Creation (End User)**
    * Access the **End User Portal** and create a **New Ticket**.
    * Select a relevant Help Topic 
    * Set the Subject to something like "Adobe not working"
    * ![image](https://github.com/user-attachments/assets/41ec1bd8-71ed-4755-9a76-3873c9515271)
    * Submit the ticket.
* **b. Triage & Categorization (Agent: John)**
    * Log in to the **Agent Panel** as **John** and locate the new ticket.
    * Observe the initial ticket properties and provided context
    * Can contact End User for more information to determine serverity
    * Determine that 2 people can't access and ask him to have them restart their computers as there was upadtes the day before
    * Set the **SLA Plan** to Sev-C and the **Department** to Support. Save Changes.
    * ![image](https://github.com/user-attachments/assets/c4598c02-cbf2-4a0e-ac8e-1e0a067e3818)
    * Assign it to yourself as you are in the Support team
    * ![image](https://github.com/user-attachments/assets/600349d6-7875-4673-89ed-9ebf3fabb515)
    * Post a reply
    * ![image](https://github.com/user-attachments/assets/8d4210a9-4e69-4c70-8e71-d009b7882d04)
    * Restart fixed it so provide a reply update
    * ![image](https://github.com/user-attachments/assets/2edb85c2-138f-4290-bee0-52e9bde939e9)
* **c. Resolution (Agent: John)**
    * Change the ticket status to **Resolved** or **Closed**.
    * ![image](https://github.com/user-attachments/assets/fd0fe31c-67bd-4a2b-90fc-6a6560696f7a)

### 3. Ticket Workflow: Scenario 3 - Hardware Issue (CFO Laptop)

* **a. Ticket Creation (End User)**
    * Access the **End User Portal** and create a **New Ticket**.
    * Select a relevant Help Topic (e.g Personal Computer Issues)
    * Set the Subject to: "CFO cant use laptop" and add context "CFO laptop can't power on. Power button not working. "
    * Submit the ticket.
    * ![image](https://github.com/user-attachments/assets/0222f2f2-9945-409b-8cdf-73fec9f065e5)

* **b. Triage & Categorization (Agent: John)**
    * Log in to the **Agent Panel** as **John** and locate the new ticket.
    * Observe the initial ticket properties.
    * Note that it is the CFO so can set `Priority` to Emergency
    * Set the **SLA Plan** to Sev-B (not Sev-A as their isn't enough info to determine)
    * ![image](https://github.com/user-attachments/assets/dc6f848d-f445-488d-b3cd-ea7b7beb22fe)
    * Assign to self and Support Department
* **c. Resolution (Agent: John)**
    * As John, simulate work on the ticket (e.g., noting contact with the CFO and dispatching a technician(or yourself) depends on the company).
    * Pretend you went to see the computer and that charger was found to be broken and you replaced it
    * Post a reply as a status update
    * ![image](https://github.com/user-attachments/assets/9b954521-5be2-4904-9a11-516ccc335e15)
    * Change the ticket status to **Resolved** or **Closed**.


### 4. Final Ticket Resolution

* Ensure all test tickets created during the project are set to a final state (Resolved or Closed) by logging in as the appropriate agent (Jane for SysAdmins, John for Support, or an Admin).
* ![image](https://github.com/user-attachments/assets/fbc754b3-10fd-4ebf-a894-854eba86400c)

### Takeaways


* Understood the complete ticket lifecycle, from end-user creation to agent resolution, highlighting the importance of each stage in efficient ticket management.
* Explored different agent roles and permissions, demonstrating how department assignments and extended access settings control agent capabilities.
* Learned the crucial role of proper ticket categorization (Help Topics, Departments) and SLA assignment for prioritizing and routing tickets effectively.
* Observed real-world IT support practices, emphasizing clear communication with end-users and the necessity of creating tickets for all support interactions.
* Gained practical experience with osTicket's core features, including ticket creation, property modification, internal notes, and status updates.
* Discovered the importance of internal notes for agent communication without end-user visibility.
* Demonstrated how to escalate tickets to different departments and the impact on agent visibility.
* Simulated user behavior, recognizing that users may not always select the most appropriate help topics.
* Contributed to the development of essential technical skills for IT professionals in help desk and ticketing systems.
* Recognized the importance of metrics and documenting all work.
* Identified the importance of proper department setup.
