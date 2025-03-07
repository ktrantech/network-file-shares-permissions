<p align="center">
<img src="https://i.imgur.com/AeiqMDZ.png" alt="Traffic Examination"/>
</p>

<h1>Network-File-Shares-and-Permissions</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Domain Controller/Client Machine)
- Remote Desktop
- Shared Network Files

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

</p>
<p>
In this lab, we will configure shared network files and manage permissions. We will create folders on the DC-1 virtual machine and share them across the network, each with specific access rights. Only authorized individuals will have permission to view certain files. Let's dive in! First, navigate to the C:/ drive on the DC-1 machine and create the following four folders: 'read-access,' 'read/write-access,' 'no-access,' and 'accounting.'"
</p>
<br />

<p>
<img src="https://i.imgur.com/k70dozS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After the folders have been created what you want to do is share them on the network so that the client-1 machine can view them. We can also set the permissions of the folders in DC-1. Set the folders to the appropriate permissions. "read-access" should be read only for domain users, "read/write access" should have read/write permissions for domain users. Lastly "no-access" should have read/write permissions for domain admins only.
</p>
<br />

<p>
<img src="https://i.imgur.com/wcpB5Ex.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<img src="https://i.imgur.com/hku11Pt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p>
If we log in to the client machine with a normal user account we can test out the shared files we just created. As you can see the permissions that we set are working properly.
</p>
<br />
<p>
<img src="https://i.imgur.com/CGQ8yaO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<img src="https://i.imgur.com/f9TldBO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p>
</p>
Go back to the DC-1 VM. In AD create a security group called "Accountants" the users assigned to this security group will be the only ones allowed to view the "Accountants" folder. We have to share the "Accountants" folder just like we did in the last section, we will be sharing it with only the accountants' group. Normal users will not have access to this folder. If we wanted to give a normal user access to the accounting folder they would have to be a part of the "Accountants" security group.
</p>
<br />
<p>
<img src="https://i.imgur.com/QADy92Z.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<img src="https://i.imgur.com/BUm3L2Q.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<img src="https://i.imgur.com/fH8fU7b.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
