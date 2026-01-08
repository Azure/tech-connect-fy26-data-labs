<!-- # TAP Generation for Staging Only

Select 'Generate TAP' button below to generate a new TAP:

@lab.Activity(Automated2)

TAP: +++@lab.Variable(tap)+++

> [!note] TAP will only display above. It will NOT display on the Resources tab or elsewhere

> [!knowledge] You should see a green checkmark once the TAP has generated. If it does not display next to "TAP:", refresh your Monitor page.

#Staging Steps

1. [] Open **Microsoft Edge** on the desktop and connect to +++https://portal.azure.com/?createprojectwithregion=true+++.

1. [] Log in using +++@lab.CloudPortalCredential(User1).Username+++ with +++@lab.CloudPortalCredential(User1).AccessToken+++.

	>[!Note] When asked to save your password, select **Not now**. When asked to stay signed in, select **no**.

1. [] Select **Resource Groups**

1. [] Select the **AZMigrateRG** resource group.

1. [] **Expand essentials** and look at deployments on the right. If you see any failures, exit the lab by selecting exit lab in the top corner and then selecting **End Lab**. if no failures you can continue even if it still says deploying, as long as there are no failures, you are good.

    !IMAGE[yjcdzvvr.jpg](instructions315313/yjcdzvvr.jpg)

1. [] In the Azure search box at the top, search for and then select +++Azure Migrate+++.

1. [] Select **Create project**.

	!IMAGE[msrgssym.jpg](instructions315313/msrgssym.jpg)

1. [] On the Create project page, select the following options.
        
    | Object | Value |
    | -------- | -------- |
    | Resource Group | **AZMigrateRG** |
    | Project Name | +++az-migrate-project-@lab.LabInstance.Id+++ |
    | Geography | **@lab.Variable(Reigon)** |

1. [] Select **Create**.

	>[!Note] When the deployment completes, you will be taken back to the Get Started page below.
    !IMAGE[8a2ngjws.jpg](instructions315313/8a2ngjws.jpg)

1. [] On the left menu, select **All Projects**.

1. [] Select the **az-migrate-project-@lab.LabInstance.Id** (not the checkbox, the project name).

1. [] On the project page, select **Start discovery**, and then select **Using Appliance** and **For Azure**.

	!IMAGE[acj8e7v8.jpg](instructions315313/acj8e7v8.jpg)

1. [] On the Discover page, select the following options.

    | Object | Value |
    | -------- | -------- |
    | Select type of virtualization | **Yes, with VMware vSphere Hypervisor** |
    | Name your appliance | +++app@lab.LabInstance.Id+++ |

1. [] Select **Generate key**. Then wait until the key appears below. This will take about **2 minutes**.

1. [] Once the key appears, select the **Copy to clipboard** icon on the right side of the key.

	!IMAGE[jtdy9hjb.jpg](instructions315313/jtdy9hjb.jpg)

1. [] Minimize the web browser.
	
    !IMAGE[v6czlxsw.jpg](instructions315313/v6czlxsw.jpg)

1. [] On the desktop, double-click the Azure Migrate Appliance icon.

	!IMAGE[s3ojdfu4.jpg](instructions315313/s3ojdfu4.jpg)

1. [] It may take a minute or two for the page to load. If you get a warning that it is taking too long, select **Wait**.

1. [] When the page appears, select **Register VMware appliance by pasting the key here**, and then paste the key using **Ctrl+V**.

1. [] Select **Verify**.

	!IMAGE[wr4upu71.jpg](instructions315313/wr4upu71.jpg)

    >[!Alert] If you don't see the green circle with the check in it or receive any kind of error, select **Verify** again.

1. [] Under Azure user login and appliance registration status, select **Login**.

1. [] On the pop-up, select **Copy code & Login**.

	!IMAGE[ioecvdxl.jpg](instructions315313/ioecvdxl.jpg)

1. [] On the pop-up, enter the code using **Ctrl+V**, and then select **Next**.

1. [] On the Pick an account pop-up, select the **User1** account, and then select **Continue**.

1. [] When you see the message that you have signed into MS Azure PowerShell, close the browser tab.

	!IMAGE[daz4208o.jpg](instructions315313/daz4208o.jpg)

    >[!Alert] This will take about 10 minutes to complete.

1. [] When complete, you should see:

	!IMAGE[x2sq7fq4.jpg](instructions315313/x2sq7fq4.jpg)

1. [] You will see a red X next to **Check if VMware Virtual Disk Development Kit is installed**. This is normal. Select the **Verify** button below, and it should turn green.

	!IMAGE[13q7ezyb.jpg](instructions315313/13q7ezyb.jpg)

1. [] Under Provide vCenter Server credentials for discovery of VMware VMs, select **Add credentials** and add credentials with the following settings.

    | Setting       | Value                                                 |
    | :------------ | :---------------------------------------------------- |
    | Friendly Name | +++VMware+++                                          |
    | User Name     | +++administrator@vsphere.local+++                     |
    | Password      | +++Passw0rd!+++                                       |

1. [] Select **Save**.

1. [] Under Provide vCenter Server details, select **Add discovery source**, and then for the IP Address/FQDN, enter +++vcenter01.contoso.com+++.

1. [] Select **Save** (if you are prompted to save your password select **Not now**). 

1. [] Verify that **Validation successful** is displayed under the Status.

	!IMAGE[ptvv1y3m.jpg](instructions315313/ptvv1y3m.jpg)

1. [] Under Provide server credentials to perform guest discovery of installed software, dependencies and workloads, ensure that the slider is **enabled**, then scroll down and select **Add credentials** with the following settings.

    | Setting          | Value                        |
    | :--------------- | :--------------------------- |
    | Credentials type | **Windows (Non-domain)**     |
    | Friendly Name    | +++WinUser+++                |
    | User Name        | +++Administrator+++          |
    | Password         | +++Passw0rd!+++              |
    | **Add more **    |                              |
    | Credentials type | **SQL Server Authentication** |
    | Friendly Name    | +++SQLUser+++                |
    | User Name        | +++workshopServiceAcc+++     |
    | Password         | +++Password~1+++             |

1. [] Select **Save**. (If you are prompted to save your password select **Not now**.) 

	>[!Note] You should see the following.
    !IMAGE[87r5miqr.jpg](instructions315313/87r5miqr.jpg)

1. [] Select **Start discovery**.

>[!alert] Wait until the start discovery button starts a spinning wheel. It should only be a few seconds.



1. [] Leave the browser open in the lab. 

1. [] Make sure the instructions are displaying the Windows Cloud Migration Workshop page.

1. [] Close your local browser tab that the lab is in to disconnect from the lab


#STAGING TEAM STOP HERE!!!

 -->
# Windows Cloud Migration Workshop

### Azure Migrate provides the following features:

- **Unified migration platform**: You use a single portal to start, run, and track your migration to Azure. The unified platform supports discovery, assessment, and migration of variety of workloads, like servers, databases, and web applications.

- **Free service**: Azure Migrate is a free service that you can use to:
    - Identify your inventory of workloads.
    - Assess workloads for multiple infrastructure as a service (IaaS) and platform as a service (PaaS) Azure targets.
    - Develop a plan for migration.
    - Migrate the workloads by using in-product, Microsoft, and partner migration tools. (Partner tools might charge you for using their services.)
    - **Assessment, migration, and modernization**: In the Azure Migrate hub, you can assess, migrate, and modernize:
        - **Servers**
        - **Databases**
        - **Web applications**
        - **Data**

## Objectives

#### After completing this workshop, you will be able to:

- Map dependencies, create applications and analyse inventory
- Build a Business Case and review TCO, YoY cashflow, AHB/ESU, Sustainability; adjust assumptions.
- Assess migration and modernization by comparing PaaS vs VM paths.
- Plan waves & prepare targets by creating a migration wave.
- Modernize (replatform) by moving DBs to SQL MI and the .NET app to App Service via ASMA.
- Execute & validate by replicating/cutover VMs, finalizing networking, and verify the app on Azure.

## Lab Staging

In a real-world migration scenario, several preparatory steps are required before performing assessments or migrations.
To save time in this lab environment, these steps have already been completed for you.

**The following setup tasks have been pre-configured:
**
- **You've already logged in to the Azure portal and created an Azure Migrate project.**

- **The Azure Migrate appliance has been installed and configured.**

- **vCenter, guest operating system, and database credentials have been added to the appliance.**

- **A discovery scan of the environment has already been performed.**

You'll begin this lab from the point where these initial configurations are complete.

===
# Exercise 1: Validate the lab environment

This exercise guides you through **Validate the lab environment**, clarifying the purpose, expected outcome, and where to focus so you avoid common pitfalls.
In this exercise, you'll verify that the on-premises application is reachable and confirm that Azure Migrate discovered the expected assets.

##Task 1: Confirm onsite application functionality

In this task, you'll **Confirm onsite application functionality**, with concise, ordered steps to complete it efficiently.

Validate that the on-premises web application endpoints are accessible before any migration activity.

1. [] Using **Microsoft Edge**, connect to +++http://gadgetcart+++.

1. [] You should see the Parts Unlimited website.

	!IMAGE[xuywc6gd.jpg](instructions315313/xuywc6gd.jpg)

	>[!Note] This site is hosted on the GadgetCart server, which is running Windows Server 2016. This server is hosting the website and the SQL database.

1. [] Using **Microsoft Edge**, connect to +++http://partunlimited-websrv+++.

1. [] You should see the Parts Unlimited website.

	!IMAGE[xuywc6gd.jpg](instructions315313/xuywc6gd.jpg)

	>[!Note] In this version there are two separate Windows servers, both of which are running Windows Server 2022. The partunlimited-sqlsrv server is hosting the SQL database, and the partunlimited-websrv is hosting the website.

##Task 2: Review the discovered inventory

In this task, you'll **Review the discovered inventory**, with concise, ordered steps to complete it efficiently.

Confirm that Azure Migrate discovery completed and that the expected servers, databases, and web apps appear.

1. [] Open a new browser tab and connect to +++portal.azure.com+++.

1. [] Log in. Use the following credentials: +++@lab.CloudPortalCredential(User1).Username+++ with +++@lab.CloudPortalCredential(User1).AccessToken+++.

1. [] In the Azure search box at the top, search for and then select +++Azure Migrate+++.

1. [] In the left menu, select **All projects**.

1. [] Select **az-migrate-project-@lab.LabInstance.Id**.

1. [] In the left menu, expand **Explore Inventory**, and then select **All inventory**.

    >[!Note] You should see that three servers have been discovered. Note that they are running various versions of Windows.

1. [] On the left menu, select **Databases**.

	>[!Note] You should see that two SQL databases have been discovered.

1. [] On the left menu, select **Web apps**.

	>[!Note] You should see that two web apps have been discovered.

===
# Exercise 2: Define an Application

1. [] In the left menu, select the **Overview** tab.

1. [] On the All inventory tile, select the **Define application** drop-down, and then select **New application**.

	!IMAGE[cp65pjb1.jpg](instructions315313/cp65pjb1.jpg)

1. [] For the Name, enter +++PartsUnlimited-@lab.LabInstance.Id+++.

1. [] For the Type, select **Custom**, and then select **Next**.

1. [] Select **Link workloads**.

1. [] Select **both partsunlimited workloads** along with their **webapp and SQL database**, and then select **Add**.

1. [] Select **Next**.

1. [] In the Properties page, enter the following.

    | Object | Value |
    | -------- | -------- |
    | Business criticality | **High** |
    | Complexity | **Low** |

1. [] Select **Review + Create**, and then select **Create**.

1. [] Refresh the overview pages using the **Refresh** option in the top right, until you see **1** application on the All inventory tile.

    !IMAGE[xtk6i62p.jpg](instructions315313/xtk6i62p.jpg)
===
# Exercise 3: Create a Business Case

This exercise guides you through **Create a Business Case**, clarifying the purpose, expected outcome, and where to focus so you avoid common pitfalls.

## Task 1: Create and review a business case

In this task, you'll **Create and review a business case**, with concise, ordered steps to complete it efficiently.

1. [] On the Business case tile, select **Build business cases**.

    !IMAGE[aj3r1yup.jpg](instructions315313/aj3r1yup.jpg)

1. [] In the **Build business case** blade, use the following values to create the business case.

    | Setting                       | Value                                             |
    | ----------------------------- | ------------------------------------------------- |
    | Business case name            | +++bc-@lab.LabInstance.Id+++  |
	| Scope of business case        | **Entire datacenter**                             |

1. [] Select **Next**.

    | Setting                       | Value                                             |
    | ----------------------------- | ------------------------------------------------- |
    | Target location               | **@lab.CloudResourceGroup(AZMigrateRG).Location** |
    | Migration preference          | **Modernize**                                     |
    | Savings options               | **Reserved Instance + Azure Savings Plan**        |
    | Discount (%) on Pay as you go | **0**                                             |

1. [] Select **Build business case**.

1. [] On the left menu, expand **Decide and plan**, and then select **Business cases**.

    >[!Note] The business case will take approximately 10 minutes to complete. You must wait for the business to generate. Review the business case, browse through the overview, migration strategies, current on-prem vs future page, before moving to the next exercise.

===
# Exercise 4: Review an assessment

You will notice that an assessment has already been created. This gets created automatically when you create a business case.

1. [] On the left menu, expand **Decide and plan**, and then select **Assessments**.

1. [] Select the **businesscase-bc-@lab.LabInstance.Id**.

>[!Note] Review the assessment. Browse through the different migration paths. Open the PaaS preferred migration path by clicking on "View details". Browse through the recommendations on Azure for the partsunlimited application.

1. [] From the top menu, select **Add code insights**, and then select **Using CAST Highlight**.

1. [] Next to Connection name, select **Create new**.

1. [] Enter +++CAST@lab.LabInstance.Id+++ for connection name.

1. [] For Company ID. enter +++7105+++

1. [] For Token, at the top of the lab instructions panel, select the **Resources** tab.

1. [] Locate the section marked **CAST Tokens**, and then select the **Token** to enter it. (Change back to the instructions tab)
 
1. [] enter +++@lab.CloudCredential(Token).Token+++.

1. [] Select **Authenticate**.

1. [] Select **Close**.

1. [] In the Application name in CAST dropdown, select **PartsUnlimited**, and then select **Add**.

    >[!Note] It will take approximately one minute to update and then you should see the Code insights under the PartsUnlimited Application. You will also see the Replatform recommendation for the application changing to Refactor based on the code changes required.

===
# Exercise 5: Migrate an on-prem SQL database to an Azure SQL Managed Instance

This exercise guides you through **Migrate an on-prem SQL database to an Azure SQL Managed Instance**, clarifying the purpose, expected outcome, and where to focus so you avoid common pitfalls.

## Task 1: Configure permission on the storage account

In this task, you'll **Configure permission on the storage account**, with concise, ordered steps to complete it efficiently.

1. [] In the Azure portal search bar at the top of the page, search for and then select +++Storage Accounts+++.

1. [] Select the **stoacc@lab.LabInstance.Id** storage account.

1. [] On the left menu, select **Access Control (IAM)**.

1. [] Select **+ Add**, and then select **Add role assignment**.

1. [] In the Search by role name field, enter +++Storage Blob Data Reader+++.

1. [] Select the **Storage Blob Data Reader** role, and then select **Next**.

1. [] On the Members page, select **+ Select members**.

	!IMAGE[lfo4n1bk.jpg](instructions315313/lfo4n1bk.jpg)

1. [] In the search field on the flyout page, enter and then select +++@lab.CloudPortalCredential(User1).Username+++.

1. [] Select **Select**.

1. [] Select **Review + assign**, and then select **Review + assign**.

## Task 2: Generate the storage account access string

In this task, you'll **Generate the storage account access string**, with concise, ordered steps to complete it efficiently.

1. [] On the left menu, expand **Security + networking**, and then select **Shared access signature**.

1. [] Under Allowed services, **deselect everything except Blob**.

1. [] Under Allowed resource type, select **All options**.

	!IMAGE[p7zkqbxp.jpg](instructions315313/p7zkqbxp.jpg)

1. [] Under Start and expiry date/time, for the Start date, enter +++11/01/2025+++.

1. [] For the End date, enter +++12/01/2025+++.

1. [] Select **Generate SAS and connection string**.

	!IMAGE[yya48ykd.jpg](instructions315313/yya48ykd.jpg)

1. [] At the end of the Blob service SAS URL string, select the copy icon.

	!IMAGE[z889rtph.jpg](instructions315313/z889rtph.jpg)

1. [] Minimize Microsoft Edge.

	!IMAGE[z0gltyf0.jpg](instructions315313/z0gltyf0.jpg)

1. [] Use the icon on the desktop to launch **Notepad**.

	!IMAGE[klm4vi1n.jpg](instructions315313/klm4vi1n.jpg)

1. [] In Notepad, paste the Blob service SAS URL string that you copied from the portal.

## Task 3: Create a backup of the SQL database to the Azure storage container

In this task, you'll **Create a backup of the SQL database to the Azure storage container**, with concise, ordered steps to complete it efficiently.

1. [] Use the icon on the desktop to launch the **PartsUnlimited SQL** RDP connection, and log in using +++Passw0rd!+++.

1. [] On the partunlimited-sqlsrv, go to the search bar, then search for +++ssms+++.

1. [] Select **SQL Server Management Studio 21**.

	!IMAGE[m8gv4xs6.jpg](instructions315313/m8gv4xs6.jpg)

1. [] On the Connect to Server pop-up, select **Connect**.

1. [] Expand **Databases**.

1. [] Right-click the **PartsUnlimitedDB**, select **Tasks**, and then select **Back Up...**.

1. [] Below Destination, for Back up to, select **URL**.

1. [] Select **Add** to add the Azure Blob location.

1. [] Minimize the **PartsUnlimited SQL** RDP session.

	!IMAGE[tui61iip.jpg](instructions315313/tui61iip.jpg)

1. [] At the beginning of the string that you pasted into Notepad, highlight from the https:// to the ? **(DO NOT INCLUDE THE ?)**.

	!IMAGE[zfd5s4yg.jpg](instructions315313/zfd5s4yg.jpg)

1. [] Copy the text that you highlighted.

1. [] From the system tray, select the RDP session to return to the SQL server.

	!IMAGE[ob66kem0.jpg](instructions315313/ob66kem0.jpg)

1. [] Paste the string that you just copied from Notepad into the **Azure storage container** field.

1. [] At the end of the string that you just pasted, add +++partsunlimited+++.

1. [] Minimize the **PartsUnlimited SQL** RDP session.

	!IMAGE[tui61iip.jpg](instructions315313/tui61iip.jpg)

1. [] In the string that you pasted into Notepad, highlight **after the ? to the end of the line** (DO NOT INCLUDE THE ?).

	!IMAGE[54wjldmr.jpg](instructions315313/54wjldmr.jpg)

1. [] Copy the text that you highlighted.

1. [] From the system tray, select the RDP session to return to the SQL server.

	!IMAGE[ob66kem0.jpg](instructions315313/ob66kem0.jpg)

1. [] Paste the string that you just copied from Notepad into the **Shared Access Signature** field.

1. [] Select **OK**, and then select **OK** again to start the backup.

    >[!Note] When you see the message that the backup has completed successfully, you have backed up the Parts Unlimited database to the Azure Blob storage.

1. [] Disconnect the **partunlimited-sqlsrv** RDP session.

    !IMAGE[17ctn6j3.jpg](instructions315313/17ctn6j3.jpg)

## Task 4: Configure permission for the Azure SQL Managed Instance to access the storage account

In this task, you'll **Configure permission for the Azure SQL Managed Instance to access the storage account**, with concise, ordered steps to complete it efficiently.

1. [] Ensure that you are still on the **stoacc@lab.LabInstance.Id** storage account page.

1. [] On the left menu, select **Access Control (IAM)**.

1. [] Select **+ Add**, and then select **Add role assignment**.

1. [] In the Search by role name field, enter +++Storage Blob Data Reader+++.

1. [] Select the **Storage Blob Data Reader** role, and then select **Next**.

1. [] Select **Managed identity**.

1. [] On the Members page, select **+ Select members**.

	!IMAGE[nutkn9h3.jpg](instructions315313/nutkn9h3.jpg)

1. [] In the search field on the flyout page, under Managed identity, select **SQL managed instance (1)**.

1. [] Select the **sql-mi-@lab.LabInstance.Id** managed instance that appears below, and then select **Select**.

1. [] Select **Review + assign**, and then select **Review + assign**.

## Task 5: Restore the backup of the on-prem SQL database to the SQL Managed Instance

In this task, you'll **Restore the backup of the on-prem SQL database to the SQL Managed Instance**, with concise, ordered steps to complete it efficiently.

1. [] In the Azure portal search bar at the top of the page, enter and then select +++Database Migration Services+++.

1. [] On the left menu, select **All resources**, and then select the **partsunl@lab.LabInstance.Id**.

1. [] On the Start migrations tile, select **New Migration**.

	!IMAGE[ngdjpr3o.jpg](instructions315313/ngdjpr3o.jpg)

1. [] On the Select migration scenario page, review the options, and then select **Select**.

1. [] On the Source details tab, enter the following.

    | Option | Value |
    | -------- | -------- |
    | Source infrastructure type | **Physical Server** |
    | Location | **@lab.CloudResourceGroup(AZMigrateRG).Location** |
    | SQL Server Instance Name | +++sql-mi-@lab.LabInstance.Id+++ |

1. [] Select **Next: Select migration target**.

1. [] On the Select migration target tab, review the options, and then select **Next: Data source configuration**.

1. [] On the Data source configuration tab, select the following.

    | Option | Value |
    | -------- | -------- |
    | Resource group | **AZMigrateRG** |
    | Storage Account | **stoacc@lab.LabInstance.Id** |
    | Blob container | **partsunlimited** |
    | Folder | **/** |
    | Last backup file | **Use default value** |
    | Target database | +++partsunlimiteddb+++ |

1. [] Check **I confirm the Managed Identity has read access to the above blob container(s)**.

1. [] Select **Next: Database migration summary**.

1. [] Review the selections, and then select **Start migration**.

    >[!Note] The migration will take several minutes. The **Migration status** will display **Succeeded** when the migration is finished. You can select **Refresh** periodically to update the status. 

    !IMAGE[evinfwwk.jpg](instructions315313/evinfwwk.jpg)



===
# Exercise 6: Migrate an on-prem App server to Azure App Service

This exercise guides you through **Migrate an on-prem App server to Azure App Service**, clarifying the purpose, expected outcome, and where to focus so you avoid common pitfalls.

## Task 1: Migrate the Web app

In this task, you'll **Migrate the Web app**, with concise, ordered steps to complete it efficiently.

1. [] Minimize the Edge browser.

1. [] Use the icon on the desktop to launch the **PartsUnlimited Web** RDP connection, and log in using +++Passw0rd!+++.

1. [] On the pop-up, select **Yes** to connect.

1. [] From the desktop, launch the **AppServiceMigrationAssistant**.

	!IMAGE[apqrhv4r.jpg](instructions315313/apqrhv4r.jpg)

1. [] On the Start page, select **Default Web Site**, and then select **Next**.

	!IMAGE[pnf44sca.jpg](instructions315313/pnf44sca.jpg)

1. [] On the Assessment Report for 'Default Web Site', select **Next**.

1. [] On the Login to Azure page, select **Copy Code & Open Browser**.

	!IMAGE[9vrb6ulw.jpg](instructions315313/9vrb6ulw.jpg)

1. [] **Paste** the code, and then select **Next**.

	!IMAGE[cityfp0c.jpg](instructions315313/cityfp0c.jpg)

1. [] If you are prompted to sign in, use +++@lab.CloudPortalCredential(User1).Username+++ and +++@lab.CloudPortalCredential(User1).AccessToken+++.

1. [] Select **Continue**, and then close the browser window.

1. [] In the Azure Migrate Project drop-down, select the **az-migrate-@lab.LabInstance.Id**, and then select **Next**.

1. [] On the Azure Options page, use the following values.

    | Option | Value |
    | -------- | -------- |
    | Resource Group | Use existing<br>**AZMigrateRG** |
    | Destination Site Name | +++partsunlimited-@lab.LabInstance.Id+++ |
    | Region | **Italy North** |
    | Databases | **Skip database setup** |

1. [] Select **Migrate**.

1. [] Wait for the migration to complete.

    >[!Note] The migration will take several minutes.

    >[!Alert] If your migration fails, you can try again using other regions. Many regions are restricted. You can also ask for suggestions from the proctors.

1. [] On the Migration Results page, confirm that it displays **Congratulations, your site has been successfully migrated!**.

1. [] Disconnect the **partunlimited-sqlsrv** RDP session.

    !IMAGE[05mh0af8.jpg](instructions315313/05mh0af8.jpg)

## Task 2: Update the web app connection string

In this task, you'll **Update the web app connection string**, with concise, ordered steps to complete it efficiently.

1. [] Return to the **Azure portal** tab in the Edge browser.

1. [] In the Azure portal search bar at the top of the page, enter and then select +++Azure SQL Managed Instance+++.

1. [] Select the **sql-mi-@lab.LabInstance.Id** managed instance.

1. [] On the Overview page, locate the host entry.

1. [] Locate only the **section that appears after this sql-mi-@lab.LabInstance.Id. and before the next "."** and type it into the text box below (do not include the dots).

	 @lab.TextBox(MILocationTag).

1. [] In the Azure portal search bar at the top of the page, enter and then select +++App Service+++.

1. [] Select the **partsunlimited-@lab.LabInstance.Id** App Service.

1. [] On the left menu, expand **Settings**, and then select **Environment variables**.

1. [] Select the **Connection strings** tab, and then select **+ Add**.

1. [] In the Name, enter +++DefaultConnectionString+++.

1. [] For the Value, enter +++Server=tcp:sql-mi-@lab.LabInstance.Id.public.@lab.Variable(MILocationTag).database.windows.net,3342;Database=partsunlimiteddb;User ID=misqladmin;Password=Password~1;Encrypt=True;TrustServerCertificate=False;Connection Timeout=30;+++.

1. [] For the Type, select **SQLAzure**.

1. [] Select **Apply**, and then select **Apply**.

1. [] Select **Confirm**.

## Task 3: Edit the web app config file

In this task, you'll **Edit the web app config file**, with concise, ordered steps to complete it efficiently.

1. [] In the search bar above the left menu, enter +++kudu+++, and then select **Advanced Tools**.

	!IMAGE[fpa96h6c.jpg](instructions315313/fpa96h6c.jpg)

1. [] Select **Go ->**.

1. [] On the top menu, select **Debug console**, and then select **CMD**.

	!IMAGE[ct9g50t2.jpg](instructions315313/ct9g50t2.jpg)

1. [] Select **Site**, and then select **wwwroot**.

1. [] Scroll down and select edit (pencil icon) to the left of **web.config**.

	!IMAGE[as0zizbg.jpg](instructions315313/as0zizbg.jpg)

1. [] **Replace the contents of line 26** with the following: `<add name="DefaultConnectionString" connectionString="" providerName="System.Data.SqlClient" />`.

1. [] Select **Save** in the top left, and then close the browser tab.

1. [] On the partsunlimited-@lab.LabInstance.Id App Service page, select the **X** next to Kudu in the search box to clear the search.

1. [] Select the **Overview** page.

1. [] At the top of the Overview page, select **Restart**, and then select **Yes**.

	!IMAGE[n9bvmdwa.jpg](instructions315313/n9bvmdwa.jpg)

1. [] Select the **Default domain** link to open the app in a new browser tab.

	!IMAGE[g6qykvc7.jpg](instructions315313/g6qykvc7.jpg)

If you see the Parts Unlimited website, congratulations, you have successfully migrated both the web app and SQL database from on-prem to Azure.

===
# Exercise 7: Configure Replication of a Windows VM

This exercise guides you through **Configure replication of a Windows VM**, clarifying the purpose, expected outcome, and where to focus so you avoid common pitfalls.

1. [] In the Azure search box at the top, search for and then select +++Azure Migrate+++.

1. [] In the left menu, select **All projects**.

1. [] Select **az-migrate-project-@lab.LabInstance.Id**.

1. [] In the left panel, expand **Execute**, and then select **Migrations**.

1. [] On the **Replication** tile, select **Replicate**.

	!IMAGE[0r6qb095.jpg](instructions315313/0r6qb095.jpg)

1. [] On the Specify intent page, in the Are your machines virtualized? drop-down, select **Yes, with VMware vSphere**.

1. [] In the On-premises appliance drop-down, select **app@lab.LabInstance.Id (Azure Migrate Appliance)**, and then select **Continue**.

1. [] On the Virtual machines tab of the Replicate page, use the following settings to complete the replication criteria.

    | Setting                                                    | Value                                                              |
    | :--------------------------------------------------------- | :----------------------------------------------------------------- |
    | Import migration settings from an Azure Migrate assessment | **No, I'll specify the migration settings manually**. |
    | Virtual machines                                           | **GadgetCart**. |

	>[!Alert] Do not select any machines other than the ones listed.

1. [] Select **Next**.

1. [] On the **Target settings** tab of the Replicate page, use the following settings to specify the target details.

    | Setting                     | Value                                         |
    | :-------------------------- | :-------------------------------------------- |
    | Region                      | **@lab.CloudResourceGroup(AZMigrateRG).Location** |
    | Storage account             | **stoacc@lab.LabInstance.Id**                                   |
    | Subscription                | **@lab.CloudSubscription.Name**               |
    | Resource group              | **@lab.CloudResourceGroup(AZMigrateRG).Name** |
    | Register with SQL Iaas extension | **Uncheck**.                         |
    | Virtual Network             | **migrate@lab.LabInstance.Id**                |
    | Subnet                      | **Default**                                   |
    | Availability options        | **No infrastructure redundancy required**.    |

1. [] Select **Next**.

1. [] On the Compute tab of the Replicate page, select the following.

    | Setting                     | Value                                         |
    | :-------------------------- | :-------------------------------------------- |
    | Name                        | **GadgetCart** |
    | VM Security Type            | **Trusted launch virtual machines** |
    | Azure VM Size               | +++Standard_D2s_v4+++ |

1. [ ] Select **Next**.

1. [] On the Disks tab of the Replicate page, review the settings, and then select **Next**.

1. [] On the Tags tab of the Replicate page, select **Next**.

1. [] On the Review + Start replication tab of the Replicate page, review the settings and select **Replicate**.

    >[!Alert] Wait for the replication job to begin. You may be returned to the **Specify intent** page. You do not need to configure this a second time; you can safely continue to the next step.

1. [] In the breadcrumbs menu at the top, select your project **az-migrate-project-@lab.LabInstance.Id** to return to the main project page.

1. [] On the Track migrations tile, select **Replications summary**.
    
    !IMAGE[9aplco3l.jpg](instructions315313/9aplco3l.jpg)

1. [] In the left panel, expand **Migration**, and then select **Jobs**.

	>[!Note] You should see a job named **Create replication policy**.

	>[!Note] The replication will take approximately 40 minutes to complete. You can safely continue to the next exercise while the replication job is running.

1. [] In the breadcrumbs menu at the top left, select the az-migrate-project.

	!IMAGE[ij4uo6mf.jpg](instructions315313/ij4uo6mf.jpg)

===
# Exercise 8: Perform a VM migration

This exercise guides you through **Perform a VM migration**, clarifying the purpose, expected outcome, and where to focus so you avoid common pitfalls.

1. [] In the Azure portal search bar at the top of the page, enter and then select +++Azure Migrate+++.

1. [] On the left menu, select **All projects**.

1. [] Select the **az-migrate-project-@lab.LabInstance.Id**.

1. [] On the left menu under **Execute**, select **Migrations**.

1. [] On the Track migrations tile, select **Replications summary**.

	!IMAGE[qt09hphu.jpg](instructions315313/qt09hphu.jpg)

1. [] On the left menu under **Migration**, select **Replication**.

1. [] Ensure that the replication status of the GadgetCart server is **Delta sync**.

	!IMAGE[8y9m3u5p.jpg](instructions315313/8y9m3u5p.jpg)

	>[!Alert] If the replication status displays anything other than **Delta sync**, you must wait for the replication to complete before you may continue.

1. [] Select **Migrate** from the top menu.

1. [] Ensure that **Shutdown machines before migration to minimize data loss** is set to **Yes**.

1. [] Check the box next to **GadgetCart**, and then select **Migrate**.

1. [] Refresh the browser periodically and wait for the migration to complete. 

    >[!Note] The migration status will change to the current date and time when the migration is complete.

===
# Exercise 9: Post-migration tasks

This exercise guides you through **Post-migration tasks**, clarifying the purpose, expected outcome, and where to focus so you avoid common pitfalls.

##Task 1: Confirm VM has been migrated to Azure

In this task, you'll **Confirm VM has been migrated to Azure**, with concise, ordered steps to complete it efficiently.

1. [] In the top left of the Azure portal, select **Home**.

1. [] On the Home screen, select **Virtual machines**.

	!IMAGE[iyetev8p.jpg](instructions315313/iyetev8p.jpg)

1. [] Confirm that you see the GadgetCart VM running in Azure.

	!IMAGE[qmu7g70i.jpg](instructions315313/qmu7g70i.jpg)

## Task 2: Assign a public IP to GadgetCart

In this task, you'll **Assign a public IP to GadgetCart**, with concise, ordered steps to complete it efficiently.

1. [] On the Virtual machines page, select the **GadgetCart** VM.

1. [] On the GadgetCart page, expand Networking, and then select **Network settings**.

1. [] Next to Public IP address, select **(Configure)**.

    !IMAGE[uahu792o.jpg](instructions315313/uahu792o.jpg)

1. [] On the IP Settings page, select the nic (the link, not the checkbox).

1. [] Check the box next to **Associate public IP address**.

1. [] In the drop-down, select **public_ip_@lab.LabInstance.Id** (x.x.x.x).

1. [] Select **Save**.

## Task 3: Test the migration

In this task, you'll **Test the migration**, with concise, ordered steps to complete it efficiently.

1. [] Open a new browser tab and connect to +++http://public-ip-@lab.LabInstance.Id.@lab.CloudResourceGroup(AZMigrateRG).Location.cloudapp.azure.com+++.

1. [] You should see the Parts Unlimited website.

	!IMAGE[xuywc6gd.jpg](instructions315313/xuywc6gd.jpg)

If you see the Parts Unlimited website, congratulations, you have successfully migrated the GadgetCart server from on-prem to Azure, and you are accessing it via an Azure-assigned public IP address.

===
# Complete

You have completed the exercises in this workshop.

Select **End** to close the lab environment.  
===
1. [] Select this button to generate your login token @lab.Activity(Automated2)
+++@lab.Variable(tap)+++
