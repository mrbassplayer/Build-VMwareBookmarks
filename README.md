# Build-VMwareBookmarks
Bookmark generator for VMware Products in your environment.

This it a basic script which generates bookmarks for all vCenters that are connected at the time of run, their respective ESXi hosts, and VMware products which utilize the 'vApp Config'.
NOTE: This script assumes you use FQDNs for your ESXi hosts, and the VMware appliances in your vcenter inventory. This script will not work if you don't use that naming format.

Currently, it can find
* vCenter
* ESXi 
* ESXi OOB Mgmt via user provided details
* Identity Manager
* VMware Aria Operations for Networks Platform
* VMware Aria Suite Lifecycle Appliance
* VMware HCX
* VMware NSX
* VMware Site Recovery Manager Appliance
* VMware Skyline Appliance
* VMware vCenter Log Insight
* vRealize Automation
* vRealize Operations Appliance
* vSphere Replication Manager Appliance and supporting Replication Servers
Feel free to add missing products. I've tried to get a list from VMware, but haven't had any luck there.

For the ESXi hosts, it will organize the bookmarks by the vCenter they are managed by, then by the cluster they are in. 

To use, first connect to all the vcenters you have in your environment, using their FQDN.
Then, run the script.
It will ask you for the domain name of your environment.
It will then ask you for the modifier in the FQDN for the out of band management. (e.g. iDrac, iLO, IPMI).
Lastly, it will ask for the path to where it should save the bookmarks file.

Here is a screenshot of all the bookmarks created for non-ESXi appliances. Inside each of these folders are the FQDNs of each appliance found for that respective product.

<img width="374" alt="SCR-20240805-oega" src="https://github.com/user-attachments/assets/c15b664f-3dc9-4355-99d4-5d38be149e74">

Here is a screenhost of the bookmarks for the ESXi Client and iDrac/iLo/IPMI/etc. 

<img width="251" alt="SCR-20240805-offt" src="https://github.com/user-attachments/assets/05b4b360-acdc-487d-b6d9-db09b115546b">

Here is a bulleted list of how those ESXi bookmarks breakdown
* ESXi Hosts
   * ESXi Client
      * vCenter
         * Cluster A
            * ESXi Host FQDN 1
            * ESXi Host FQDN 2
            * ESXi Host FQDN 3
         * Cluster B
            * ESXi Host FQDN 4
            * ESXi Host FQDN 5
            * ESXi Host FQDN 6
   * ESXi iDrac / iLO / IPMI
      * vCenter
         * Cluster A
            * ESXi Host iDrac / iLO / IPMI FQDN 1
            * ESXi Host iDrac / iLO / IPMI FQDN 2
            * ESXi Host iDrac / iLO / IPMI FQDN 3
         * Cluster B
            * ESXi Host iDrac / iLO / IPMI FQDN 4
            * ESXi Host iDrac / iLO / IPMI FQDN 5
            * ESXi Host iDrac / iLO / IPMI FQDN 6
