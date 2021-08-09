## TOC
* [Overview](#overview)
* [SoftEther Client setup](#softether-client-setup)
* [Reference](#reference)

## Overview

![](https://github.com/MRLIVING/vpn/blob/master/doc/img/mrl_network_overview.PNG)


##  SoftEther Client setup
### 1. download [SoftEther VPN Client](http://www.softether-download.com/en.aspx?product=softether)
<img src="https://github.com/MRLIVING/vpn/blob/master/doc/img/se_vpn_client_download.PNG" width="200" />

### 2. install VPN Client and new a Virtual Network Adapter
#### 2.1 install VPN Client
<img src="https://github.com/MRLIVING/vpn/blob/master/doc/img/se_vpn_client_install1.PNG" width="200" /> <img src="https://github.com/MRLIVING/vpn/blob/master/doc/img/se_vpn_client_install2.PNG" width="200" /> <img src="https://github.com/MRLIVING/vpn/blob/master/doc/img/se_vpn_client_install3.PNG" width="200" /> 

### 2.2 new a Virtual Network Adapter
<img src="https://github.com/MRLIVING/vpn/blob/master/doc/img/se_vpn_client_install4.PNG" width="200" /> <img src="https://github.com/MRLIVING/vpn/blob/master/doc/img/se_vpn_client_install5.PNG" width="200" />


### 3. config VPN connection properties  
#### 3.1 open VPN Client and new a connection
#### 3.2 config properties
* Host Name: `xxx` (ask info)
* Virtual Hub Name: `vpc-erp`
* User Name: `xxx` (ask info)
* Password: `xxx` (ask info)

<img src="https://github.com/MRLIVING/vpn/blob/master/doc/img/se_client_new_conn.PNG" width="200" />

### 4. connect to VPN server
<img src="https://github.com/MRLIVING/vpn/blob/master/doc/img/se_vpn_client_connect.PNG" width="200" />
<img src="https://github.com/MRLIVING/vpn/blob/master/doc/img/se_vpn_client_connect_ok.PNG" width="200" />

### 5. browser a server page to verify the VPN connection 
   * navigate `https://10.1.0.5:5555/` 
   * congratulations, VPN setup is done.
   
<img src="https://github.com/MRLIVING/vpn/blob/master/doc/img/se_vpn_server_page.PNG" width="200" />

### 6. Optional, RDP to SAP B1 server (please skip this step if you would prefer to use local SAP B1 client)
* host/IP:  `xxx` (ask info)
* account:  `xxx` (the predix of your email account before `@`)
* password: `xxx` (ask info)


##  SoftEther Server setup
TODO...

### Create A Virtual Hub
`HubCreate ${HubName}`

### Create a user
`UserCreate ${UserName}`

`UserPasswordSet ${UserName}`



## Reference
* [SoftEther VPN Project](https://www.softether.org/)
  * [How to Setup a Multi-Protocol VPN Server Using SoftEther](https://www.digitalocean.com/community/tutorials/how-to-setup-a-multi-protocol-vpn-server-using-softether)
  * [softether download center](http://www.softether-download.com/en.aspx?product=softether)
  * [How to install and configure SoftEther VPN on Windows](https://proprivacy.com/open-source/guides/install-configure-softether-vpn-device) 
* [Building High-throughput VPNs between VPCs in GCP](https://cloud.google.com/solutions/building-high-throughput-vpns#top_of_page)
  * [Connecting to your network with Google Cloud VPN | 9.27.18 | Linux Academy](https://www.youtube.com/watch?v=Uhws3bXR7sc)
    * VPC to VPC with cloud VPN
    * VPC subnet and cloud route
    * BGP
* [GCP Network](https://www.youtube.com/playlist?list=PLIivdWyY5sqJ0oXcnZYqOnuNRsLF9H48u)
  * [Cloud DNS - VPC internal name server](https://cloud.google.com/dns/docs/overview#vpc-name-resolution-order)
