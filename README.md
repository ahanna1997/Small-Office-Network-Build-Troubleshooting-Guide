# Small Office Network Building Lab


<img width="1150" height="842" alt="Image" src="https://github.com/user-attachments/assets/2917e78f-8d89-4216-9048-78ddcc6b61d7" />


Overview:
This project models a functional small office network using Packet Tracer, including router, switch, DHCP, DNS, and end devices.

Key Components:
- Configured DHCP scopes, DNS records, and IP addressing.
- Designed a network diagram with routers, switches, and clients.
- Simulated common network failures: DNS outages, IP conflicts, gateway misconfigurations. - Created a professional troubleshooting guide with command outputs.
  
Skills Demonstrated:
- TCP/IP fundamentals
- DNS & DHCP configuration
- Network troubleshooting (ping, tracert, nslookup) - Network design & documentation


# Lets start by Building the Small Office Network

So here is where we are goimng to grab our router, switch, DHCP, DNS, and end devices and connect them using our cables aswell.

 
So let start with our router and switch

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

- Step 1 After that type enable enter then configt which leads to you admin commands and privaliges for the router.(You will know your in configurastion commands because it will say Router(configt)#)

- Step 2 Type interface g0/0 and enter (which if you rememeber when you connected the Router to the Switch the gigabitEthernet 0/0 that we connected to so if you use a different gigabitEthernet use that on this step but mine was 0/0)

- Step 3  Set the IP address and subnet mask so type ip address and whatever Ip address you want spave and give it a subnet mask ( I'm using 192.168.10.1 for my IP address and 255.255.255.0 as my subnet mask )

- Step 4 Type no shutdown so it always stays on then exit.

- Step 5 Now lets lets set up our DHCP pool(network,main baseline IP address,DNS server).First lets Type ip dhcp pool ABC-POOL hit enter.
  + Type network 192.168.10.0  255.255.255.0.
  + Now like let's configure the main baseline IP address by type default-router 192.168.10.1 .
  + Then the DNS server by typing 192.168.10.254
  + Type exit and exit again to completely leave the configuration setting and write memory.

 Now we should see all green arrowns meaning connectity. now lets configure the end users devices starting with PC0
- Step 1 Click on the PC let find the desktop tab there you should see that it is on is default IP configuration which is static.We want to chose DHCP and you will see that it is atomicatically assigned to the DHCP configurations which we set up above.
  
- Step 2 Repeat step 1 for each device (Notice every PC will have the a different IP address but still on the same network)
  
- Step 3 now that you finished configuring lets ping our PCs.Go to your Desktop tab and click command Prompt.lets ping our first PC so type ping  192.168.10.2 which is our IP address for our PC0.After seeing the ping work Ping the next 5 PC using their IP address( so the command will be ping 192.168.10.3-5) to see if the are connected.
  
- Step 4
  
  
