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

# Note: It is only necessary to connect to your VNET if you intend on using these VM's for Network excersises.

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
Good news! You largely know how to do this portion already simply by following "Creating Our Virtual Machine(s)" There is one very important note here: when we go to select "Image" you must make sure to select a datacenter or equivelant to i.e. Windows Server 2022 Datacenter: Azure Edition Hotpatch - x64 Gen2
</p>
<br />

---
## Congratulations, we have created Virtual Machines, a Virtual Network, and a Domain Controller. With this in your Microsoft Azure you are free to go forward and practice more skills!
