<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1> Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of Active Directory within Azure Virtual Machines.

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>Deployment and Configuration Steps</h2>

1. Create a Resource Group

<img width="2559" height="1439" alt="Screenshot 2025-07-19 090755" src="https://github.com/user-attachments/assets/23e29466-ebc8-45f8-8587-97223ab38a2b" />

2. Create a Virtual Network and Subnet

<img width="2559" height="1439" alt="Screenshot 2025-07-19 123334" src="https://github.com/user-attachments/assets/6fc16bf1-616c-41e8-9545-c5b9ce7dd9ca" />

3. Create the Domain Controller VM (Windows Server 2022) named “DC-1”
   
- Username: labuser
  
- Password: Cyberlab123!

<img width="2559" height="1439" alt="Screenshot 2025-07-19 123836" src="https://github.com/user-attachments/assets/e5215028-c969-4d09-b757-170644b41d00" />

4. After the VM is created, set the Domain Controller’s NIC Private IP address to be static

<img width="2559" height="1439" alt="Screenshot 2025-07-19 124822" src="https://github.com/user-attachments/assets/6693caf5-99fb-43f7-b986-f0f1a4a38a86" />

5. Log into the VM and disable the Windows Firewall (for testing connectivity)

<img width="2559" height="1439" alt="Screenshot 2025-07-19 125254" src="https://github.com/user-attachments/assets/ef3634a3-3e22-46ba-8bda-032d3cf9fee3" />

6. Create the Client VM (Windows 10) named “Client-1”

- Username: labuser

- Password: Cyberlab123!
  
- Attach it to the same region and Virtual Network as DC-1

<img width="2559" height="1439" alt="Screenshot 2025-07-19 123836" src="https://github.com/user-attachments/assets/3edb87a3-06c8-49cf-940a-67cf0e8daff7" />

7. After VM is created, set Client-1’s DNS settings to DC-1’s Private IP address

<img width="2559" height="1439" alt="Screenshot 2025-07-19 125804" src="https://github.com/user-attachments/assets/c07108b3-f6b7-4bd4-b189-ebb97360e599" />

8. From the Azure Portal, restart Client-1

- Log in to Client-1

- Attempt to ping DC-1’s private IP address

- Ensure the ping succeeded

<img width="2559" height="1439" alt="Screenshot 2025-07-19 130519" src="https://github.com/user-attachments/assets/813e08db-8438-4b29-b9f3-53d151253af8" />

  9. From Client-1, open PowerShell and run ipconfig /all
      
- The output for the DNS settings should show DC-1’s private IP Address

<img width="2559" height="1439" alt="Screenshot 2025-07-19 130719" src="https://github.com/user-attachments/assets/d0b18efb-d9d9-43f9-b9cd-529ab2ed5e11" />





