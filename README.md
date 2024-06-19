# Active Directory Home Lab

This is a homelab project of an Active Directory Domain Services (AD DS) environment inside of VMware Workstation Pro 17.
This project starts with a Windows Server 2022 VM with AD DS installed in which things such as basic Users, Groups, and Organisational Units (OU) are configured.

<!-- The completed project then moves on to set up a client machine and uses PowerShell scripts to configure over 1000 users. -->

![Starter Project Diagram](./assets/starter_project_diagram.png)

## Architecture

### Starter

The starter project runs inside VMware Workstation Pro 17. This was recently made available to be downloaded and used for [free for personal use](https://blogs.vmware.com/workstation/2024/05/vmware-workstation-pro-now-available-free-for-personal-use.html).

Windows Server 2022 is run as a virtual machine within VMware and will also be configured to have a network connection.

Starter is a WIP.

<!-- ### Complete

Complete is a WIP. -->

## Initial VMware Setup

### Prerequisites

This project uses VMware Worksation. More information can be found [here](https://www.vmware.com/products/workstation-pro/html.html).

The Windows Server 2022 ISO file can be downloaded from [here](https://www.microsoft.com/en-us/evalcenter/download-windows-server-2022).

### Configuring the Virtual Machine

Load VMware and select `Create New Virtual Machine`.

![VMware Start Screen](./assets/vmware_start.png)

Select the default (typical) from the setup wizard.

![VMware Setup Wizard](./assets/vm_config_1.png)

Once the `.ISO` file has been selected, a prompt will ask for a product key. A product key can be ommited to make use of the 180 day trial.

Keep the version as Datacenter to install the data centre version of Windows Server 2022.

Accept and create a local administrator account.

![Easy Install Information](./assets/vm_config_2.png)

Continue to follow the prompts on the screen and make sure to select the Datacenter Evaluation (Desktop Experience) to install a desktop environment.

![Installing the correct server experience](./assets/vm_config_3.png)

Follow the remaining prompts and restart the system once the install has finished to reach the desktop. Accept the network connection so the VM can access the internet.

![Initial boot](./assets/vm_config_4.png)

After the initial boot, it is good practice to fully update the system to receive the latest features and security patches. Once installed, restart and the system should be ready.

![Updating system post install](./assets/vm_config_5.png)

From here, create a VMware snapshot to revert back to if any errors are made.

### Renaming Network Interface

This will be helpful in the future when expanding the project to identify different NIC's.

Select the `Network Internet Access` from the dashboard on the bottom right hand side of the Windows Taskbar and enter the `Network and Internet Settings` menu.

![Network Internet Access Menu](./assets/network_internet_access.png)

Select `Change Adapter Options` to view all NIC's.

On the Ethernet NIC, `Right Click > Rename` and name it something distinct to make it easy to identify.

![Renaming NIC](./assets/rename_nic.png)

## Starter Project

### Installing Active Directory Domain Services

Within the server manager dashboard, select `Add roles and features` to start installing active directory.

![Server Manager Dashboard](./assets/server_manager_dashboard.png)

Select `Role-based or feature-based installation > Select a server from the server pool (and select the PC currently in use)` and ensure the checkbox for `Active Directory Domain Services` is selected.

![Installing Active Directory](./assets/installing_ad.png)

Continue to select the defaults and complete the installation. Successful installation is pictured below.

![Successful AD Install](./assets/successful_ad_install.png)

### Domain Controller and AD Forest Configuration

From here, the server needs to be promoted to a domain controller. Open the notification flag in the top right hand side of the toolbar and select `Promote this server to a domain controller`.

![Promote to domain controller notification](./assets/post_install_notification.png)

From here a new `Forest` can be created. A `Forest` is the top-level container that holds one or more AD domains. A root domain name should be specified. Sub-domains can be configured later.

![Adding a new forest](./assets/add_new_forest.png)

![Set a password for the forest](./assets/forest_password.png)

![Forest NetBIOS name](./assets/netbios.png)

After a reboot, the login screen should display a prompt for the newly created domain.

![Logging into the new domain](./assets/forest_login.png)

### Configuring Organisational Units, Users and Groups

## Known Issues

- Issue with Windows Server 2022 displaying desktop properly at 1920x1080 resolution inside of VMware Workstation.

## Additional Resources

- Microsoft's training platform [Learn](https://learn.microsoft.com/en-us/training/) has a module focused on [AD DS](https://learn.microsoft.com/en-us/training/).

- Jon Good [Windows Server with VMware](https://youtu.be/II-a79HFQtQ?si=WNRtZwhiH6w9uKkJ)
