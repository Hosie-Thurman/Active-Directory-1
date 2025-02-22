<p align="center">
  
![Image](https://github.com/user-attachments/assets/5cde0913-0053-42bf-8927-9adcce00239b)

<h1>Configuring VMs and Installing Active Directory</h1>

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)









<h3>Step 1: Creating the Resource Group and Virtual Network</h3>

-Log in to Azure Portal.

-Go to Resource Groups

-Click Create

-Name your group and select a region

-Click Create again

-Go to Virtual Networks

-Click Create.

-Name your network, choose a region
Click Create again.


![Image](https://github.com/user-attachments/assets/b2de952e-cb4a-4412-9e5e-26bd563c9de7)

![Image](https://github.com/user-attachments/assets/3e201827-d157-4fa9-9848-46f27ba8bf1c)



h3>Step 2: Create the Domain Controller VM</h3>

-Go to Virtual Machines 
-Click Create

-Fill in the details:
    * Name your VM DC-1
* Choose Windows Server 2022 for the operating system 
    * Select a Region, Size, and OS (like Windows or Linux).
    * Set Username - DC- 1 ———  Password - Password1

-Make sure to add the VM to the Resource Group and Virtual Network that was created


![Image](https://github.com/user-attachments/assets/17d17b88-00fd-4715-b5a2-9a2d787d2c9c)


h3>Step 3: Create the Client VM</h3>

-Go to Virtual Machines 
-Click Create

-Fill in the details:
    * Name your VM Client-1
* Windows 10 pro for the operating system 
* Attach it to the same region and Virtual Network as DC-1
    * Set Username - DC- 1 ———  Password - Password1

-Make sure to add the VM to the Resource Group and Virtual Network that was created


![Image](https://github.com/user-attachments/assets/315f7c4e-ad54-4dfc-9af4-c6499958eb8d)

h3>Step 4: Changing the Domain Controller IP to Static </h3>

- Go to Networking → Click Network Interface.

- Under IP Configurations, select your IP config.

- Change Assignment to Static → Save.


![Image](https://github.com/user-attachments/assets/c59c625c-7848-4f62-86c3-8a1a836e02b9)

![Image](https://github.com/user-attachments/assets/abfe1dcf-44ad-4364-9149-3ace3cbff4c9)

![Image](https://github.com/user-attachments/assets/b8056c53-2b56-4855-a82d-cfffd4312a56)



h3>Step 5: Changing Client-1 DNS Setting</h3>

* In Azure Portal, go to Virtual Machines.

* Click on DC-1 (your Domain Controller).

* Go to the Networking tab.

*  Copy the Private IP address.

- In Client-1’s settings, go to Networking (left menu).

- Click Network Interface (under Network settings).

- Under Settings, select DNS servers.

- Choose Custom and enter DC-1’s Private IP as the DNS server.

- Click Save.

- From the Azure Portal, restart Client-1

![Image](https://github.com/user-attachments/assets/20cb5c53-5460-4590-ac94-9af291523e40)


h3>Step 6: Changing DC-1 VM Firewall Settings</h3>

- Login to DC-1
- Open Control Panel (Press Win + R, type control, and press Enter).
- Click System and Security → Windows Defender Firewall.
- In the left menu, click Turn Windows Defender Firewall on or off.
- For each profile shows switch the Firewall State for On → Off

![Image](https://github.com/user-attachments/assets/00ae1811-62de-41b3-80de-60467d1e79c9)

![Image](https://github.com/user-attachments/assets/ed1c2775-4af0-4fd8-8caf-cadd21827a66)

![Image](https://github.com/user-attachments/assets/a497a335-fdf6-4d70-81ae-b42a467a57c9)


h3>Step 7: Changing Client-1 DNS Setting</h3>

- Login to Client-1

- Attempt to ping DC-1’s private IP address

- Ensure the ping succeeded

- From Client-1, open PowerShell and run ipconfig /all

- The output for the DNS settings should show DC-1’s private IP Address


![Image](https://github.com/user-attachments/assets/8f9d11b9-e466-44ad-a36e-830c3edcd386)

![Image](https://github.com/user-attachments/assets/2e002bd8-2636-40dd-b397-285fc6b1bf2c)




<h2>osTicket:Active Directory VMs are all setup</h2>

