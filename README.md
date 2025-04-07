<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Post-Install Configuration</h1>
This tutorial outlines the post-install configuration of the open-source help desk ticketing system osTicket.<br />


- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (22H2)

<h2>Post-Install Configuration Objectives</h2>

- Configure Roles (Allows us to group permissions)
- Configure Departments (Allows us to create ticket visibility to org departments)
- Configure Teams (Allows us to group agents from different departments into teams)
- Allowing anyone to create tickets
- Configure Agents (The help desk workers)
- Configure Users (End users/Customers)
- Configure SLA (Service Level Agreement, in this context how much time you have to do a specific task)
- Configure Help Topics (Categories to choose from when creating a ticket)

<h2>Configuration Steps</h2>

<p>
For this lab I will be navigating between Admin and Agent Panels. Just wanted to give an explanation here of what the differences are. The "Admin Panel" allows to configure settings for osTicket on the backend and the "Agent Panel" is for the help desk worker when they are working tickets. Ok lets proceed.
</p>
<br />

<p>
<b>1. Configure Roles </b> <br />
 - Login to the Help Desk login page with credentials created previously http://localhost/osTicket/scp/login.php. <br />
 - Select Admin Panel (Top right) -> Agents -> Roles -> Add new Role. <br />
 - Create a role called Supreme Admin and give all permissions to that role.
</p>
<p>
<img src="https://i.imgur.com/LWInHcs.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/gFgnjSw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/QAMcTSB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/1U3As2t.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
<b>2. Configure Departments </b> <br />
 We are going to create a new department called SysAdmins. To do this go to Admin Panel -> Agents -> Departments -> Add New Department. Make sure Parent = TopLevelDepartment. We can configure things like SLAs here but not neccessary for the purpose of this lab. We can also add agents to departments here but we can come back and configure this later. Click create department. Reload the departments page and you should be able to see the new department called "SysAdmins" has been created.
</p>
<p>
<img src="https://i.imgur.com/AHEnsOM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/Bd1yO0i.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/K7D6tpF.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
<b> 3. Configure Teams </b>  <br />
Teams allows us to create a group of people from different departments. We are going to create a team in our fake org called "Online Banking" which will consist of online baking team members and help desk agents. <br />
Start by going to Admin Panel -> Agents -> Teams -> Add New Team. Call the team "Online Banking" and click create. We could've added members here but we haven't created any. Reload the teams page and you should see the new team "Online Baking" has been created.
</p>
<p>
<img src="https://i.imgur.com/9GqodU8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/vEcNVXT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/CbZ8w0Z.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
<b>4. Allow anyone to create tickets </b> <br />
We are going to allow anyone to create tickets. So go to Admin Panel -> Settings -> Users. Uncheck: require registration and login to create tickets.
</p>
<p>
<img src="https://i.imgur.com/P6hr9Il.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
<b>5. Configure Agents </b> <br />
We are going to create a couple of help desk agents to do tickets with. One will be called Jane (Assigned to SysAdmins Department) and the other John (Assigned to the Support Department). Start by going to 

</p>
<p>
<img src="https://i.imgur.com/P6hr9Il.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
