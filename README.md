# Creating-Virtual-Machines-Virtual-Networks-and-Domain-Controllers


## Objective
Using Microsoft Azure we are going to create a Virtual Machine(s) (VM's), Virtual Network (VNet), and a Domain Controller (DC).



---

## Environments and Technologies Used
- Microsoft Azure



Note
- This example will use a previously created Microsoft Azure account, subscription, and resource group.

---

## Operating System
- This breakdown is created using Windows platform.

---

## Creating Our Virtual Network

<p>
For sake of ease, we will create our Virtual Network first. However it should be noted that VM's can have their network changed after the VM is already created
</p>
<br />

<p>
<img width="1678" height="870" alt="image" src="https://github.com/user-attachments/assets/20d1ab9e-b272-4de6-8910-c23a23ab4811" />
</p>
<p>
Navigate to your "Virtual Networks" from the Microsoft Azure Portal. This can be done either by the search bar at the top, or the drop down menu on the left. Click "Create".
</p>
<br />

<p>
<img width="1065" height="626" alt="image" src="https://github.com/user-attachments/assets/22876f7f-7ecf-41bd-864f-c449a176ade3" />
</p>
<p>
To create your Virtual Network simply add to your existing resource group, name the network, and select your region. Click "Review + Create" followed by "Create".
</p>
<br />

## Creating our Virtual Machine(s)

<p>
<img width="1507" height="797" alt="image" src="https://github.com/user-attachments/assets/00189fa6-eb85-4dfc-9e03-af186a3b3f15" />

</p>
<p>
To begin, we will access the Microsoft Azure page, and navigate to virtual machines. This can be done either by the search bar at the top, or the drop down menu. Once there, click "Create", then select "Virtual Machine".
</p>
<br />

<p>
<img width="1061" height="820" alt="image" src="https://github.com/user-attachments/assets/f70bb4d1-6fcd-42c4-a740-dcefe1d8f379" />
<img width="1113" height="693" alt="image" src="https://github.com/user-attachments/assets/91195679-053e-4cfd-b3b1-5052cb4938d7" />
<img width="630" height="114" alt="image" src="https://github.com/user-attachments/assets/f608d5a8-3206-41f0-bc06-83d4a4d4b73c" />
</p>
<p>
Now you will select your resource group, and name your virtual machine. Pay close attention to what operating system you are putting on the machine as well as  the "size" of the machine. Create Username, and password, and be sure to select the licensing box at the bottom. From here we click "next" until we reach the Networking page.
</p>
<br />

<p>
<img width="1232" height="717" alt="image" src="https://github.com/user-attachments/assets/749edb4f-1e6e-4042-b3d0-d4c1ae86b01b" />

</p>
<p>
Ensure your virtual machine is on the virtual network you created earlier. Click "Review + Create" followed by "Create". 
</p>
<br />



<p>
<img width="656" height="380" alt="image" src="https://github.com/user-attachments/assets/563503e6-0962-478b-a6ff-897532d7614d" />
</p>
<p>
Repeat this series of steps at least one more time, or until you have achieved the number of virtual machines desired.
</p>
<br />

# Creating Domain Controller

<p>
<img width="1087" height="707" alt="image" src="https://github.com/user-attachments/assets/86b87fdd-918f-4aa3-b6ab-54c1066621cd" />
</p>
<p>
This portion is largely the same as "Creating Our Virtual Machine(s)" There is one very important note here: when we go to select "Image" you must make sure to select a datacenter or equivelant to i.e. Windows Server 2022 Datacenter: Azure Edition Hotpatch - x64 Gen2
</p>
<br />

---
## This completes the creation of Virtual Machine(s), Virtual Network, and Domain Controller

<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Active Directory, Account Management, Security Policy Enforcement</h1>
This project demonstrates hands on implementation of user account management and security policy enforcement within an Active Directory environment using Windows Server.
Core administrative tasks included configuring account lockout policies through Group Policy, managing user account states, and resolving authentication related incidents such as account lockouts and credential resets.


## Environments and Technologies Used

- Microsoft Azure
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10

<h2>Objectives</h2>

- Set lockout policies
- Simulate account lockout
- Simulate account lockout resolution

<h2>Deployment and Configuration Steps</h2>

## Install Active Directory on Domain Controller

<p>
<img width="1496" height="799" alt="image" src="https://github.com/user-attachments/assets/40944d50-b09b-4a97-92fe-a89c0a799a8d" />
</p>
<p>
Assuming our VM does not have Active Directory installed, we will install via the server manager. Once installed promote this VM to Domain Controller through server manager. I will also create a server admin account to act as.
</p>
<br />

## Adding a "Client" VM to the domain

<p>
<img width="1080" height="353" alt="image" src="https://github.com/user-attachments/assets/8d6adf25-103e-45c0-a705-4e7b505617d4" />

</p>
<p>
In a previous session, we already joined "Client" VM to the domain. This was done by setting the VM's DNS settings to our Domain Controllers private I.P. address, and joining the domain through system settings.
</p>
<br />

<p>
<img width="874" height="590" alt="image" src="https://github.com/user-attachments/assets/9c9e9a76-b920-41f4-8794-67028853e1e4" />
</p>
<p>
You can verify that "Client" VM joined the DC through "Active Directory Users and Computers". 
</p>
<br />

## Group Policy

<p>
<img width="1892" height="932" alt="image" src="https://github.com/user-attachments/assets/b1285f34-31b0-4685-af8e-e53aa3efa1f8" />
<img width="1703" height="902" alt="image" src="https://github.com/user-attachments/assets/17010aea-335f-4530-9459-ed26e7aa2c02" />
<img width="513" height="147" alt="image" src="https://github.com/user-attachments/assets/4b094cb3-847f-4bc2-949b-d6e747d3e0f6" />



</p>
<p>
Group Policies can be used to control users and computers behavior across the domain. This ranges from security settings, computer configuration, user configuration, adminstrative templates, and much more. In this example we are only editing an existing policty to control number of attempted log ins before the account is locked out.
</p>
<br />

## Unlocking a locked out account

<p>
<img width="782" height="569" alt="image" src="https://github.com/user-attachments/assets/63acce77-5b3e-451a-a7ed-e51f14be3f3f" />

</p>
<p>
To unlock an account, simply go to active directory users and computers. Find and select the user that has requested assistance with a lockout. Under the properties of this users, you will go to account. Here you will see the notification stating that the user is in fact locked out. You must only check the box that says "Unlock Account". Depending on company policy you may want to force a password change, or any other condition.
</p>
<br />

## Managing a users account

</p>
<p>
Through Active Directory Users and Computers you can also disable, or re-enable a users account. I perform this action with a simple right click on the user under the database they can be found in.
</p>
<br />


## Throug Active Directory , and Group Policy Management Console as an admin, you have control of the domain, policies, and the users on it. This example is only a very brief demonstration of what can be managed from this station.
<br />

## Working a ticketing system (osTicket)

<p>
<img width="596" height="90" alt="image" src="https://github.com/user-attachments/assets/4beda061-ebc6-46ab-bc5e-9dae62ff52eb" />

<img width="1038" height="461" alt="image" src="https://github.com/user-attachments/assets/ec8b73b4-b2eb-4f5f-9cd5-d6103c15531a" />

</p>
<p>
For this first example I will be working a ticket in which a client or employee needs a password reset. First we will click ticket 833805 to open the ticket.
</p>
<br />

<p>
  <img width="1004" height="943" alt="image" src="https://github.com/user-attachments/assets/f186415e-830b-4574-b0b7-99acaa3f05d8" />

</p>

</p>
<p>
For this ticket we are going to say that the Status, Priority, Dept, and SLA are all already correct. We need to verify user information and ensure we are not providing a password reset to someone who is not the actual user. This can be done via phone, teams, email, as well as other forms of communication. You will verify based on given authentication factors whether that be, Employee ID, Reset Questions, or whatever is previously determined by the company.
</p>
<br />


<p>
<img width="383" height="259" alt="image" src="https://github.com/user-attachments/assets/9cf37a73-5e45-4d79-a29e-0597be36a772" />

</p>
<p>
Once user identity has been verified. Open Active Directories Users and Computers. Expand to the Users folder, find the user, right click the user and select "Reset Password". Enter a new temporary password to allow the user to log back in. Require that the password be reset on next login if required by policy. If necessary, select "Unlock the User's Account".
</p>
<br />


<p>
<img width="969" height="686" alt="image" src="https://github.com/user-attachments/assets/1cfd58cf-3467-46dc-83ff-4ae7a1d941db" />
<img width="1147" height="799" alt="image" src="https://github.com/user-attachments/assets/8cfe7a0b-06e2-4599-85de-08277cc52661" />
<img width="1006" height="886" alt="image" src="https://github.com/user-attachments/assets/0a705756-de72-4028-973f-fa927032b764" />



</p>
<p>
It is important to keep note in the system of what steps have been taken to correct the issue. This is useful in case you are unable to finish the ticket and someone else needs to take over. It is also good practice for accountability, and tracing. 
</p>
<br />


<p>
<img width="1028" height="807" alt="image" src="https://github.com/user-attachments/assets/ff036688-21e2-4f7d-af16-698a3a27613e" />

</p>
<p>
Once you have confirmed that the issue has been resolved, you can mark the ticket as resolved, closed, or send off to review depending on company policy.
</p>
<br />


## Correcting Ticket Status

# In this example, an employee/client has submitted a ticket, however the ticket has been submitted incorrectly. This is going to be corrected quickly.


<p>
<img width="964" height="118" alt="image" src="https://github.com/user-attachments/assets/4843f885-b25b-4029-9b12-b69bedee1246" />
<img width="989" height="862" alt="image" src="https://github.com/user-attachments/assets/badf4d62-b0a7-4258-b945-ac61616bc304" />
<img width="1019" height="891" alt="image" src="https://github.com/user-attachments/assets/c2716df7-6938-42d2-955c-241aceab3d65" />




</p>
<p>
As shown above, when karen got to work this morning, her entire department was unable to login to their online systems. Highlighted you can see that Karen submitted this under "General Inquiry" topic. Doing so has lowered the severity and therefor could impact the SLA. This is a severe problem that needs fixed right away.
</p>
<br />


<p><img width="961" height="480" alt="image" src="https://github.com/user-attachments/assets/bc452f74-bce3-458f-8c15-ed40c25d507b" />
<img width="1008" height="569" alt="image" src="https://github.com/user-attachments/assets/c3731abb-557c-453a-8d14-32cc1f82c701" />
<img width="1033" height="649" alt="image" src="https://github.com/user-attachments/assets/b772d73b-3e40-4ab0-9945-0855deea814c" />
<img width="974" height="725" alt="image" src="https://github.com/user-attachments/assets/06b88121-e3b3-483b-a42a-bd8cce65c600" />
<img width="955" height="743" alt="image" src="https://github.com/user-attachments/assets/bdaeedea-e3b3-4ccd-afd2-5155195fb8f4" />
<img width="1003" height="411" alt="image" src="https://github.com/user-attachments/assets/d1162270-f1ef-41f6-90d3-e9857642087f" />
<img width="1104" height="824" alt="image" src="https://github.com/user-attachments/assets/a0997855-92cc-4d4a-8d93-283c7185edf5" />



</p>
<p>
To resolve this problem as quickly as we can we are going to correct the ticket information to reflect the truth of the matter. By clicking on the titles for things such as "Priority" "Department" etc you can update the information. In the given example i am going to update the "Priority" level to High, we also want to correct the SLA Plan to reflect the severity of the issue. In this example we are using Sev-A (highest level severity in the shown system). You also have the option if needed to transfer this ticket to a specific department, or even an individual. It is important to note all the work done on this ticket so that when it moves forward or is resolved the history can be traced. In this example we are going to assume ourselves as an entry level help desk personell without the authorization to correct this problem. By updating the ticket information and forwarding to the correct party I am making sure I am doing my part to resolve this ticket as quickly as possible.
</p>
<br />



