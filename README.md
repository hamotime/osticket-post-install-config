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
We are going to create a couple of help desk agents to do tickets with. One will be called Jane (Assigned to SysAdmins Department) and the other John (Assigned to the Support Department). We will create "Jane" first then follow the same steps to create John making sure he is assigned to "Support" department. <br />
- Start by going to Admin Panel -> Agents -> Add New. <br />
- Fill out "Name", "Email Address", "Username" <br />
- Uncheck "Send the agent a password reset email". Enter the password and make sure "Require Password change at next login it set to off". This isn't the best security practice and ideally you would want them to change their password at next login but as this is a practice lab it isn't neccessary <br />
- Select the "Access" tab. Under "Primary Department" select SysAdmins and then choose the "SysAdmin" role. Next is optional but under "Extended Access" I chose "Support" and then add to give Jane the ability to observer "Support" department tickets. <br />
- Select the "Teams" tab next. Choose "Online Banking" then click Add. Then select the yellow "Create" button <br />
- Refresh the Agents page and you will see a new agent has been created <br /> <br />
- Repeat the steps above to create another Agent but enter the following: <br />
- Name: John Doe <br />
- Email: john@lognpacific.com <br />
- Username: john <br />
- Under "Access" Tab "Primary Department" = Support and SupremeAdmin Role. We don't need to add John to a team. <br />
</p>
<p>
<img src="https://i.imgur.com/RO0JupF.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/Rlzwv1H.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/WtBMoUf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/mVFk2Yp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/AbWTwEo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/7qo8xPg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
<b>6. Configure Users </b> <br />
Next, we will create two customers who will be used to submit tickets to the help desk. One will be called "Karen" and the other will be called "Ken". To start, go to Agent Panel -> Users -> Click "Add New User" <br />
Name: Karen, Email Address: karen@lognpacific.com. Select "Add User". Refresh the "User directory" and you will see Karen has been added. Repeat the steps and create another user called "Ken" using the email address: "ken@lognpacific.com". You should now that two users created "Karen" and "Ken".
</p>
<p>
<img src="https://i.imgur.com/1b9QhZ0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/QtABwI5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/u3YwvP6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/LSVGpPl.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
<b>6. Configure SLAs (Service Level Agreements) </b> <br />
In the context of Helpdesks, this is going to mean how much time we have to do a specific task. We are going to create 3 SLAs: <br />
1. Sev-A (Severity A - Highest Priority) - Grace Period: 1hr (the number of hours after a ticket is created that it will be automatically marked as overdue), Schedule: 24/7 <br />
2. Sev-B (Severity B - Mid Priority) - Grace Period: 4hrs, Schedule: 24/7 <br />
3. Sev-C (Severity C - Lowest Priority) - Grace Period: 8hrs, Schedule: 24/7 <br />

Start by going to Admin Panel -> Manage -> SLA -> Add New SLA Plan <br />
Name: Sev-A <br />
Grace Period: 1hr <br />
Schedule: 24/7 <br />
Adding an internal note is optional. <br /> 
Select "Add Plan". Refresh the SLA page and you will notice the "Sev-A" SLA has been created. Repeat the steps and create two more plans called "Sev-B" and "Sev-C". Make sure to enter the correct information for them which is outlined above. Once you are done refresh the SLA page and you should see three SLAs created called "Sev-A", "Sev-B" and "Sev-C".
</p>
<p>
<img src="https://i.imgur.com/BtMCBJo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/sC4nzZH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/nBsvSHw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/dqyBdRN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
