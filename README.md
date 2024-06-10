# Active Directory Home Lab

An Active Directory Domain Services (AD DS) environment inside of VMware Workstation Pro 17.
This project starts with a Windows Server 2022 VM in which things such as basic Users, Groups, and Organisational Units (OU) are configured.

The completed project then moves on to set up a client machine and uses PowerShell scripting to configure over 1000 users.

![Starter Project Diagram](./assets/starter_project_diagram.png)

## Architecture

### Starter

The starter project runs inside VMware Workstation Pro 17. This was recently made available to be downloaded and used for [free for personal use](https://blogs.vmware.com/workstation/2024/05/vmware-workstation-pro-now-available-free-for-personal-use.html).

Windows Server 2022 is run as a virtual machine within VMware and will also be configured to have a network connection.

### Complete

Complete is a WIP.

## Initial Setup

### Prerequisites

This project uses VMware Worksation. More information can be found [here](https://www.vmware.com/products/workstation-pro/html.html).

The Windows Server 2022 ISO file can be downloaded from [here](https://www.microsoft.com/en-us/evalcenter/download-windows-server-2022).

### Configuring the Virtual Machine

Initial load of VMware should provide you with some options. Select Create New Virtual Machine.

![VMware Start Screen](./assets/vmware_start.png)

A setup wizard will appear and confirm the type of installation. Typical is the default and what will be selected.

![VMware Setup Wizard](./assets/vm_config_1.png)

Once the `.ISO` file has been selected, a prompt will ask for a product key. And some extra information.

A product key can be ommited to make use of the 180 day trial.

The version can be kept as Datacenter. This will install the data centre version and a GUI to use with the server.

A basic demo admin account is also created.

![Easy Install Information](./assets/vm_config_2.png)

## Known Issues

- Issue with Windows Server 2022 displaying desktop properly at 1920x1080 resolution inside of VMware Workstation.

## Additional Resources

Microsoft's training platform [Learn](https://learn.microsoft.com/en-us/training/) has a module focused on [AD DS](https://learn.microsoft.com/en-us/training/).
