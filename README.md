# sp-sdwan
# Aruba Silver-Peak SD-WAN solution with Multicast Routing

This documantation contains configuration file of Silver-Peak Orchestation's and Guide how to multicast routing.  

This is the LAB which contains sites like HQ, Ankara, Antalya and Izmir. The Wide Area Network (WAN) have 3 different connection types which are ISP1, ISP2 and MPLS. MPLS is the closed circuit, there is no internet connection and only connected HQ, Ankara and Antalya. ISP1 have real internet connection but simulated Public IP address 89.0.0.x/30 and connected HQ, Izmir and Antalya.  ISP2 have real internet connection but simulated Public IP address 88.0.0.X/30 and connected HQ and Izmır. ISP1 and ISP2 can routes eachother that their connected interfaces' Public IP. 


ISP1 and ISP2 are Linux Machine with routing enabled and they have a script for manipulating connectivity Delay, Packet Lose etc..

<img width="1164" alt="image" src="https://user-images.githubusercontent.com/111356277/184869971-bebeccbe-5ddc-412b-a7a1-24b29395329e.png">

HQ has Windows10 and Linux Machines, Linux Machine will work as Multicast Server wich can straeam video file with ffmpeg. Other sites have only Windows10 machines can IGMP join and play Multicast videos. 

After make initial configuration all tunnels UP 
<img width="1417" alt="image" src="https://user-images.githubusercontent.com/111356277/184874831-e50bd68e-bfb4-4229-a567-0a30b8a0cdf9.png">

Because of a habit from the past, I have configured LoopBack interface on HQ. The other sites can reach this Lo interface because all sites advertises LAN interfaces with eachother. 

To configure Multicast go to Orchestrator Configuration -> Routing Section -> Multicast

<img width="796" alt="image" src="https://user-images.githubusercontent.com/111356277/184879747-7ae970f9-9a3d-4e69-a0fb-5de15fbd4577.png">

For multicast routing, Aruba Silver-Peak Solution does not need any external Rendezvous Point (RP) router as like other SD-WAN solutions. You just need enable multicast routing which sites can reach. I configured HQ's lo0 address (192.168.255.255/32) as RP. 




## HQ - Multicast Configuration
<img width="1387" alt="image" src="https://user-images.githubusercontent.com/111356277/184877368-0fd3d346-c135-4ca0-a942-dfd9ae17e1ca.png">

PIM shoud be enabled all LAN interfaces that you use Multicast routing but IGMP should be enabled only receivers on your LAN.
<img width="301" alt="image" src="https://user-images.githubusercontent.com/111356277/184879275-6c861db1-f82f-460c-a14e-4dba774d8224.png">

## ANKARA - Multicast Configuration 
<img width="1434" alt="image" src="https://user-images.githubusercontent.com/111356277/184880578-c8becf87-9a02-4f47-a048-cced9ce4b571.png">

## ANTALYA - Multicast Configuration
<img width="1414" alt="image" src="https://user-images.githubusercontent.com/111356277/184880773-74f49e15-f798-443f-96bc-d6b6b14362e7.png">

## IZMIR - Multicast Configuration
<img width="1447" alt="image" src="https://user-images.githubusercontent.com/111356277/184880927-cf717cfc-da1b-4f95-97ea-c8b757eab911.png">

After completing al configuration than Lets Play!


https://user-images.githubusercontent.com/111356277/184886264-d5ff9d64-5dba-471f-823d-a5cb22d93138.mp4





