

# Developer Environment (Common to all languages)

## Overview
In this lab, you will set up an Office365 trial subscription, an Azure trial subscription, configure your Azure subscription for the DevCamp, and provision 
a virtual machine in the subscription to use for development of further labs.

## Objectives
In this hands-on lab, you will set up an Office365 developer subscription, and Azure trial subscription, and an Azure-based virtual machine for the development environment for subsequent labs in the DevCamp.  To expedite the process, we've prepared Windows and Linux images that you will copy into your own environment, start the virtual machine and connect to it.  You will then configure the components for Azure development.
* Set up an Office365 trial subscription
* Set up an Azure trial subscription
* Configure your Azure subscription for DevCamp
* Create an Azure Virtual Machine for development
* Connect to the Azure Virtual Machine and configure it for development.
* Review the features of the Azure Portal
* Review the Resource group that we created in Exercise 3

## Prerequisites

You will need a cell phone and credit card for identity verification.  The credit card will not be charged unless you remove the spending cap on the subscription you will create.

## Exercises
This hands-on-lab has the following exercises:
* Exercise 1: Set up Office 365 trial subscription
* Exercise 2: Set up Azure trial subscription
* Exercise 3: Start your VSTS trial subscription
* Exercise 4: Configure your Azure subscription for DevCamp
* Exercise 5: Use an Azure Virtual Machine for development
* Exercise 6: Connect to the Azure Virtual Machine and configure it for development
* Exercise 7: Connect to the Azure Virtual Machine and configure it for development
* Exercise 8: Azure Portal walkthrough
* Exercise 9: View the resources you created

---
### Exercise 1: Set up Office 365 trial subscription

1. In your browser, go to `https://products.office.com/en-us/business/office-365-enterprise-e3-business-software` 
and click the link that says "Free Trial", which will take you to this page:

    ![image](./media/2016-10-14_18-59-56.png)

1. Enter the information requested, and click `Just one more step` which 
    will take you to the following page:
    
    ![image](./media/2016-10-14_19-06-31.png)

1. Choose a userid and a `tenant name` for your trial.  In this case I chose `devcampross`, but you 
    can choose anything you'd like, as long as it is unique.  You'll also have to choose 
    a password, and click `Create my account`.  Next you will see this page, which asks
    for a phone verification:

    ![image](./media/2016-10-14_19-07-30.png)

1. After this process is complete, your O365 trial will be set up, and you'll see this page:
    
    ![image](./media/2016-10-18_12-39-13.png)

    Make note of your user id, which will be used to sign onto the Azure portal later.
    Click `You're ready to go`, which will take you to the following screen:

    ![image](./media/2016-10-18_12-42-47.png)

    Click on the `admin` app icon, which will open the Office365 admin center page
    in your browser.  It will look like this:

    ![image](./media/2016-10-14_18-38-17.png)

     If you'd like to see the welcome tour click `Next`, 
    or simply close the dialog box.   
    
> Stay on this page until the next exercise.

---
### Exercise 2: Set up Azure trial subscription

1.  Next, we want to set up an Azure subscription, which
    can be accessed via the Azure Active Directory.  At the bottom of the screen, 
    click `Admin centers`, and then click `Azure AD`. This will open up a new browser tab
    showing this page:

    ![image](./media/2016-10-14_21-41-33.png)

1. Click on `Azure subscription`, that will take you to the page for creating a new 
    trial subscription:

    ![image](./media/2016-10-18_12-48-52.png)

    Enter the requested information and click `next`.

1. Enter the information about you, and verify your identity by phone.  Also you'll 
    need to verify via credit card.  Your credit card will not be charged unless you
    remove the spending cap from your subscription.
    
    ![image](./media/2016-10-14_21-42-46.png)

1. Finally after the verification process, you'll have to agree to the terms of the trial
    subscription: 

    ![image](./media/2016-10-14_21-44-53.png)

1. it will take a few moments to set up your azure subscription.  

    ![image](./media/2016-10-14_21-45-32.png)

1. When the subscription set up process is done, you can click on `Start managing my service`
to open the Azure portal, which will look like this:

    ![image](./media/2016-10-14_18-00-54.png)

---
### Exercise 3: Start your VSTS trial subscription

1. In your browser, go to `http://www.visualstudio.com/team-services`, and click on `sign in` in the upper right corner.  This should take you to a screen that looks like this:

    ![image](./media/2016-10-18_17-30-18.png)

    click on `Use your benefits`, and this window will pop up:

    ![image](./media/2016-10-18_17-42-01.png)

    Click Accept to access your Visual Studio Dev Essentials benefits.

---
### Exercise 4: Configure your Azure subscription for DevCamp

1. We have created an Azure Resource Group template that will configure the resources you need in Azure for the DevCamp.  To deploy 
these resources in your Azure subscription, do `control-click` on this button:

    <a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAzureCAT-GSI%2FDevCamp%2Fmaster%2FShared%2FARMTemplate%2FAzureDeploy.json" target="_blank">
        <img src="http://azuredeploy.net/deploybutton.png"/>
    </a>

1. You should see a new tab open in your browser and open the Azure portal, with a blade that looks like this:

    ![image](./media/2016-10-18_13-13-25.png)

    Name your resource group `DevCamp`, choose a location for your deployment (please do **NOT** choose USGov, Brazil South, UK West or UK South - they don't have all the services we'll need), check the box that indicates you agree to the terms and conditions, and click the `Purchase` button.

    The Resource Group template will start deploying, and the portal will pin a tile to the dashboard showing the status:

    ![image](./media/2016-10-18_13-19-01.png)

1. This will take approximately 20 minutes to complete. Please don't continue on until the template has completed.  While it is working, it is useful to understand what this process is doing.
    In a later session, we will take a look at Azure Resource Group templates, and how to manage your infrastructure the same way 
    you manage your code.  As a short introduction, a template is a JSON file that contains definitions for the resources you want in your
    resource group.  When you apply the resource group template, Azure will apply the template to your Azure resource group, and create 
    the resources you have specified in the template.  This makes it easy to maintain the infrastructure definition in the JSON text file.
    
    In the resource group template we have created for DevCamp, there are several types of resources including Web Apps and Virtual Machines.  The 
    complete list of resources deployed is detailed in Exercise 8 of this Hands-On-Lab.  Resource Group Templates are usually fairly quick to
    apply - the reason this one takes so long is that we are creating a Windows Virtual machine and installing all the tools you will
    need for the DevCamp including Visual Studio, the Java development kit, and other software resources.

    When the Resource Group creation is done, go visit the resource group by clicking `resource groups on the left:

    ![image](./media/2016-10-18_13-36-29.png) 

    Then click your Resource group

    ![image](./media/2016-10-18_13-39-10.png)

---
### Exercise 5: Use an Azure Virtual Machine for development

1. The Azure resource group template will have created two virtual machines - one for 
Windows development, and the other for Linux development.  Exercise 6 describes the configuration
for the Windows virtual machine, which would be appropriate for any of the languages.  Exercise 7 describes 
the configuration for the Ubuntu Linux virtual machine - this would be approproate for Java or Node development.


1. Find the Windows virtual machine in your resource group, it's name will start with `windev`:

    ![image](./media/2016-10-18_15-32-30.png)

    The Linux development machine is the one that starts wit `ubudev`.

1. Jump to Exercise 6 for Windows (all languages) or 7 for Linux (Node or Java), based on your development OS & language choice.

---
### Exercise 6: Connect to the Windows Azure Virtual Machine and configure it for development
You can develop for any of the three languages using a Windows virtual machine in Azure.  If you'd like to use
Windows as your development platform, follow these instructions in Exercise 6.  If you would rather use 
Linux for your development platform (and are using either Node.js or Java), jump to Exercise 7.

1. Click the virtual machine, and then click `Connect` to connect to the machine using 
Remote Desktop:

    ![image](./media/2016-10-18_16-37-57.png)

    This will download a remote desktop connection file, and when you open it, remote desktop 
    on your local machine will attempt to attach to your virtual machine.   When the windows security dialog pops up, click on the `more choices link`, then choose `use a different account`
    
    ![image](./media/2016-10-19_14-42-16.png)

    Use the credentials `l-admin` with password `Devc@mp2016!` to log on to the machine.  It
    would be wise to change the password in the virtual machine.

    When remote desktop is connected, you will see server manager initially.  We will
    want to turn of IE enhanced security, to make accessing the web within the virtual machine easier.  First click local server;

    ![image](./media/2016-10-18_16-46-33.png)

    then click the `on` next to 

    ![image](./media/2016-10-18_16-50-50.png)

    A dialog box pops up - choose to turn enhanced security off for administrators.

1. We are going to use git to clone the DevCamp github repository to this development machine.  Open `cmd`, change directory to the root using `cd c:\`, and do `git clone https://github.com/AzureCAT-GSI/DevCamp.git` :

    ![image](./media/2016-10-18_17-03-51.png)

    All of the content for this DevCamp will now be located in `c:\DevCamp\`.

    Start Visual Studio using `start experimental instance of visual studio 2015`, and in the sign in screen, click `sign in` and use the credentials you used earlier for Office 365.

    ![image](./media/2016-10-18_17-59-21.png)
    
    You can create a VSTS repository now, choose an appropriate repository name and click continue:

    ![image](./media/2016-10-18_18-07-34.png)

    Create your first team project, and name it `DevCamp`:

    ![image](./media/2016-10-18_18-10-39.png)

    Finally click close, and you are done with the Visual Studio setup.

1. We are now going to deploy our .NET API to an Azure App Service if necessary.  First, check whether the API application is installed.  Go to the Azure portal and locate the app service named `incidentapi....` in the resource group blade:
    ![image](./media/2016-11-14_12-00-24.png)

    click on that app service, which will bring up the app service blade.  Click on `Browse` at the top:

    ![image](./media/2016-11-14_12-02-26.png)

    A new browser tab will open.

    ![image](./media/2016-11-14_12-10-59.png)

    If the page looks like the above image, this means the API was automatically deployed from GitHub, and you can skip the rest of this step.  Otherwise, it should have the below initial web app page, and you should continue with this step, deploying the API app to the app service.

    ![image](./media/2016-11-14_12-03-50.png)

    In the command window change the directory to the root with `cd \`, and clone the GitHub repository for the API with `git clone https://github.com/AzureCAT-GSI/DevCamp.git`.  

    Switch back to Visual Studio and open the API solution with **File > Open > Project/Solution**:

    ![image](./media/2016-10-18_18-34-01.png)

    and open the `DevCamp.Shared.sln` solution located at `C:\DevCamp\Shared\API\src`.  

    ![image](./media/2016-10-18_18-44-50.png)

    right click on the DevCamp API project, and choose `publish`:

    ![image](./media/2016-10-18_18-47-26.png)

    In the publish wizard, click `Microsoft Azure App Service` for the publish target:

    ![image](./media/2016-10-18_18-49-13.png)

    Next select `DevCamp` and then the `incidentapi...` app service, and click `OK`

    ![image](./media/2016-10-18_18-55-41.png)

    In the next step, leave all the defaults and click `Publish`:

    ![image](./media/2016-10-18_19-03-10.png)

    After a short time, you should see the `publish succeeded` message in the output window:

    ![image](./media/2016-10-18_19-05-52.png)
    
1. In a browser windows inside your development Virtual Machine, open a browser window and go to `http://nodejs.org`, 
and click on the `Other Downloads` link under v6.9.0:

    ![image](./media/2016-10-19_10-15-22.png)

    In the next page, click on `32 bit` next to `Windows Installer (.msi)`, download the MSI and run the installation.

    ![image](./media/2016-10-19_10-20-21.png)

    >please do not skip this step, because we will need node.js to install the Azure cross platform command line interface in the next step.

1. Install the azure command line interface.  Go to a terminal window and do this command:
    `node -v` 
    Verify that the version is v6 or greater.

    `npm install azure-cli -g`

---
### Exercise 7: Connect to the Linux Azure Virtual Machine and configure it for development
You only need to perform Exercise 7 if you want to use the Linux Virtual Machine for development.  If you are going to use Windows for development instead, feel free skip to Exercise 8.  Otherwise, let's configure the Linux machine for DevCamp:

1. In the Azure portal, click on the Linux machine and make note of its public IP address:

    ![image](./media/2016-10-31_10-37-38.png)

1. We will need to install an application on your local machine to [SSH](https://en.wikipedia.org/wiki/Secure_Shell) into the Linux virtual machine.  On Windows, two of the popular SSH applications are
[PUTTY](http://www.putty.org/) and [MobaXterm](http://mobaxterm.mobatek.net/).  These instructions will
assume Putty, but you can install the terminal/SSH application of your choice.

    After installing Putty, open the applicationand type your linux machine IP address in the host Name box, and click open:

    ![image](./media/2016-10-31_10-41-51.png)

    log in with your l-admin/Devc@mp2016! credentials.  It would be wise to change the password at this point.

1. On Mac or Linux, you can simply open up a terminal window and use
    ```bash
    ssh -l l-admin <ubuntu machine IP addr> 
    ```
    to connect to the Linux virtual machine.

1. We are now going to install a desktop environment on the virtual machine, and enable remote desktop to it.  Newer versions of the Ubuntu desktop don't work with xrdp, so we're going to install the [xfce](http://www.xfce.org/) desktop environment.  Perform these commands in the Putty/terminal window:
    ```bash
    sudo apt-get update
    sudo apt-get install -y ubuntu-desktop
    sudo apt-get install -y xrdp
    sudo apt-get install -y xubuntu-desktop
    echo xfce4-session >~/.xsession
    ```
    Edit the config file `/etc/xrdp/startwm.sh`, using:
    ```
    sudo vi /etc/xrdp/startwm.sh 
    ```

    Add line `xfce4-session` before the line `/etc/X11/Xsession`.

    restart the xrdp service using this command:
    ```bash
    sudo service xrdp restart
    ```

1. On your local Windows or Mac machine, start remote desktop, and enter the Linux VM IP address:

    ![image](./media/2016-10-31_11-25-39.png)

    Click connect, and you should get a window that contains the XRDP login:

    ![image](./media/2016-10-31_11-28-12.png)

    Login with your VM credentials, and you should get the Ubuntu desktop screen:

    ![image](./media/2016-10-31_11-30-57.png)

1. Now let's configure the machine for DevCamp development.  
    ```
    sudo apt-get update
    sudo apt-get install build-essential libssl-dev
    curl https://raw.githubusercontent.com/creationix/nvm/v0.16.1/install.sh | sh
    source ~/.profile
    nvm install 6.9.1
    nvm alias default 6.9.1
    npm install azure-cli -g
    sudo apt-get git
    sudo apt-get update
    sudo add-apt-repository ppa:webupd8team/java
    sudo apt-get update
    sudo apt-get install oracle-java8-installer
    sudo apt-get install -y gradle
    sudo apt-get install -y maven 
    wget -O VisualStudioCode.deb http://go.microsoft.com/fwlink/?LinkID=760868 
    sudo dpkg -i VisualStudioCode.deb
    ```

1. if you want to use Visual Studio Code, you'll need to use a workaround documented [here](https://github.com/Microsoft/vscode/issues/3451).

1. We are going to use git to clone the DevCamp github repository to this development machine.  Open a terminal window, change directory to your user's root using `cd ~/`, and do `git clone https://github.com/AzureCAT-GSI/DevCamp.git` :

    ![image](./media/2016-10-18_17-03-51.png)

    All of the content for this DevCamp will now be located in `~/DevCamp`.

---
### Exercise 8: Azure Portal walkthrough

1. On your local machine or the virtual machine in Azure, open a browser window and go to the main Azure portal page, http://portal.azure.com.  Log in with the credentials you supplied in the subscription signup exercise.  You should see the Azure portal, similar to this:

    ![image](./media/2016-10-19_15-08-26.png)

    There is a lot to notice on this screen.  At the upper left corner, the icon under the `Microsoft Azure` banner allows you to shrink and expand the left bar:

    ![image](./media/2016-10-19_15-15-50.png)

    Under that, clicking on the `+ New` item will allow you to create new deployments, virtual machines, databases, etc:

    ![image](./media/2016-10-19_15-15-50.png)
    
1. On the left you will see a list of the Azure services that you can use on the left hand side.  Notice that this list will scroll up and down to reveal more services, and finally an item that says `More Services >`:

    ![image](./media/2016-10-19_15-10-45.png)

    You can click on any of these and see what items are deployed, and easily create new deployments.

    At the top of the window you have a search box where you can search for any resources:

    ![image](./media/2016-10-19_15-22-14.png)

1. The bell icon is for notifications, and in this screenshot, it indicates that there are two notifications pending: 

    ![image](./media/2016-10-19_15-22-14a.png)

    Clicking on the bell will show you the notifications:

    ![image](./media/2016-10-19_15-49-23.png)

    If you click on one of the notifications, you can go to the list of 
    all current notifications:

    ![images](./media/2016-10-19_15-51-02.png)

1. The gear at the top of the screen lets you set the color palate for the portal, whether or not there will be animations, and other options for the portal itself:

    ![image](./media/2016-10-19_15-22-14b.png)

1. The "smiley face" button allows you to send feedback to Microsoft:

    ![image](./media/2016-10-19_15-22-14b.png)

    Clicking on the icon will give you a form to let us know about your experience:

    ![image](./media/2016-10-19_15-54-02.png)

1. The Question icon will give you the ability to enter a support case, manage support requests, or get further information on Azure.
    
    ![image](./media/2016-10-19_15-22-14d.png)

1. Your login name and company name on the upper left hand corner has two functions: 

    ![image](./media/2016-10-19_15-22-14e.png)
    
    If you hover the mouse over your name, you'll get information about your login, the directory and subscription:

    ![image](./media/2016-10-19_16-25-54.png)

    If you click on your name, you can sign out, change your password, view your permissions, and view your bill:

    ![image](./media/2016-10-19_16-28-33.png)

1. Next we will look at the resource group we set up with the template.  Click on `Resource Groups` on the left hand side:

    ![image](./media/2016-10-19_16-30-19.png)

    then, click on the resource group that you created:

    ![image](./media/2016-10-19_16-32-12.png)

    A new blade will open with the overview of all of the contents of the resource group listed:

    ![image](./media/2016-10-19_16-33-39.png)

    You can click on any of the items on the left hand side which will view or manipulate settings for the resource group as a whole.  If you click on any of the individual resources in the center, you will get more information on that resource.

1. Azure automatically logs changes to resource group and who made those changes.  Clicking `Activity log` on the left of the blade will allow you to query the log, and clicking on any logged items will give you additional information on that entry:

    ![image](./media/2016-10-19_16-40-00.png)

1. Clicking on `Automation script` will allow you to view, edit or download the resource group template that would create this resource group.

    ![image](./media/2016-10-19_16-44-51.png)

> it is particularly useful to create resources in the Azure portal, then save or edit the resource group template.  Resource group templates will be explained further in a later lab.

### Exercise 9: View the resources you created

Going back to the list of resources in the resource group, we'll go through the list of each resource, with a description.  Feel free to click on the resource and view its detail blade.

![image](./media/2016-10-19_17-13-01.png)

Also, our resource group template has added a random string to the end of many of the resources.  In this description, we'll replace that string with ....

1. `incidentcache....:`  This is the Redis cache that we use from the application to make data access faster.  The modern-cloud-apps hands on lab adds support to the application to be able to leverage the cache.

1. `ubudev....:` This is an Ubuntu linux virtual machine, meant to be for development in a non Windows server environment.  If you are doing development in Windows only or in an on-premisses machine, you can safely delete this virtual machine.

1. `windev....:` This is the Windows server virtual machine that we are using as a development machine for these hands-on-labs.  You can delete this machine after the developer-environment lab if you are using Linux or an on-premisses machine for development. 

1. `incidentdb....:` This is the documentDB database that will hold the JSON incident documents stored by the application.

1. `ubdev....NetworkInterface:`  This is a network interface that will allow the Ubuntu linux virtual machine to communicate on the network.  If you delete the Ubuntu virtual machine, you can safely delete this.

1. `windev...NetworkInterface:`  This is a public network interface that will allow the Windows development virtual machine to communicate on the network.  If you delete the Windows virtual machine, you can safely delete this.

1. `UbuntuDevPip:`  This is a public IP that will allow the Ubuntu linux virtual machine to communicate with the Internet (eg. via Putty).  If you delete the Ubuntu virtual machine, you can safely delete this.

1. `WindowsDevPip:`  This is a public IP that will allow the Windows development virtual machine to communicate with the Internet (eg. via Remote Desktop).  If you delete the Windows virtual machine, you can safely delete this.

1. `DevCampVnet:`  This is an Azure Virtual Network, which will allow components of the resource group to communicate as they were on the same physical network.

1. `incidentblobstg....:` Storage account for storing the uploaded images and the Azure Queue, from the modern-cloud-apps lab.

1. `incidentdiagstg....:` Storage account for storing diagnostics from the services in the resource group.

1. `vmstorage....:` Storage account for storing the virtual hard disk images for the virtual machines in the resource group.

1. `incidentappplan....:` App Service Plan, which defines how the app services in the resource group will be configured.

1. `dotnetapp....:` App service for running the .NET application when deployed to the cloud.  If you are not using .NET in the labs, you can safely delete this.

1. `incidentapi.....:` App service for running the API service that provides a REST API to the web applications.

1. `javaapp....:` App service for running the Java application when deployed to the cloud.  If you are not using Java in the labs, you can safely delete this.

1. `nodejsapp....:` App service for running the Node.js application when deployed to the cloud.  If you are not using Node.js in the labs, you can safely delete this.

---
## Summary

In this hands-on lab, you learned how to:
* Set up an Office365 developer subscription
* Set up an Azure trial subscription
* Configure your Azure subscription for DevCamp
* Create an Azure Virtual Machine for development
* Connect to the Azure Virtual Machine and configure it for development
* Use the Azure portal to view the resources that you created

After completing this module, you can continue on to Module 2: Building modern cloud apps

#### View Module 2 instructions for [.NET](../../../HOL/dotnet/02-modern-cloud-apps) 

---
Copyright 2016 Microsoft Corporation. All rights reserved. Except where otherwise noted, these materials are licensed under the terms of the MIT License. You may use them according to the license as is most appropriate for your project. The terms of this license can be found at https://opensource.org/licenses/MIT.