# Objective
Install and configure Metasploitable through VirtualBox

# Useful Links
* [https://www.virtualbox.org/wiki/Downloads](https://www.virtualbox.org/wiki/Downloads)
* [https://sourceforge.net/projects/metasploitable/](https://sourceforge.net/projects/metasploitable/)

# Oracle VM VirtualBox
Before installing Metasploitable, it is necessary to install a virtual machine manager. In this case, we have chosen to use Oracle VM VirtualBox.

Go to the following address: [https://www.virtualbox.org/wiki/Downloads](https://www.virtualbox.org/wiki/Downloads). Download the installer for the latest version available for Windows (currently it is `7.0.20`). After installing the software, we should see the main screen:

<img src="1.png" width="650">

# Metasploitable
We can download Metasploitable from the following address: [https://sourceforge.net/projects/metasploitable/](https://sourceforge.net/projects/metasploitable/) (the file is about 1 GB):

<img src="2.png" width="850">

We saved the file in this directory:

<img src="3.png" width="650">

Extract the file:

<img src="4.png" width="650">

Now that we have downloaded Metasploitable, we can add it to VirtualBox for use. Open VirtualBox:

<img src="1.png" width="650">

Click on `New`:

<img src="5.png" width="650">

Assign a name to the VM you want to create, and select `Linux:Debian64` as the OS. In this way, we have created a VM on VirtualBox:

<img src="6.png" width="650">

Now we can associate this VM with the Metasploitable file we downloaded. To do this, select the VM and click on `Settings`. Then select `Storage`. Here, select the default file `metasploit.vdi` under the `SATA` section. At this point, select `Choose a disk file`:

<img src="6.5.png" width="650">

Select the `.vdmk` file:

<img src="7.png" width="650">

# Configuring Metasploitable
To use Metasploitable, select the VM on VirtualBox and click on `Run`. VirtualBox opens the Metasploitable shell. Upon access, you will be asked for credentials, which are displayed on the screen (`msfadmin:msfadmin`):

<img src="8.png" width="650">

By entering the credentials, we finally arrive at the Metasploitable shell:

<img src="9.png" width="650">

Using the `ifconfig` command, we can read the IP of the VM, which is `10.0.2.15`:

<img src="10.png" width="650">

Trying to ping this IP from the Windows shell returns no results:

<img src="11.png" width="650">

This happens because the VM is not yet configured in Bridged mode. To configure it, close the shell and return to the VM settings in the `Network` section:

<img src="12.png" width="650">

Here, we need to set the settings like this, selecting the same network interface we use on Windows:

<img src="13.png" width="650">

If we now reopen the VM, we can see that the IP has changed, and it is now `192.168.1.227`:

<img src="14.png" width="650">

In this way, we can successfully ping Metasploitable from Windows:

<img src="15.png" width="650">