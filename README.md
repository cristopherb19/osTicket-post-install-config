<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Post-Install Configuration</h1>
This tutorial outlines the post-install configuration of the open-source help desk ticketing system osTicket.
<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>Objectives</h2>

- If you haven't installed and setup osTicket yet on your machine, please follow the guide <a href="https://github.com/cristopherb19/osTicket-prereqs">here</a> and come back
- Configure Roles
- Configure Departments
- Configure Teams
- Configure Agents
- Configure Users
- Configure SLA
- Configure Help Topics

<h2>Configuration Steps</h2>
<h3>&#9312; Configure Roles (used for grouping permissions)</h3>

<p>

- Acknowledge Agent Panel vs Admin Panel:
The Agent Panel is used by agents to work on tickets.
The Admin Panel is used to manage system settings, configurations, and permissions.
- In the osTicket installation page, click on "Your Staff Control Panel" link(http://localhost/osTicket/scp), login with admin credentials, then navigate to "Admin Panel" -> Agents -> Roles 
- Click "Add New Role"
<img src="https://imgur.com/UtAGptB.png" height="80%" width="80%" alt="New Role window"/>

- Add a new role called Supreme Admin.
- Define permissions for agents based on the role they will have. In this lab, we will give permissions for the Tickets, Tasks, and Knowledgebase sections.
<img src="https://imgur.com/dd551Xf.png" height="80%" width="80%" alt="Role list"/>
<img src="https://imgur.com/x0RA2c0.png" height="80%" width="80%" alt="Role list"/>
<img src="https://imgur.com/9qLGmPu.png" height="80%" width="80%" alt="Role list"/>
<img src="https://imgur.com/t7TtXQS.png" height="80%" width="80%" alt="Role list"/>
<img src="https://imgur.com/LdsuIzV.png" height="80%" width="80%" alt="Role list"/>


</p>
<br />
<h3>&#9313; Configure Departments (used for ticket visibility)</h3>

<p>

- Within osTicket, navigate to "Admin Panel" -> Agents -> Departments
- Use departments to control ticket visibility and assign areas of responsibility (e.g., Help Desk, SysAdmins, Networking)
- Delete the "Maintenance" department to prevent tickets from automatically being sent there
- Click "Add New Department" then fill out the following fields:
  - Parent: Top Level Department
  - Name: SysAdmins
<img src="https://imgur.com/JxHn5NJ.png" height="80%" width="80%" alt="New department page"/>
<img src="https://i.imgur.com/aP0Rvsl.png" height="80%" width="80%" alt="New department page"/> 
- Click "Create Dept"
<img src="https://imgur.com/LGuc9KI.png" height="80%" width="80%" alt="New department page"/>  
</p>
<br />
<h3>&#9314; Configure Teams  </h3>

<p>

- Within osTicket, navigate to "Admin Panel" -> Agents -> Teams
- Click "Add New Team"
- Name the team "Online Banking" and click "Create Team"
- Pull agents from different departments to form specialized teams
<img src="https://imgur.com/7W3jOmZ.png" height="80%" width="80%" alt="New team page"/>
  
</p>
<br />
<h3>&#9315; Allow anyone to create a ticket</h3>

<p>

- Within osTicket, navigate to "Admin Panel" -> Settings -> Users
- Disable "Registration Required" box (should be unchecked) to allow ticket creation from anyone
- Enable "Public Anyone can register" option to disable requiring users to register and log in before creating tickets
- Click "Save Changes"
<img src="https://imgur.com/dxNQAaN.png" height="80%" width="80%" alt="User Settings"/>
</p>
<br />
<h3>&#9316; Configure Agents (employees / workers)</h3>

<p>

- Within osTicket, navigate to "Admin Panel" -> Agents -> Add New Agent
- Add agents with the following details:
Jane: Assigned to the SysAdmins department.
John: Assigned to the Support department.
<img src="https://imgur.com/4lOmcol.png" height="80%" width="80%" alt="Agent creation"/>
- You can choose to set their password or send the agent a password reset email.
<img src="https://imgur.com/mJDuwwh.png" height="80%" width="80%" alt="Agent creation"/>

- Within "Access" tab, assign department and role
<img src="https://imgur.com/oBMKbsg.png" height="80%" width="80%" alt="Agent dept and roleassignment"/>

- Within "Teams" tab, assign team, then click "Create" to finish
<img src="https://imgur.com/5YNyf0e.png" height="80%" width="80%" alt="Agent team assignment"/>
<img src="https://imgur.com/du64ZLx.png" height="80%" width="80%" alt="Agent team assignment"/>
<img src="https://imgur.com/2GJO8eT.png" height="80%" width="80%" alt="Agent team assignment"/>
<img src="https://imgur.com/KToVVBa.png" height="80%" width="80%" alt="Agent team assignment"/>
<img src="https://imgur.com/QsvaTXR.png" height="80%" width="80%" alt="Agent team assignment"/>

- In my case, I created 2 agents with the following assignments:
  - Agent 1:
    - Name: Jane Doe
    - Email Address: Jane@lognpacific.com
    - Username: jane
    - Password: Password1
    - Department: SysAdmins
    - Role: Supreme Admin
    - Team: Online Banking
  - Agent 2:
    - Name: John Doe
    - Email Address: john@lognpacific.com
    - Username: john
    - Password: Password1
    - Department: Support
    - Role: Expanded Access
    - Team: Online Banking
  
</p>
<br />
<h3>&#9317; Configure Users (customers)</h3>

<p>

- Within "Agent Panel", navigate to Users -> Add User
- Fill out necessary fields and click "Add User" to finish
<img src="https://imgur.com/hICMzMh.png" height="80%" width="80%" alt="Add user page"/>
  
</p>
<br />
<h3>&#9318; Configure SLA</h3>

<p>

- Within "Admin Panel", navigate to "Manage" -> SLA -> Add New SLA Plan
- Fill out necessary fields and click "Add Plan" to complete
- We are going to create 3 SLA's:
  - 1:
    - Name: Sev-A
    - Grace Period: 1 (hr)
    - Schedule: 24/7
  - 2:
    - Name: Sev-B
    - Grace Period: 4 (hrs)
    - Schedule: 24/7
  - 3:
    - Name: Sev-C
    - Grace Period: 8 (hrs)
    - Schedule: Monday-Friday, 8am - 5pm
   
  - All SLA pages will look something like the picture below:
  <img src="https://imgur.com/drDlWn8.png" height="80%" width="80%" alt="SLA Page"/>
  <img src="https://imgur.com/pwrfk76.png" height="80%" width="80%" alt="SLA Page"/>
  <img src="https://imgur.com/HUdQWDR.png" height="80%" width="80%" alt="SLA Page"/>
  <img src="https://imgur.com/aq5CeVT.png" height="80%" width="80%" alt="SLA Page"/>
  
</p>
<br />
<h3>&#9319; Configure Help Topics</h3>

<p>

- Within "Admin Panel", navigate to Manage -> Help Topics -> Add New Help Topic
<img src="https://imgur.com/p3zPM32.png" height="80%" width="80%" alt="Help Topic Page"/>

- We are going to create the following Help Topics:
  - Help Topic 1:
    - Topic: Business Critical Outage
    - Parent Topic: Report a Problem
  - Help Topic 2:
    - Topic: Personal Computer Issues
    - Parent Topic: Report a Problem
  - Help Topic 3:
    - Topic: Equipment Request
    - Parent Topic: General Inquiry
  - Help Topic 4:
    - Topic: Password Reset
    - Parent Topic: Report a Problem
  - Help Topic 5:
    - Topic: Other
    - Parent Topic: General Inquiry
<img src="https://imgur.com/hoKttSq.png" height="80%" width="80%" alt="SLA Page"/>
<img src="https://imgur.com/hyxXr2M.png" height="80%" width="80%" alt="SLA Page"/>
<img src="https://imgur.com/KytPD4j.png" height="80%" width="80%" alt="SLA Page"/>
<img src="https://imgur.com/FWMzr7E.png" height="80%" width="80%" alt="SLA Page"/>
<img src="https://imgur.com/CveU9Lk.png" height="80%" width="80%" alt="SLA Page"/>
  
</p>
<br />

<h2 align=center>Congratulations!! You are now ready to explore the ticket lifecycle!</h2>
By completing the post-installation configuration steps, you have successfully customized osTicket to suit your organization's requirements. You are now ready to start using osTicket to manage and resolve customer issues efficiently. Once you're finished with post-install configuration, please continue <a href="https://github.com/cristopherb19/osTicket-ticket-lifecycle">here</a> to see how tickets are made and resolved within osTicket.

  
</p>
