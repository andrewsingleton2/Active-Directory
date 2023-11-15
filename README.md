# Active Directory Home Lab Project

I installed and configured Active Directory for 1,000 users.

### Tasks Performed:

• Installed Windows Server 2019 and configured it as the domain controller.

• Installed and Configured Active Directory, added myself as an Admin.

• Installed and Configured RAS/NAT.

• Setting Up A DHCP Server. (Allows Windows 10 users to automatically get an IP to access and browse the internet)

### (Downloads)
###### VirtualBox Download: https://www.virtualbox.org/wiki/Downloads
###### Windows Server 2019 ISO Download: https://www.microsoft.com/en-us/evalcenter/download-windows-server-2019
###### Windows 10 ISO Download: https://www.microsoft.com/en-us/software-download/windows10

# These Are The Steps I Took To Complete This Project.

# Installing Windows Server 2019:

1st Step: Download the Windows Server 2019 ISO disk and create the VM in VirtualBox, this will be your Domain Controller.

![image](https://github.com/andrewsingleton2/Active-Directory/assets/150304510/3c117755-b5f5-4965-b6f8-4b1f376a8e1b)

2nd Step: I added two network adapters in the VM's settings. (Set the first adapter to NAT to allow the VM to connect to your home network and the second adapter set to Internal Network for the VM machine)
![image](https://github.com/andrewsingleton2/Active-Directory/assets/150304510/b2b6ffa6-3192-4cdd-b8fb-86e7dd944f8b)
![image](https://github.com/andrewsingleton2/Active-Directory/assets/150304510/c5e1087b-6ba6-4b1d-bae7-c6ece018e97b)

3rd Step: Save your VM settings and boot the Windows Server 2019 VM. 

MAKE SURE to select "Standard Desktop Experience" when booting the VM, otherwise, you will only have a command line interface.
![image](https://github.com/andrewsingleton2/Active-Directory/assets/150304510/4c5a4f7a-d4c9-4191-88c3-0e576f6573f2)

4th Step: Select "Custom Install" and click next.
![image](https://github.com/andrewsingleton2/Active-Directory/assets/150304510/b859f2aa-dec5-4cfa-8857-4c2f52361a59)

5th Step: Let the VM install.
![image](https://github.com/andrewsingleton2/Active-Directory/assets/150304510/2ae8840b-3b19-4b19-b78c-5ba78530cd6c)

6th Step: Set your credentials.

![image](https://github.com/andrewsingleton2/Active-Directory/assets/150304510/9db1e6ed-caa7-413f-bb00-46dbf219c50d)

7th Step: (Optional) To make it easier to identify, you can rename the PC to "DC" for the domain controller, instead of keeping it the default randomized name.

![image](https://github.com/andrewsingleton2/Building-An-Active-Directory/assets/150304510/9c14caac-c1be-4b48-b559-06f3a128bf58)

8th Step: (Optional) Go to your ethernet settings and select "Change adapter options". Your network adapters should be named Ethernet by default, to make it easier you can name your external network "INTERNET" (identified from 10.x.x.x ip), and your internal network "Internal" (identified by any class B public IP range that your VM has). You can locate these IP's when right-clicking the adapter and selecting "Status", then "Details".

![image](https://github.com/andrewsingleton2/Building-An-Active-Directory/assets/150304510/bff961b6-7e6a-4b26-b0c5-d99711163f93)
![image](https://github.com/andrewsingleton2/Building-An-Active-Directory/assets/150304510/0e0d8d1e-3829-42fc-9a1b-2bb42838b376)

9th Step: Select the "Internal" network and click properties, then IPv4 and enter the IP information provided in the screenshot, then click ok. (Once AD is installed, the server will use itself as the DNS)

![image](https://github.com/andrewsingleton2/Building-An-Active-Directory/assets/150304510/aef26b89-275e-4088-8c08-33eb81448b98)

# Installing and Configuring Active Directory:

1st Step: Click "Add roles and features", then select Active Directory Domain Services when selecting Server Roles.
![image](https://github.com/andrewsingleton2/Building-An-Active-Directory/assets/150304510/1d3f849b-1746-462e-81c6-b604c22e0a92)

2nd Step: Click Install and close once the installation is complete.
![image](https://github.com/andrewsingleton2/Building-An-Active-Directory/assets/150304510/ca7b1f9a-e7c0-44ea-b906-7f38ab900d79)

3rd Step: Click "Promote this server to a domain controller", then name the domain "mydomain.com" and then install. Once it's installed the VM will restart.

![image](https://github.com/andrewsingleton2/Building-An-Active-Directory/assets/150304510/f57916d0-22e6-4025-a08c-0a4111ecb140)
![image](https://github.com/andrewsingleton2/Building-An-Active-Directory/assets/150304510/6ec3e872-0017-4d04-81fd-2db2b85db891)

4th Step: Click Active Directory Users and Computers > right-click mydomain.com > new > organization unit > and create a unit for admins, as seen in the screenshot below.
![image](https://github.com/andrewsingleton2/Building-An-Active-Directory/assets/150304510/e837fffa-7726-43bc-b579-96ced87e24e7)

5th Step: Right-click _ADMINS (or what you named your admin org unit as) > new > user, and create your own personal admin account. Set your password and uncheck "User must change password at next login" and check "Password never expires".

![image](https://github.com/andrewsingleton2/Building-An-Active-Directory/assets/150304510/2742898d-1c56-4d4d-8ce5-01092565f42c)
![image](https://github.com/andrewsingleton2/Building-An-Active-Directory/assets/150304510/295078a9-63a2-480c-bcc5-e31f8e8ee3a0)

6th Step: Right-click your name > properties > the "member of" tab > add > type "domain admins" and click check names > then apply.

![image](https://github.com/andrewsingleton2/Building-An-Active-Directory/assets/150304510/d3646129-2e85-4080-b1e2-06f0e6f128a1)

7th Step: Sign out of your domain account and click "Other User", and log into the admin account you just created for yourself.

![image](https://github.com/andrewsingleton2/Building-An-Active-Directory/assets/150304510/e217ac4f-8e7a-4d55-8865-764a773b0cbb)

# Installing and Configuring RAS/NAT
1st Step: Go back to Server Manager and click "add roles and features" > select "Remote Access" > check "Routing" > then Install.

![image](https://github.com/andrewsingleton2/Building-An-Active-Directory/assets/150304510/dc729d7d-03c8-4954-b410-e929f5c7be87)
![image](https://github.com/andrewsingleton2/Building-An-Active-Directory/assets/150304510/d94174c7-04c7-47c7-b5e0-347ccd48a5a9)

2nd Step: Go to Tools > click Routing and Remote Access > right-click DC (local) and click configure and enable > select your internet interface and click next and finish.

![image](https://github.com/andrewsingleton2/Building-An-Active-Directory/assets/150304510/b69b6ff4-5163-478f-b391-4a4e299128a0)
![image](https://github.com/andrewsingleton2/Building-An-Active-Directory/assets/150304510/9253c806-ae1e-4657-8ddc-cf5312ec4100)

# Setting Up A DHCP Server:

1st Step: Go back to the server manager > click "Add roles and features" > add "DHCP Server" > and install.

![image](https://github.com/andrewsingleton2/Building-An-Active-Directory/assets/150304510/79002618-486e-4057-b211-d347c4d428b4)

2nd Step: Click tools > DHCP > right-click IPv4 > New Scope > name the scope "172.16.0.100-200" > list the start IP, end IP, and subnet mask as it is and the screenshot below and click next.

![image](https://github.com/andrewsingleton2/Building-An-Active-Directory/assets/150304510/29410f50-3b5f-42e0-8b89-6ed436f13e3f)
![image](https://github.com/andrewsingleton2/Building-An-Active-Directory/assets/150304510/d0876985-4dfc-4796-865e-ae1c15f43d45)

3rd Step: Enter the DC IP address (172.16.0.1) and click add, and add the IP 172.16.0.1 if it's not already there, then finish.

![image](https://github.com/andrewsingleton2/Building-An-Active-Directory/assets/150304510/a1b4bcd7-8eec-45b6-b2aa-d3d678d66e22)

4th Step: Right-click dc.mydomain.com > click Authorize > right-click dc.mydomain.com again and click Refresh.

![image](https://github.com/andrewsingleton2/Building-An-Active-Directory/assets/150304510/5aeb36ac-ee05-4469-b309-bc4cd30aaa16)

# Downloading a PowerShell Script to Create Sample Accounts on Active Directory

1st Step: Download the script here and save to your desktop. https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbk0yZWs5NURNTUtXLS14cmNuaVZfMnBqeUpKQXxBQ3Jtc0tuWTZCcExSYU1aQmtyelQ5eml6XzlBbGkzRU5FWi0tVlhNRC0xUnNYTlU5LWpNbXNMTW1faGtPQjRpZXI4SWtOdW1NaDFTSnJEM2I5SmJhalBZOWFsX1ZWY3NTa2swMWd0UWJqOUdWNTgzakItWW4tcw&q=https%3A%2F%2Fgithub.com%2Fjoshmadakor1%2FAD_PS%2Farchive%2Frefs%2Fheads%2Fmaster.zip&v=MHsI8hJmggI

Then click on Start (windows icon) > Windows PowerShell > right-click Windows PowerShell ISE > more > click Run as administrator

![image](https://github.com/andrewsingleton2/Building-An-Active-Directory/assets/150304510/fda545ee-c12a-453b-85f8-71c59fdae808)

2nd Step: Click on the folder in the top left "Open Script" > click 1_CREATE_USERS > Open.

![image](https://github.com/andrewsingleton2/Building-An-Active-Directory/assets/150304510/e39e56ae-2eb2-4847-8a42-5d10bb9b8c45)

3rd Step: Turn off the security feature preventing the script from running, by typing Set-ExecutionPolicy Unrestricted > then click Yes to All.
![image](https://github.com/andrewsingleton2/Building-An-Active-Directory/assets/150304510/366a2dbc-b160-4a18-a59b-32bbfe91e482)
