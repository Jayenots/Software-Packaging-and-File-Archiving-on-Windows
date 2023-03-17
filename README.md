# Software-Packaging-and-File-Archiving-on-Windows

<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket. OsTicket is a widely-used open source support ticket system which seamlessly integrates inquiries created via email, phone and web-based forms into a simple easy-to-use multi-user web interface. It can manage, organize and archive all your support requests and responses in one place while providing your customers with accountability and responsiveness.<br />


<h2>Video Demonstration</h2>

- ### [ How To Setup a Resource Group](https://loom.com/share/a4b3e70ccf6246aa89bed4496dea9a86)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Create the environment using Azure
- Install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)
- Install Rewrite Module (rewrite_amd64_en-US.msi)
- Create a directory c:\PHP
- Download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP
<a href="https://imgur.com/hSxWqeY"><img src="https://i.imgur.com/hSxWqeY.png" title="source: imgur.com" /></a>

# Software Packaging and File Archiving on Windows

In this lab, we'll learn how to install and remove software in the Windows GUI and CLI, and work with zipped files. We'll install a text editor, called Sublime Text, and extract/un-extract .tar files. We'll also use *Windows Powershell*  to install and uninstall programs on Windows.

**What you'll do**

You have a bunch of tasks for this lab. First, you'll install and remove software using the Windows graphical user-interface (GUI). Second, you'll remove and install software using the Windows Command Line Interface (CLI), known as Powershell. Third, you'll extract and compress files into a .zip archive in the GUI and CLI.

- Install Sublime Text using Windows GUI
- Extract files using 7-Zip and Powershell
- Install VLC using Windows Powershell
- Uninstall GIMP using Windows Powershell

Open ******VM******  as this is where you’ll be performing these steps in the lab. For this lab, we’re using Qwiklabs. Remember that if you use Azure to delete the resources at the end of the lab to save the credits of avoid a big bill at the end of the month ( 🥲 you really don’t want this surprise)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/f2ffe510-224b-4db8-be1c-d816a21f4d51/Untitled.png)

# **Install and uninstall software using Windows GUI**

**Installing Sublime Text**

First, you'll install the Sublime Text editor. Using Google Chrome, visit [https://www.sublimetext.com](https://www.sublimetext.com/) to download the latest version of Sublime Text. Once you have downloaded the file, open your "Downloads" folder under **C:\Users\Qwiklabs**\**Downloads**. You should see the installer, called "sublime_text_build_4126_x64_setup.exe". Double click the executable and the process should begin.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/4d9e1db6-af25-4df3-814f-43cda8d6d45c/Untitled.png)

Leave the folder location as default, just click on the **Next**  button to proceed with the installation.

Now, click on the **Install**  button. When the installation is finished, click the Search icon in the bottom-left of the taskbar, and start typing “Sublime Text” to search. This will bring up the **Sublime Text**
editor. (as shown below).

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/a3c2afd8-0d11-47c6-b707-a5508fbdb7ec/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/e5fe4f50-6205-41e4-977c-95e346474cfa/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/06becce0-59f6-4da2-a973-b3950436bd69/Untitled.png)

# **Extracting using 7-Zip**

7-Zip is a super useful program for working with archived or zipped files, and it's already been installed on your system. Using File Explorer navigate to "**C:\Users\Qwiklabs\Downloads**". This folder contains a .tar archive called "example.tar". You don't have permissions to extract files in this .tar file's current folder, so click-and-drag the file to the Desktop. After moving the file, you'll be prompted to confirm the move; click "Continue" to finish the move. Then, you can use it to extract the contents of the archive by right-clicking "example.tar" (now on the Desktop), hovering over "7-Zip", and clicking "Extract Here":

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/2a27001c-e94b-4f35-9b07-b0d4a65d1c04/Untitled.png)

Afterwards, you'll see the contents of the .tar file on the Desktop, alongside the archive:

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/26e028f1-7d4c-41ce-acda-4c9a9a9a2ae3/Untitled.png)

# **Archiving files**

Now you'll perform the other half of the process, bundling multiple files into a .zip archive. Navigate to **"C:\Users\Qwiklabs\Documents"** and find the three files named, "Earth", "Mercury", and "Venus":

[https://cdn.qwiklabs.com/W6czqlE0AKmABwXRfgQ0znK2TSV8jg5DOjH7zeNi0%2Fk%3D](https://cdn.qwiklabs.com/W6czqlE0AKmABwXRfgQ0znK2TSV8jg5DOjH7zeNi0%2Fk%3D)

**Archiving files with PowerShell**

Now you'll build multiple files into a .zip archive using PowerShell. Open Powershell and navigate to this folder. (Make sure you have administrative privileges enabled!). So, search for `Windows Powershell`, right-click it, and select **"Run as Administrator"**.

[https://cdn.qwiklabs.com/5AubM9PzO4npKI5zNrU7uj25wA%2BF6W7MHW%2BfPk33vBM%3D](https://cdn.qwiklabs.com/5AubM9PzO4npKI5zNrU7uj25wA%2BF6W7MHW%2BfPk33vBM%3D)

Now, Use the following command:

cd C:\Users\ **Qwiklabs**\Documents\

to navigate to the "Documents" folder. Once you're there, you can create a .zip archive (called Planets.zip) using this command:

Compress-Archive -Path Earth, Mercury, Venus Planets.zip

# I**nstall and uninstall software using Windows CLI**

**Installing VLC**

There are alternatives to manually downloading and running installers when you need to install or manage programs on Windows. To install or remove programs, you need administrative privileges. So, open `Windows Powershell` by searching for it in the Windows start menu, then right-click it and select "Run as Administrator".

In the `Windows Powershell` terminal, enter the following commands to download and install VLC media player.

$VLC_URL = "[https://get.videolan.org/vlc/last/win64/](https://get.videolan.org/vlc/last/win64/)"

$GET_HTML = Invoke-WebRequest  $VLC_URL

 

$FILE = $GET_HTML.Links |Select-Object 

@{Label='href';Expression={@{$true=$_*.href}*

*[$_*.href.EndsWith('win64.exe')]}} | 

Select-Object -ExpandProperty href

$URL = ($VLC_URL+$FILE)

$DOWNLOAD_DIR = "C:\users\’username’\Downloads\”

$OUTPUT_FILE = ($DOWNLOAD_DIR+$FILE)

(new-object System.Net.WebClient).DownloadFile($URL, $OUTPUT_FILE)

cmd.exe /c $OUTPUT_FILE /S

Once the installation process is successfully completed,  we can verify that VLC has successfully been installed with the following command:

Get-Package -Name *vlc***

# **Uninstalling GIMP**

You can use `Windows Powershell` to uninstall programs. If you've closed your PowerShell window, reopen it again by searching for it in the Start Menu, then right-clicking it and selecting "Run as Administrator".

You can uninstall GIMP, a photo editor, using this command:

cmd.exe /c "C:\Program Files\GIMP 2\uninst\unins000.exe" /VERYSILENT /NORESTART

Once the process finishes, GIMP will no longer be available on your system. You can verify this with the following command and notice that GIMP is not listed:

Get-Package

Congrats! We've successfully installed and uninstalled programs on Windows using both the GUI and CLI tools, as well as archived and unarchived .tar files.
