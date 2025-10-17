# Summary


# AWS Configuration

This project is completed trough AWS Website and Interfaces as we are provided Virtual Machines and ways to manipulate them.

The objective here is to set everything before hand.
- Set Virtual Machines;
- Set Elastic IPs;
- Set Security Groups.

## Virtual Machines

Starting with Windows Server, steps here will be the same for all others besides the contents of the machine.

It will be required to lauch the instances.
You can do so following the current images.

![Lauching Instances 1](/Images/Screenshots%20AWS/WinServer/AWS_1.png)
![Lauching Instances 2](/Images/Screenshots%20AWS/WinServer/AWS_2.png)


-- Windows Virtual Machine --
TYPE: c5.large
OS: Windows Server 2022
VPC: Default
SUBNET: Public
PRIVATE IP: DHCP Automatic
ELASTIC IP: Yes
SG GROUP: RDP(3389), HTTP, HTTPS, DNS (53 TCP/UDP), LDAP, SMB, Kerberos(88)

As seen in images below.
![Setting Windows VM 1](/Images/Screenshots%20AWS/WinServer/AWS_3.png)
![Setting Windows VM 2](/Images/Screenshots%20AWS/WinServer/AWS_4.png)
![Setting Windows VM 3](/Images/Screenshots%20AWS/WinServer/AWS_5.png)
![Setting Windows VM 4](/Images/Screenshots%20AWS/WinServer/AWS_6.png)

-- Ubuntu Virtual Machine --
TYPE: t3.medium
OS: Ubuntu Server 24.04 LTS
VPC: Default
SUBNET: Public
PRIVATE IP: DHCP Automatic
ELASTIC IP: Yes
SG GROUP: SSH, HTTP, HTTPS, SMTP, IMAP, POP3

Same process as above.

-- Clients Virtual Machine --
TYPE: c5.large
OS: Windows 11 Pro
VPC: Default
SUBNET: Private (Same avaiability zone as Windows Server)
PRIVATE IP: DHCP Automatic
ELASTIC IP: Yes
SG GROUP: RDP, ICMP

Same process as above.
Either create two at once (Can be seen on the right) or do process twice.

## Elastic Ips

Elastic IPs will allow for perpetual use of these Virtual Machines, this way there is no need to reconfigure the public IPs every day.

Elastic IP's menu interface can be found on tab on the left of AWS Interface
![Elastic IP location](/Images/Screenshots%20AWS/Elastic_IP/AWS_7.png)

By accessing that interface it is possible to create Elastic Ips by clicking the big orange button. For this project two will be Allocated.
![Creating 2 Elastic IPs](/Images/Screenshots%20AWS/Elastic_IP/AWS_9.png)

Afterwards by either clicking the 'Action' button on top right or right-click an Elastic IP, it is possible to allocate it to a Virtual Machine.
![Allocating Elastic IP - Finding Menus](/Images/Screenshots%20AWS/Elastic_IP/AWS_14.png)
![Allocating Elastic IP - Interface](/Images/Screenshots%20AWS/Elastic_IP/AWS_15.png)
![Allocating Elastic IP - Results](/Images/Screenshots%20AWS/Elastic_IP/AWS_16.png)

## Security Groups

These are all beeing set now as it is known what they will require thanks to information above.

To set Security Groups (sg for short) one must access their menu interface trough the tab on the left.
![Finding it on tab](/Images/Screenshots%20AWS/SecurityGroups/AWS_22.png)

I myself made three of them right away with a only an RDP for the current IP of my machine and later edited the remaining ones.
Just like Elastic IP, big orange button to create security groups.
![Finding security group](/Images/Screenshots%20AWS/SecurityGroups/AWS_23.png)
![writing IP](/Images/Screenshots%20AWS/SecurityGroups/AWS_25.png)
![Result, 3 more times](/Images/Screenshots%20AWS/SecurityGroups/AWS_27.png)

To close these security groups in a 'castle' or 'bubble' it will be required to find what is VPC's or Subnet's IP.
To do so from Instances click on subnet to find IP. It can be found inside 'Networking' tab.
![Instance screen](/Images/Screenshots%20AWS/SecurityGroups/AWS_28.png)
![Networking to find sg](/Images/Screenshots%20AWS/SecurityGroups/AWS_29.png)

Knowing that Subnet's IP it is possible now to block the machines from the outside by editing Inbound groups.
Finish groups by filling remaining fields above mentioned.
![WinSer sg](/Images/Screenshots%20AWS/SecurityGroups/AWS_30.png)
![UbuntuSer sg](/Images/Screenshots%20AWS/SecurityGroups/AWS_31.png)
![WinClient sg](/Images/Screenshots%20AWS/SecurityGroups/AWS_32.png)

In the end it would look as such:
![final sg groups](/Images/Screenshots%20AWS/SecurityGroups/AWS_33.png)

Do not forget however to replace all security groups on the correct virtual machines, otherwise no connection to them is possible.
![Were to find menu](/Images/Screenshots%20AWS/SecurityGroups/AWS_34.png)
![changing interface](/Images/Screenshots%20AWS/SecurityGroups/AWS_35.png)

# Windows Server Set-up

In this project Windows10 was used as the Main Server.
For working proccess both Windows10 and Windows11 have the same proccess besides the diferent UI.

Start by changing this Computer's name.
In this case I called this computer Winsrv.
![Computer Properties](/Images/WinServer/InitialSetup/2.png)
![Name Change UI](/Images/WinServer/InitialSetup/3.png)

Always Restart a Windows Computer when it asks.
![Restart Computer](/Images/WinServer/InitialSetup/4.png)

## Initial Server Configuration

## Activa Directory Installation and Configuration

## DNS Configuration

## Users Set-up

## Mobalizing User

## Network Sharing with Regional Permissions

## Internet Information Services Set-Up 


# Ubuntu Email Server Set-up

## Initial Configuration

## Web Server Configuration

## Certifying Server

## Enail Server Configuration

## Creting Usernames and Emails


# Windows Clients Set-up

## Joining Domains

## Installing Software - Google Chrome

## Installing Software - Mozilla Thunderbird

## Thunderbird Configuration - WS-OCE01

## Thunderbird Configuration - WS-CEN01


# Tests and Results

## Windows Server Tests

## Linux Server Tests

## Windows Clients Tests


## Email Tests

