<h1 align="center"> Cấu Hình Mạng Máy Tính - Cisco Packet Tracer <br/></h1>

<p align="center">
  <img width="90%" src="https://user-images.githubusercontent.com/91842746/196658865-aabe823f-5994-4b96-a9e8-af97098d9a7a.png" /></a>
</p>


# [**Table Of Content**](#table-of-content)
- [**Table Of Content**](#table-of-content)
- [**Introduction**](#introduction)
- [**Overview**](#overview)
- [**Content**](#content)
- [**Official Exam**](#official-exam)
- [**Document**](#document)
- [**Post Script**](#post-script)
- [**Our Team**](#our-team)
- [**Made with 💘 and Vietnamese <img src="https://cdn.britannica.com/41/4041-004-D051B135/Flag-Vietnam.jpg" width="30">**](#made-with--and-vietnamese-)

##

# [**Đề Bài**]
A. Scenarior: Implement network for Company BKACAD with 2 SITEs connect to the INTERNET. The company uses both IPv4 and IPv6 for the network, detail as follow:

- SITE1-LAN2 use only IPv4 address.
- SITE1-LAN1 use both IPv4 and IPv6 address (dual stack).
- Wan link use both IPv4 and IPv6 address (dual stack).
- SITE2-LAN3 use only IPv6 address
- Note: DNSv4 assign only IPv4 address, and DNSv6 assign only IPv6 address.

B. The tasks are performed by following parameters:
1. IP Address planning:
<p align="center">
  <img width="80%" src="https://user-images.githubusercontent.com/91842746/196716380-d0941424-d210-4cec-b1af-edd0dc933fc7.png" /></a>
</p>
 
2.Assign IP address, subnet mask, default gateway to the networking devices.
a. All routers and server are assigned IP address manually as following rule:
- Router interface : +1
- DHCP : +2
- WEB,MAIL : +3
- DNS: +4
- TFTP : +5, PC1 : +11, PC2 : +12; PC3 : +13; PC4 : +14
- Note:  PC5, PC6, PC7, PC8 : assigned IP address by DHCP server.

Ex: In the subnetwork: 192.168.1.128/25. (there are DHCP, PC5)
Router's interface : 192.168.1.129   (128+1).
DHCP server :192.168.1.130           (128+2).
PC4 client : 192.168.1.142           (128+14)
 

3.Basic router configuration:
- Overall requirements: all network segments in the network diagram can connect to each other (example: ping and tranceroute work for to reach all devices and PCs); users can telnet to get access to router CLI.

a) Router name, MOTD banner and descriptions
<p align="center">
  <img width="80%" src="https://user-images.githubusercontent.com/91842746/196717390-173ffddc-5a43-44bb-9d9e-fe446c5f1c7f.png" /></a>
</p>

b) Password:
+ The console are protected by clear text password (Unencrypted), password= cisco@console”
+ All VTY lines (0 – 4) are protected by clear text password (Unencrypted), password= ”cisco@vty”
+ Set the secret password to enter privileged mode, password= “cisco@enable”.

4.Configuring the SERVERS:

a. DHCP server:

### DHCP for LAN2 :
- PoolName: serverPool
- Start IP address: +10.
- Maximum number of user: 100

### DHCP for LAN 4 :
- PoolName: serverPool
- Start IP address: +50
- Maximum number of user: 150


b. Enable TFTP server. Backup routers’ configuration with the file name: R1-confg, R2-confg.

c. MAIL:
   ### Mail server:
   + Domain name: bkacad.com.
   + Add username/password: pc1/cisco and pc3/cisco
   + PC1 Mail client:

  ### Name: PC1
  + Mail address: pc1@bkacad.com
  + Incoming and outgoing mail server: bkacad.com
  + User pc1, pass cisco

  ### PC3 Mail client:
  + Name: PC3
  + Mail address: pc3@bkacad.com
  + Incoming and outgoing mail server:bkacad.com
  + User pc3, pass cisco

5.Test.
- From PCs, check connectivity with web server bkacad.com;cisco.com

- From PC1, Note: send mail from PC1 to PC3 and check the result.

##

# [**Bài Làm**]

# [**CHIA IPV4 theo Host**](#Chia-ipv4)
<p align="center">
  <img width="60%" src="https://user-images.githubusercontent.com/91842746/196668952-6abbfd06-fee1-4898-80fb-3e2bec5e51a7.png" /></a>
</p>

<p align="center">
  <img width="80%" src="https://user-images.githubusercontent.com/91842746/196666290-dc8e56fe-dbdc-4f0f-a5a0-348571178a9d.png" /></a>
</p>


# [**CẤU HÌNH ROUTER**](#router)
<h3 align="center">
  ## Router 1
</h3>
<p align="center">
  <img width="80%" src="https://user-images.githubusercontent.com/91842746/196725873-5572473d-9909-43c7-9a75-01a72e86a062.png" /></a>
</p>
<p align="center">
  <img width="80%" src="https://user-images.githubusercontent.com/91842746/196725913-0415e7e8-9c8b-4148-9e43-7452a8f2d0e6.png" /></a>
</p>


<h3 align="center">
  ## Router 2
</h3>
<p align="center">
  <img width="80%" src="https://user-images.githubusercontent.com/91842746/196725922-794aadb9-eb73-4aaa-8f08-4ef2c417ddba.png" /></a>
</p>
<p align="center">
  <img width="80%" src="https://user-images.githubusercontent.com/91842746/196725953-9dcf98ff-8c80-4d04-8659-62be331a21bd.png" /></a>
</p>


<h3 align="center">
  ## SeverPT - DHCP SITE 2
</h3>
</p>
<p align="center">
  <img width="80%" src="https://user-images.githubusercontent.com/91842746/196727565-4ef53fb5-a33e-4c14-88fe-73faef34ed5b.png" /></a>
</p>
</p>
<p align="center">
  <img width="80%" src="https://user-images.githubusercontent.com/91842746/196727586-8cb810f0-4ed0-4db3-b3f1-9189228eb51a.png" /></a>
</p>


<h3 align="center">
  ## SeverPT - DHCP SITE 2
</h3>
</p>
<p align="center">
  <img width="80%" src="https://user-images.githubusercontent.com/91842746/196731384-2372be16-262d-4533-a656-c7c8f0dcfbbc.png" /></a>
</p>
</p>
<p align="center">
  <img width="80%" src="https://user-images.githubusercontent.com/91842746/196731414-1a66ed4b-c5ce-4bb1-99b8-137c13d34eee.png" /></a>
</p>


<h3 align="center">
  ## Sever Fa0/4 - TFTP
</h3>
<p align="center">
  <img width="80%" src="https://user-images.githubusercontent.com/91842746/196730137-d5db2645-1d33-4be5-83c5-358482ecf55d.png" /></a>
</p>
<p align="center">
  <img width="80%" src="https://user-images.githubusercontent.com/91842746/196730615-50f29f4b-5794-4ec8-8e52-a0113b44e5d5.png" /></a>
</p>


<h3 align="center">
  ## PC-PT PC1
</h3>
<p align="center">
  <img width="80%" src="https://user-images.githubusercontent.com/91842746/196732141-650b3910-f95e-40f8-9f01-31279c38eded.png" /></a>
</p>


<h3 align="center">
  ## PC-PT PC2
</h3>
<p align="center">
  <img width="80%" src="https://user-images.githubusercontent.com/91842746/196732577-bc87b02f-118a-4b94-8cd1-e4c36a863321.png" /></a>
</p>


<h3 align="center">
  ## Sever PT - bkacad.com
</h3>
<p align="center">
  <img width="80%" src="https://user-images.githubusercontent.com/91842746/196736839-bb06d84b-675c-477a-b9d2-d7756ad09ab7.png" /></a>
</p>
<p align="center">
  <img width="80%" src="https://user-images.githubusercontent.com/91842746/196736844-11c83d36-4df3-46c9-a588-e2e96bf11759.png" /></a>
</p>


<h3 align="center">
  ## Sever PT - bkacad.com
</h3>
<p align="center">
  <img width="80%" src="https://user-images.githubusercontent.com/91842746/196736839-bb06d84b-675c-477a-b9d2-d7756ad09ab7.png" /></a>
</p>
<p align="center">
  <img width="80%" src="https://user-images.githubusercontent.com/91842746/196736844-11c83d36-4df3-46c9-a588-e2e96bf11759.png" /></a>
</p>


<h3 align="center">
  ## Sever PT - DNS IPv4
</h3>
<p align="center">
  <img width="80%" src="https://user-images.githubusercontent.com/91842746/196737530-1819565d-98cd-4ca5-b035-d50048b076b1.png" /></a>
</p>
<p align="center">
  <img width="80%" src="https://user-images.githubusercontent.com/91842746/196737544-43621f41-4f04-4b92-93b5-e088af5acad6.png" /></a>
</p>



<h3 align="center">
  ## Sever PT - DNS IPv6
</h3>
<p align="center">
  <img width="80%" src="https://user-images.githubusercontent.com/91842746/196737598-a1acd63b-bb34-4d4d-a190-115ae07b8c3c.png" /></a>
</p>
<p align="center">
  <img width="80%" src="https://user-images.githubusercontent.com/91842746/196737623-04acb512-a3e5-4a2d-a9b3-11482d5d1291.png" /></a>
</p>


