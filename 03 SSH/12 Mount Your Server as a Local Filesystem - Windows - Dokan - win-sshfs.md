<h1>Mount Your Server as a Local Filesystem - Windows - Dokan - win-sshfs</h1>

        
This Guide will allow you to mount your Feral slots remote file system as a local file system through SFTP.<br>
<br>
 <strong>Recommended Method:</strong> Install Dokan Libraries and then use win-sshfs.<br>
<br>
To do this you need meet these requirements:<br>
<br>
<strong>1:</strong> You have a Feral slot that has been activated and you can SSH to. This means that your FTP&#x2F;SFTP&#x2F;SSH user name and password have been set-up and and are visible from You can do this from the <code>Install Software</code> link in your <a href="https://www.feralhosting.com/manager/">Account Manager</a><br>
<br>
You login information for the relevant slot will be shown here:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/slot_detail_ssh.png"><br>
<br>
<strong>2:</strong> You will need to install the Visual C++ Redistributable Packages for Visual Studio 2013 to make sure Dokan will work.<br>
<br>
<a href="http://www.microsoft.com/en-us/download/details.aspx?id=40784">Visual C++ Redistributable Packages for Visual Studio 2013</a><br>
<br>
Download and install <code>vcredist_x86.exe</code><br>
Download and install <code>vcredist_x64.exe</code><br>
<br>
 <strong>Important note:</strong> Install the x86 regardless of whether your system is x86 or you will get an error about <code>MSVCR120.dll</code> not being found<br>
<br>
Now continue to download and install the Dokan library.<br>
<br>
<h3>Step 1</h3><br>
<strong>1:</strong> Remove the previous Dokan library if you had it installed via the Add or Remove programs option.<br>
<br>
<strong>2:</strong> Download and install the current latest release from this URL:&nbsp; <a href="https://github.com/dokan-dev/dokany/releases">Dokan Libraries</a>.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Mount%20Your%20Server%20as%20a%20Local%20Filesystem%20-%20Windows%20-%20Dokan%20-%20win-sshfs/Dokan/dokan-1.png"><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Mount%20Your%20Server%20as%20a%20Local%20Filesystem%20-%20Windows%20-%20Dokan%20-%20win-sshfs/Dokan/dokan-2.png"><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Mount%20Your%20Server%20as%20a%20Local%20Filesystem%20-%20Windows%20-%20Dokan%20-%20win-sshfs/Dokan/dokan-3.png"><br>
<br>
Reboot if asked.<br>
<br>
You can now jump to the win-sshfs section.<br>
<br>
<h3>Step 2</h3><br>
This step requires some pre requisites in order to be installable:<br>
<br>
<strong>1:</strong> You will need to install <code>Net 2.0</code> if you do not already have it. It comes as part of the <code>Net 3.5</code> web installer linked here:<br>
<br>
<a href="http://www.microsoft.com/en-us/download/details.aspx?id=21">Net 3.5 x86 and x64</a><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Mount%20Your%20Server%20as%20a%20Local%20Filesystem%20-%20Windows%20-%20Dokan%20-%20win-sshfs/Dokan/sshfs.0.2.0%201.png"><br>
<br>
<strong>2:</strong> You must install this Visual C++ 2005 SP1 x86 in order to install Dokan sshfs 0201226. It does not matter if you are on a x64 OS. You must have this x86 runtime.<br>
<br>
<a href="http://www.microsoft.com/en-gb/download/details.aspx?id=5638">Microsoft Visual C++ 2005 SP1 Redistributable Package (x86)</a><br>
<br>
If you do not do this you will get this error when trying to install sshfs 0.2.0:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Mount%20Your%20Server%20as%20a%20Local%20Filesystem%20-%20Windows%20-%20Dokan%20-%20win-sshfs/Dokan/sshfs.0.2.0%20error.png"><br>
<br>
Once you have installed both of these you can download and install the sshfs 0.2.0 executable.<br>
<br>
<a href="http://ftp.psu.ac.th/pub/dokan/dokan-sshfs-0201226.zip">Dokan sshfs 0201226</a>&nbsp; install this program. (it requires the Dokan library is installed)<br>
<br>
<h3>Step 3</h3><br>
Download and unpack the files:<br>
<br>
<a href="http://ftp.psu.ac.th/pub/dokan/dokan-sshfs-0.6.0.zip">Dokan sshfs 0.60</a>:&nbsp; <br>
<br>
We will use this to update the dokan-sshfs-0201226 to 0.6.0, Why will we do this? <br>
<br>
&quot;This package doesn&#x27;t include installer and Explorer extensions which add context menu to Dokan drive and permission setting dialog. If you want to support those features, please install dokan-sshfs-0.2.0.1226 and overwrite DokanNet.dll and DokanSSHFS.exe files by dokan-sshfs-0.6.0&quot;.<br>
<br>
Now browse to the location you installed it to (if no shortcut is created) for example:<br>
<br>
<pre><code>C:\Program Files\Dokan\DokanSSHFS\</code></pre><br>
Or<br>
<br>
<pre><code>C:\Program Files (x86)\Dokan\DokanSSHFS\</code></pre><br>
You will need to copy the files from the Dokan sshfs 0.6.0 to this folder and overwrite the files.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Mount%20Your%20Server%20as%20a%20Local%20Filesystem%20-%20Windows%20-%20Dokan%20-%20win-sshfs/Dokan/update.0.2.0%201.png"><br>
<br>
Confirm the overwrite action:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Mount%20Your%20Server%20as%20a%20Local%20Filesystem%20-%20Windows%20-%20Dokan%20-%20win-sshfs/Dokan/update.0.2.0%202.png"><br>
<br>
These are the files that have been updated:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Mount%20Your%20Server%20as%20a%20Local%20Filesystem%20-%20Windows%20-%20Dokan%20-%20win-sshfs/Dokan/update.0.2.0%203.png"><br>
<br>
<h3>Step 4</h3><br>
Then run the DokanSSHFS.exe&nbsp; located in this folder and enter your details in the windows that pops up:<br>
<br>
One the program starts you will see something like this:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Mount%20Your%20Server%20as%20a%20Local%20Filesystem%20-%20Windows%20-%20Dokan%20-%20win-sshfs/Dokan/mount.png"><br>
<br>
<strong>Important note:</strong> you need to specify the full path to the root of your home directory. So it will be something like:<br>
<br>
<pre><code>&#x2F;media&#x2F;DiskID&#x2F;home&#x2F;yourusername</code></pre><br>
If you want to use a keyfile it will need to be in the OpenSSH format. To convert your PuTTy PPK file to the OpenSSH format do this:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Mount%20Your%20Server%20as%20a%20Local%20Filesystem%20-%20Windows%20-%20Dokan%20-%20win-sshfs/Dokan/puttygen.png"><br>
<br>
Upon connecting Dokan will tell you that is has started SFTP and then you should see you mounted volume in My computer with the driver letter assigned in the settings. If you get an error about assigning the driver letter check that the Dokanmounter service is running.<br>
<br>
this was done on: <br>
<br>
Windows 7 x86 &amp; x64 with no compatibility settings used. Net 2 and 3.5 are included in an updated Windows 7. You must install Microsoft Visual C++ 2005 SP1 Redistributable Package (x86)<br>
<br>
Windows 8 x86 &amp; x64 with Windows 7 compatibility settings used. Net 2 and 3.5 must be installed manually. You must install Microsoft Visual C++ 2005 SP1 Redistributable Package (x86)<br>
<br>
<br>
<h3>win-sshfs</h3><br>
<strong>Step 1:</strong><br>
<br>
Make sure you have downloaded and installed the Dokan 0.6.0 Libraries. You can skip this step if you have done this previously.<br>
<br>
<strong>Important note:</strong> Windows 8 users must use Windows 7 compatibility mode on this installer.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Mount%20Your%20Server%20as%20a%20Local%20Filesystem%20-%20Windows%20-%20Dokan%20-%20win-sshfs/Dokan/compat%201.png"><br>
<br>
Download and install this: <br>
<br>
<a href="http://ftp.psu.ac.th/pub/dokan/DokanInstall_0.6.0.exe">Dokan Libraries</a> you will need to install this first, reboot if asked.<br>
<br>
<strong>Important note:</strong> If you see this box on Windows 8 just click &quot;This program ran correctly&quot; option:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Mount%20Your%20Server%20as%20a%20Local%20Filesystem%20-%20Windows%20-%20Dokan%20-%20win-sshfs/Dokan/compat%202.png"><br>
<br>
<strong>Step 2:</strong><br>
<br>
Download and install win-sshfs:<br>
<br>
<a href="http://code.google.com/p/win-sshfs/downloads/list">Download win-sshfs</a><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Mount%20Your%20Server%20as%20a%20Local%20Filesystem%20-%20Windows%20-%20Dokan%20-%20win-sshfs/win-sshfs/1.png"><br>
<br>
You will need to meet all these requirements to install and use win_sshs<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Mount%20Your%20Server%20as%20a%20Local%20Filesystem%20-%20Windows%20-%20Dokan%20-%20win-sshfs/win-sshfs/2.png"><br>
<br>
IF you see this box when installing make sure to &quot;Overwrite&quot; the destination file.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Mount%20Your%20Server%20as%20a%20Local%20Filesystem%20-%20Windows%20-%20Dokan%20-%20win-sshfs/win-sshfs/overwrite.png"><br>
<br>
If you do not have Net Framework 4 installed you can get it from here.<br>
<br>
<a href="http://www.microsoft.com/en-gb/download/details.aspx?id=17851">Net Framework 4 Web Installer</a><br>
<br>
<strong>Step 3:</strong><br>
<br>
Once install and running you will see the icon in the tray. Right click on it and click on &quot;Show Manager&quot;:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Mount%20Your%20Server%20as%20a%20Local%20Filesystem%20-%20Windows%20-%20Dokan%20-%20win-sshfs/win-sshfs/2.5.png"><br>
<br>
This is the default screen you will see, click on &quot;Add&quot;<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Mount%20Your%20Server%20as%20a%20Local%20Filesystem%20-%20Windows%20-%20Dokan%20-%20win-sshfs/win-sshfs/3.png"><br>
<br>
Fill in your information as shown in the image. The &quot;Save&quot; before trying to mount:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Mount%20Your%20Server%20as%20a%20Local%20Filesystem%20-%20Windows%20-%20Dokan%20-%20win-sshfs/win-sshfs/4.png"><br>
<br>
Once you have saved you will see something like this. Now you can try to &quot;Mount&quot; the drive.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Mount%20Your%20Server%20as%20a%20Local%20Filesystem%20-%20Windows%20-%20Dokan%20-%20win-sshfs/win-sshfs/5.png"><br>
<br>
If successful with no programs errors, the drive will now be available to access and use. Click &quot;Unmount&quot; to unmount the drive<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Mount%20Your%20Server%20as%20a%20Local%20Filesystem%20-%20Windows%20-%20Dokan%20-%20win-sshfs/win-sshfs/6.png"><br>
<br>
<strong>Important note:</strong> You can create and use multiple connection profiles and use them as the same time. Select each profile and &quot;Mount&quot; the server.<br>
<br>
