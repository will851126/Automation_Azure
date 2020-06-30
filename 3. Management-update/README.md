# Enable Update Management on multiple VMs


## Overview
Use [Update Management](https://docs.microsoft.com/en-us/azure/automation/automation-update-management)  in Azure Automation to manage operating system updates for your Windows and Linux machines in Azure, in on-premises environments, and in other cloud environments. You can quickly assess the status of available updates on all agent machines and manage the process of installing required updates for servers

## Scenario

Azure Automation provides solutions to manage operating system security updates, track changes, and inventory what is installed on your computers


## Prerequisites

1. Already create Log analytice workspaces in **East US** location

2. Aleardy create Automation accounts in **East US 2** location

## Step by step 

### Enable solutions

1. Navigate to your Automation account and select **Inventory** under Configuration Management.

<p style="text-align:center;">
    <img src="images/001.png" width="30%" />
</p>

2. Choose the **Log Analytics workspace** and **Automation account** and click **Enable** to enable the solution

<p style="text-align:center;">
    <img src="images/002.png" width="50%" />
</p>

### Enable update management solution

1. Navigate to your Automation account and select **Update Management** under Update Management

<p style="text-align:center;">
    <img src="images/004.png" width="30%" />
</p>

2. Choose the **Log Analytics workspace** and **Automation account** and click Enable to enable the solution

<p style="text-align:center;">
    <img src="images/003.png" width="50%" />
</p>

### Onboard Azure VMs

 1.Select **Update management** under Update management
 <p style="text-align:center;">
    <img src="images/004.png" width="30%" />
</p>

 2. Click **Add Azure VMs**, select one or more VMs from the list

<p style="text-align:center;">
    <img src="images/005.png" width="80%" />
</p>


3. On the Enable Update Management page, **click Enable**


<p style="text-align:center;">
    <img src="images/006.png" width="50%" />
</p>


4. Select **Manage machines**

<p style="text-align:center;">
    <img src="images/007.png" width="80%" />
</p>

* Select **All available machines** and click **Enable**

<p style="text-align:center;">
    <img src="images/008.png" width="50%" />
</p>

### View computers attached to Automation account

After you enable Update Management for your machines, you can view machine information by selecting Computers

list of possible values for compliance state: 

* `Compliant`: Computers that are not missing critical or security update

* `Non-compliant`: Computers that are missing at least one critical or security update

* `Not assessed`: The update assessment data hasn't been received from the computer within the expected timeframe

<p style="text-align:center;">
    <img src="images/010.png" width="80%" />
</p>


### Schedule an update deployment

 To schedule a new update deployment for one or more virtual machines

1. Under Update management, select **Schedule update deployment**

<p style="text-align:center;">
    <img src="images/009.png" width="80%" />
</p>

2. In the New update deployment pane, specify the following information:

<p style="text-align:center;">
    <img src="images/011.png" width="30%" />
</p>

* `Name`: Enter your unique name  

* `Operating system`: Select **Linux**

* `Groups to update` : Select your resource , and click **Add** and **OK**

<p style="text-align:center;">
    <img src="images/012.png" width="80%" />
</p>

* `Machine to update` : Choose **Machines**, the readiness of the machine is shown in the Update agent readiness column,Click **OK**

<p style="text-align:center;">
    <img src="images/013.png" width="80%" />
</p>


* `Schedule settings`: Accept the default date and time, which is **30** minutes after the current time

* `Recurrence`: Select Recurring

    * `Recur`: **1 Day**
    * Click **OK**

<p style="text-align:center;">
    <img src="images/014.png" width="30%" />
</p>

* Click **Create**

<p style="text-align:center;">
    <img src="images/015.png" width="30%" />
</p>

### View results of an update deployment

After the scheduled deployment starts, you can see the status for that deployment on the Update deployments tab under Update management

<p style="text-align:center;">
    <img src="images/016.png" width="80%" />
</p>

1. If the deployment is currently running, its status is In progress. After the deployment finishes successfully, the status changes to **Succeeded**

<p style="text-align:center;">
    <img src="images/017.png" width="90%" />
</p>


2.  Click **Name** and view for result detail 

<p style="text-align:center;">
    <img src="images/018.png" width="90%" />
</p>

3. Form your Automation account ,under Process Automation, Select **Job**

<p style="text-align:center;">
    <img src="images/019.png" width="30%" />
</p>


4. Click runbook job

<p style="text-align:center;">
    <img src="images/020.png" width="80%" />
</p>

5. Click **All Logs**, view patch update log


<p style="text-align:center;">
    <img src="images/021.png" width="80%" />
</p>


## Conclusion

1. Assess compliance of virtual machines in Azure

2. Patch updates on both Windows and Linux VMs

3. Schedule reoccurring patching

