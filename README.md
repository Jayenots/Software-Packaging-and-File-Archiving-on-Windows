# Software-Packaging-and-File-Archiving-on-Windows

<p align="center">
<a href="https://imgur.com/xw4G10D"><img src="https://i.imgur.com/xw4G10D.jpg" title="source: imgur.com" /></a>
</p>

In this lab, we'll learn how to install and remove software in the Windows GUI and CLI, and work with zipped files. We'll install a text editor, called Sublime Text, and extract/un-extract .tar files. We'll also use *Windows Powershell*  to install and uninstall programs on Windows.


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Computer)
- Remote Desktop
- Qwiklabs

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites and Tasks</h2>
You have a bunch of tasks for this lab. First, you'll install and remove software using the Windows graphical user-interface (GUI). Second, you'll remove and install software using the Windows Command Line Interface (CLI), known as Powershell. Third, you'll extract and compress files into a .zip archive in the GUI and CLI.

- Install Sublime Text using Windows GUI
- Extract files using 7-Zip and Powershell
- Install VLC using Windows Powershell
- Uninstall GIMP using Windows Powershell

Open the virtual manchine as this is where you’ll be performing these steps in the lab. For this lab, we’re using Qwiklabs. Remember that if you use Azure to delete the resources at the end of the lab to save the credits of avoid a big bill at the end of the month ( 🥲 you really don’t want this surprise)

<p align="center">
<a href="https://imgur.com/dR6u77f"><img src="https://i.imgur.com/dR6u77f.png" title="source: imgur.com" /></a>
</p>

**Install and uninstall software using Windows GUI**

<h2>Installing Sublime Text</h2>

First, you'll install the Sublime Text editor. Using Google Chrome, visit [https://www.sublimetext.com](https://www.sublimetext.com/) to download the latest version of Sublime Text. Once you have downloaded the file, open your "Downloads" folder under **C:\Users\Qwiklabs\Downloads**. You should see the installer, called "sublime_text_build_4126_x64_setup.exe". Double click the executable and the process should begin.

<p align="center">
<a href="https://imgur.com/usA0Qsj"><img src="https://i.imgur.com/usA0Qsj.png" title="source: imgur.com" /></a>
</p>
 
Leave the folder location as default, just click on the **Next**  button to proceed with the installation.

Now, click on the **Install**  button. When the installation is finished, click the Search icon in the bottom-left of the taskbar, and start typing “Sublime Text” to search. This will bring up the **Sublime Text** editor. (as shown below). This version is old so it may ask you to update after completion.

<p align="center">
<a href="https://imgur.com/YH4q0c1"><img src="https://i.imgur.com/YH4q0c1.png" title="source: imgur.com" /></a>
<a href="https://imgur.com/c8Ll2Dt"><img src="https://i.imgur.com/c8Ll2Dt.png" title="source: imgur.com" /></a>
<a href="https://imgur.com/JjVoDLl"><img src="https://i.imgur.com/JjVoDLl.png" title="source: imgur.com" /></a>
</p>
 
<h2>Extracting using 7-Zip</h2>

7-Zip is a super useful program for working with archived or zipped files, and it's already been installed on your system. Using File Explorer navigate to "**C:\Users\Qwiklabs\Downloads**". This folder contains a .tar archive called "example.tar". You don't have permissions to extract files in this .tar file's current folder, so click-and-drag the file to the Desktop. After moving the file, you'll be prompted to confirm the move; click "Continue" to finish the move. Then, you can use it to extract the contents of the archive by right-clicking "example.tar" (now on the Desktop), hovering over "7-Zip", and clicking "Extract Here":

<p align="center">
<a href="https://imgur.com/h2lGUmR"><img src="https://i.imgur.com/h2lGUmR.png" title="source: imgur.com" /></a>
</p>
 
Afterwards, you'll see the contents of the .tar file on the Desktop, alongside the archive:

<p align="center">
<a href="https://imgur.com/h6X4YWE"><img src="https://i.imgur.com/h6X4YWE.png" title="source: imgur.com" /></a>
</p>
 
# **Archiving files**

Now you'll perform the other half of the process, bundling multiple files into a .zip archive. Navigate to **"C:\Users\Qwiklabs\Documents"** and find the three files named, "Earth", "Mercury", and "Venus":

<p align="center">
<a href="https://imgur.com/eGR7aQN"><img src="https://i.imgur.com/eGR7aQN.png" title="source: imgur.com" /></a>
</P>
 
**Archiving files with PowerShell**

Now you'll build multiple files into a .zip archive using PowerShell. Open Powershell and navigate to this folder. (Make sure you have administrative privileges enabled!). So, search for `Windows Powershell`, right-click it, and select **"Run as Administrator"**.

<p align="center">
<a href="https://imgur.com/ZjdRL5Q"><img src="https://i.imgur.com/ZjdRL5Q.png" title="source: imgur.com" /></a>
</p>
 
Now, Use the following command:

cd C:\Users\Qwiklabs\Documents\

to navigate to the "Documents" folder. Once you're there, you can create a .zip archive (called Planets.zip) using this command:

Compress-Archive -Path Earth, Mercury, Venus Planets.zip**Install and uninstall software using Windows CLI**

**Installing VLC**

There are alternatives to manually downloading and running installers when you need to install or manage programs on Windows. To install or remove programs, you need administrative privileges. So, open `Windows Powershell` by searching for it in the Windows start menu, then right-click it and select "Run as Administrator".

In the `Windows Powershell` terminal, enter the following commands to download and install VLC media player.

👉$VLC_URL = "[https://get.videolan.org/vlc/last/win64/](https://get.videolan.org/vlc/last/win64/)"

👉$GET_HTML = Invoke-WebRequest  $VLC_URL

👉$FILE = $GET_HTML.Links |Select-Object@{Label='href';Expression={@{$true=$_*.href}* *[$_*.href.EndsWith('win64.exe')]}} |Select-Object -ExpandProperty href

👉$URL = ($VLC_URL+$FILE)

👉$DOWNLOAD_DIR = "C:\users\’username’\Downloads\”

👉$OUTPUT_FILE = ($DOWNLOAD_DIR+$FILE)

👉(new-object System.Net.WebClient).DownloadFile($URL, $OUTPUT_FILE)

👉cmd.exe /c $OUTPUT_FILE /S

<p align="center">
<a href="https://imgur.com/bqpprP4"><img src="https://i.imgur.com/bqpprP4.png" title="source: imgur.com" /></a>
</p>
 
Once the installation process is successfully completed,  we can verify that VLC has successfully been installed with the following command:

Get-Package -Name *vlc***
 As you can see I had issues with the typing in of commands ( will be working on that), especially with the spaces ( it's the space, missing or extra, that'll get you)

# **Uninstalling GIMP**

<p align="center">
<a href="https://imgur.com/gRbycTF"><img src="https://i.imgur.com/gRbycTF.png" title="source: imgur.com" /></a>
</p>

You can use `Windows Powershell` to uninstall programs. If you've closed your PowerShell window, reopen it again by searching for it in the Start Menu, then right-clicking it and selecting "Run as Administrator".

You can uninstall GIMP, a photo editor, using this command:

cmd.exe /c "C:\Program Files\GIMP 2\uninst\unins000.exe" /VERYSILENT /NORESTART

Once the process finishes, GIMP will no longer be available on your system. You can verify this with the following command and notice that GIMP is not listed:

<p align="center">
<a href="https://imgur.com/T86eRbn"><img src="https://i.imgur.com/T86eRbn.png" title="source: imgur.com" /></a>
</p>
 
Get-Package

<p align="center">
<a href="https://imgur.com/xaYYc8E"><img src="https://i.imgur.com/xaYYc8E.png" title="source: imgur.com" /></a>
</p>
 
Congrats! We've successfully installed and uninstalled programs on Windows using both the GUI and CLI tools, as well as archived and unarchived .tar files.
