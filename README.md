## TOC
* [Overview](#overview)
* [Client configuration](#client-configuration)


## Overview

![](https://github.com/MRLIVING/odoo/blob/master/doc/img/mrl_vpn_overview.PNG)


## Client configuration
### 1. open VPN settings window
   <img src="https://github.com/MRLIVING/odoo/blob/master/doc/img/open_vpn_settings.png" width=100 />
   <img src="https://github.com/MRLIVING/odoo/blob/master/doc/img/settings_add_a_vpn.PNG" width=100/>

### 2. add a VPN connection
   <img src="https://github.com/MRLIVING/odoo/blob/master/doc/img/add_a_vpn.PNG" width=100 />

   filling the fields with the correct information.  
   * VPN provider            `Windows`
   * Connection name         `vpn-odoo`
   * Server name or address  `xxx` (ask info)
   * VPN type                `L2TP/IPsec with pre-shared key`
   * Pre-shared key          `xxx` (ask info)
   * Type of sign-in info    `User name and password`
   * User name (optional)    `xxx` (ask info)
   * Password (optional)     `xxx` (ask info)

### 3. config VPN connection properties  
   <img src="https://github.com/MRLIVING/odoo/blob/master/doc/img/change_adapter_options.PNG" width=100 />
   <img src="https://github.com/MRLIVING/odoo/blob/master/doc/img/open_conn_properties.png" width=100 />

####   3.1 config Security  
   <img src="https://github.com/MRLIVING/odoo/blob/master/doc/img/config_conn_security.PNG" width=100 />  

   * Type of VPN     `Layer 2 Tunneling Protocol with IPsec (L2TP/IPsec)`
   * Autherication   check `Challenge Handshake Autherication Protocol (CHAP)` and `Microsoft CHAP Version 2 (MS-CHAP v2)`

####   3.2 config Networking  
   <img src="https://github.com/MRLIVING/odoo/blob/master/doc/img/open_networking_properties.PNG" width=100 />
   <img src="https://github.com/MRLIVING/odoo/blob/master/doc/img/config_conn_dns.PNG" width=100 />  

   Use the following DNS server addresses:
   * Preferred DNS server: `169.254.169.254`
   * Alternet DNS server: `168.95.1.1`

### 4. change registry  
   <img src="https://github.com/MRLIVING/odoo/blob/master/doc/img/cmd_run_as_admin.png" width=100 /> 
   <img src="https://github.com/MRLIVING/odoo/blob/master/doc/img/run_cmd_2_change_registry.png" width=300 />  

   * open `Command Prompt` with `administrator` privilege
   * run `REG ADD HKLM\SYSTEM\CurrentControlSet\Services\PolicyAgent /v AssumeUDPEncapsulationContextOnSendRule /t REG_DWORD /d 0x2 /f`

### 5. reboot system (Win 10)

### 6. open browser 
   * navigate `http://dev.mrl.com.tw` 
   * done.
     
## Troubleshooting
* windows error 809

## Reference
* [Google Cloud Platform 搭建個人VPN](https://medium.com/%E6%BE%84%E6%80%9D%E8%A8%AD%E8%A8%88-%E6%B2%88%E6%80%9D%E4%B8%96%E7%95%8C%E7%9A%84%E8%A7%A3%E6%B1%BA%E6%96%B9%E6%A1%88/google-cloud-platform-%E6%90%AD%E5%BB%BA%E5%80%8B%E4%BA%BAvpn-358ccdbeca40)
* [IPsec VPN Server Auto Setup Scripts](https://github.com/hwdsl2/setup-ipsec-vpn)
  * [Configure IPsec/L2TP VPN Clients](https://github.com/hwdsl2/setup-ipsec-vpn/blob/master/docs/clients.md)
* [IPsec VPN Server on Docker](https://github.com/hwdsl2/docker-ipsec-vpn-server)
* [Libreswan](https://github.com/libreswan/libreswan)
  * [ipsec man](https://libreswan.org/man/)
  * [How to read status output](https://libreswan.org/wiki/How_to_read_status_output)
* [SoftEther VPN Project](https://www.softether.org/)
  * [softether download center](http://www.softether-download.com/en.aspx?product=softether)
  * [How to Setup a Multi-Protocol VPN Server Using SoftEther](https://www.digitalocean.com/community/tutorials/how-to-setup-a-multi-protocol-vpn-server-using-softether)
* [Building High-throughput VPNs between VPCs in GCP](https://cloud.google.com/solutions/building-high-throughput-vpns#top_of_page)
  * [Connecting to your network with Google Cloud VPN | 9.27.18 | Linux Academy](https://www.youtube.com/watch?v=Uhws3bXR7sc)
    * VPC to VPC with cloud VPN
    * VPC subnet and cloud route
    * BGP
* [GCP Network](https://www.youtube.com/playlist?list=PLIivdWyY5sqJ0oXcnZYqOnuNRsLF9H48u)
  * [169.254.169.254 - VPC default internal name server](https://cloud.google.com/dns/docs/overview#vpc-name-resolution-order)
