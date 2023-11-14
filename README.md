# Active-Directory
I installed and configured Active Directory for 1,000 users.

## Steps:

1st: Download the Windows Server 2019 ISO disk and create the VM in VirtualBox, this will be your Domain Controller.
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
