# Active Directory Home Lab Project
###### VirtualBox Download: https://www.virtualbox.org/wiki/Downloads
###### Windows Server 2019 ISO Download: https://www.microsoft.com/en-us/evalcenter/download-windows-server-2019
###### Windows 10 ISO Download: https://www.microsoft.com/en-us/software-download/windows10

I installed and configured Active Directory for 1,000 users.

Tasks Performed:

• Installed Windows Server 2019 

# Steps:

## Installing Windows Server 2019:

1st Step: Download the Windows Server 2019 ISO disk and create the VM in VirtualBox, this will be your Domain Controller.

![image](https://github.com/andrewsingleton2/Active-Directory/assets/150304510/3c117755-b5f5-4965-b6f8-4b1f376a8e1b)

2nd Step: Make sure you add two network adapters in your DC's settings. (Set the first adapter to NAT to allow the VM to connect to your home network and the second adapter set to Internal Network for the VM machine)
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

## Installing Active Directory

10th Step: Click "Add roles and features", then select Active Directory Domain Services when selecting Server Roles.
![image](https://github.com/andrewsingleton2/Building-An-Active-Directory/assets/150304510/1d3f849b-1746-462e-81c6-b604c22e0a92)

