# Small Office Network Building Lab


<img width="1280" height="882" alt="Image" src="https://github.com/user-attachments/assets/afa4ee14-5d28-45ee-ad04-112542523c7b" />


Overview:
This project models a functional small office network using Packet Tracer, including router, switch, DHCP, DNS, and end devices.

Key Components:
- Configured DHCP scopes, DNS records, and IP addressing.
- Designed a network diagram with routers, switches, and clients.
- Simulated common network failures: DNS outages, IP conflicts, gateway misconfigurations.
- Created a professional troubleshooting guide with command outputs.
  
Skills Demonstrated:
- TCP/IP fundamentals
- DNS & DHCP configuration
- Network troubleshooting (ping, tracert, nslookup) - Network design & documentation


# Lets start by Building the Small Office Network

So here is where we are goimng to grab our router, switch, DHCP, DNS, and end devices and connect them using our cables aswell.

 
So let start with our router and switch.

for your router we  are using 2911 model




<img width="653" height="135" alt="Image" src="https://github.com/user-attachments/assets/b97452ac-e5a6-4b9d-b599-5eab212daefb" />

For your switch we are using 2960



<img width="650" height="162" alt="Image" src="https://github.com/user-attachments/assets/0cbeeeb6-27ec-4653-8dfe-4fe93a04132d" />



<img width="614" height="413" alt="Image" src="https://github.com/user-attachments/assets/9c3fe97f-ddc1-45b6-bae3-3b770224137f" />



After that lets go to our end devices and grab out PCs and Servers



<img width="753" height="155" alt="Image" src="https://github.com/user-attachments/assets/b07f5199-cbb0-43c3-b0f8-6a3bbd5025bb" />



Grab and layout your PCs 0-5 and both Servers DHCP and DNS




<img width="1178" height="690" alt="Image" src="https://github.com/user-attachments/assets/a9fad945-2ac4-4c1c-981d-6fdcf01ff9a0" />




Once all devices have been added ... now lets connect them together to create the network 



Let's use the auto connector which looks like a lighting bolt connecting the severs and PCs to the switch. 


<img width="672" height="156" alt="Image" src="https://github.com/user-attachments/assets/8782b506-f4c2-4522-a673-72df79c0535d" />



<img width="1155" height="710" alt="Image" src="https://github.com/user-attachments/assets/1ec7d198-c346-4740-a143-13046a67c0ae" />


Now to connect the router to the switch we wil have to use the straight though cable connecting router gigabitEthernet 0/0  and the switch FastEthernet0/9  . 

<img width="932" height="554" alt="Image" src="https://github.com/user-attachments/assets/fb08b01f-f86a-4854-b86f-284976d9b093" />

<img width="765" height="602" alt="Image" src="https://github.com/user-attachments/assets/c51bf74c-57fe-4697-a446-cb71f5761e11" />

# Configuring the devices on the network

Let's work on the router first lets click Router 0 and in the router window lets go to the CLI tab 

<img width="696" height="700" alt="Image" src="https://github.com/user-attachments/assets/6adc163f-77b4-4d62-bfc0-2554cde29eee" />

In the CLI tabs let press the enter key to get started

<img width="500" height="131" alt="Image" src="https://github.com/user-attachments/assets/49a1f1ab-433d-409b-9662-d09ff466e779" />

- Step 1 After that type enable enter. Now then config t which leads to you admin commands and privaliges for the router.(You will know your in configurastion commands because it will say Router(configt)#)
  
<img width="497" height="46" alt="Image" src="https://github.com/user-attachments/assets/5a604f66-d68d-4ebb-acad-13215eb26f7d" />
<img width="409" height="46" alt="Image" src="https://github.com/user-attachments/assets/2c5035bb-ee44-44f4-a871-033ef83f56e0" />

- Step 2 Type interface g0/0 and enter (which if you rememeber when you connected the Router to the Switch the gigabitEthernet 0/0 that we connected to so if you use a different gigabitEthernet use that on this step but mine was 0/0). Set the IP address and subnet mask so type IP address and whatever Ip address you want save and give it a subnet mask ( I'm using 192.168.10.1 for my IP address and 255.255.255.0 as my subnet mask )
  
<img width="624" height="92" alt="Image" src="https://github.com/user-attachments/assets/db55a996-ce1a-4e0b-b09b-29814256b49d" />

- Step 3 Type no shutdown so it always stays on then exit.

 <img width="491" height="164" alt="Image" src="https://github.com/user-attachments/assets/8dce5a28-0edc-4f33-85b4-759d627c3e46" />

- Step 4 Now lets lets set up our DHCP pool(network,main baseline IP address,DNS server).First lets Type ip dhcp pool ABC-POOL hit enter.
  
  + Type network 192.168.10.0  255.255.255.0.
    
  + Now like let's configure the main baseline IP address by typing default-router 192.168.10.1.
      
  + Then the DNS server by typing dns-server 192.168.10.11
    
  + Type exit and exit again to completely leave the configuration setting and write memory.
    
<img width="1280" height="882" alt="Image" src="https://github.com/user-attachments/assets/afa4ee14-5d28-45ee-ad04-112542523c7b" />

 Now we should see all green arrowns meaning connectity. now lets configure the end users devices starting with PC0.
 
- Step 1 Click on the PC let find the desktop tab there you should see that it is on is default IP configuration which is static.We want to chose DHCP and you will see that it is atomicatically assigned to the DHCP configurations which we set up above.
  
- Step 2 Repeat step 1 for each device (Notice every PC will have the a different IP address but still on the same network)
  
- Step 3 now that you finished configuring lets ping our PCs.Go to your Desktop tab and click command Prompt.lets ping our first PC so type ping  192.168.10.2 which is our IP address for our PC0.After seeing the ping work Ping the next 5 PC using their IP address(so the command will be ping 192.168.10.3-5) to see if the are connected).
  

Now lets configure the PCs
---
Now lets configure the IP address for PC 0-5. 

<img width="541" height="226" alt="Image" src="https://github.com/user-attachments/assets/f70f05bf-b692-4a02-9ab1-5d880c77a9e2" />
<img width="755" height="407" alt="Image" src="https://github.com/user-attachments/assets/aa48b20e-8e4f-4db9-a56f-5ba9292c61b1" />

So lets click on PC0 and once inside click on Desktop tab and once in the desktop tab click on the IP Configuration tab.

<img width="956" height="662" alt="Image" src="https://github.com/user-attachments/assets/bff8ba81-047d-47f2-9a07-274d1f346e53" />

Once inside the IP config page you will see that it is on it's default setting of static which can be used if you want to manual configure it but in this case we have a DHCP server that we have already configured though the router and DHCP server. So now let click on the DHCP and you will see that it automatically  configures the IP address, Subnet mask , Default Gateway , and DNS Server. (You will see that the IP address was assigned to 192.168.10.2, Subnet mask 255.255.255.0, Default Gateway 192.168.10.1, and DNS Server 192.168.10.11)

<img width="927" height="455" alt="Image" src="https://github.com/user-attachments/assets/98cfcbef-e3ac-4c6b-8923-0379a62090c2" />

Now lets repeat it for PC 1 - 5  and as you can see the IP address changes for each Device.

<img width="924" height="455" alt="Image" src="https://github.com/user-attachments/assets/b65ab013-6107-4436-980f-13de1f216391" />


<img width="932" height="455" alt="Image" src="https://github.com/user-attachments/assets/438cea30-457d-4a10-9c8f-b01b91e5e490" />


<img width="944" height="457" alt="Image" src="https://github.com/user-attachments/assets/9fa3bd4b-2463-45aa-89fd-d26d70ef9f71" />


<img width="935" height="452" alt="Image" src="https://github.com/user-attachments/assets/ab887cf9-f26b-4d50-9eb6-1e571dfc1bb6" />

 
<img width="941" height="460" alt="Image" src="https://github.com/user-attachments/assets/3d3051e4-64b7-4fcf-b923-023254bf69ac" />

  
  
