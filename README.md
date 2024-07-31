# Build-VMwareBookmarks
Bookmark generator for VMware Products in your environment.

This it a basic script which generates bookmarks for all vCenters that are connected at the time of run, their respective ESXi hosts, and VMware products which utilize the 'vApp Config'.
NOTE: This script assumes you use FQDNs for your ESXi hosts, and the VMware appliances in your vcenter inventory. This script will not work if you don't use that naming format.

Currently, it can find
* vCenter
* ESXi 
* ESXi OOB Mgmt via user provided details
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
