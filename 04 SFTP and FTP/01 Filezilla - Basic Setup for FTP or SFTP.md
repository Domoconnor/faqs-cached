<h1>Filezilla - Basic Setup for FTP or SFTP</h1>

        
Your FTP &#x2F; SFTP &#x2F; SSH login information can be found on the Slot Details page for the relevant slot.<br>
<br>
Use this link in your Account Manager to access the relevant slot:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/slot_detail_link.png"><br>
<br>
You login information for the relevant slot will be shown here:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/slot_detail_ssh.png"><br>
<br>
<h2>Filezilla</h2><br>
This is a basic guide on connecting to your Feral slot using FTP&#x2F;SFTP with FileZilla.<br>
<br>
Please download and install Filezilla if you have not already done so.<br>
<br>
<a href="https://filezilla-project.org/download.php?show_all=1">Filezilla Client Download Page &#x2F; Multi platform</a><br>
<br>
Once you have installed Filezilla, run the application and you will be able to work through the images.<br>
<br>
<h2>The Layout explained:</h2><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SFTP%20and%20FTP/Filezilla%20-%20Basic%20Setup%20for%20FTP%20or%20SFTP/1.png"><br>
<br>
<h2>Accessing the Site Manager:</h2><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SFTP%20and%20FTP/Filezilla%20-%20Basic%20Setup%20for%20FTP%20or%20SFTP/2.png"><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SFTP%20and%20FTP/Filezilla%20-%20Basic%20Setup%20for%20FTP%20or%20SFTP/3.png"><br>
<br>
<h2>The Site Manager: Adding a New Site:</h2><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SFTP%20and%20FTP/Filezilla%20-%20Basic%20Setup%20for%20FTP%20or%20SFTP/5.png"><br>
<br>
<h2>Naming your new connection profile:</h2><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SFTP%20and%20FTP/Filezilla%20-%20Basic%20Setup%20for%20FTP%20or%20SFTP/6.png"><br>
<br>
<h2>If you wish to connect using unencrypted FTP use this image below or skip this image:</h2><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SFTP%20and%20FTP/Filezilla%20-%20Basic%20Setup%20for%20FTP%20or%20SFTP/7.png"><br>
<br>
<h2>If you wish to use encrypted SFTP to connect use this information scheme:</h2><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SFTP%20and%20FTP/Filezilla%20-%20Basic%20Setup%20for%20FTP%20or%20SFTP/8.png"><br>
<br>
<br>
<h2>Set UTF-8 to on (Required on Windows)</h2><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SFTP%20and%20FTP/Filezilla%20-%20Basic%20Setup%20for%20FTP%20or%20SFTP/utf.png"><br>
<br>
<h2>Connecting to your slot using this profile:</h2><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SFTP%20and%20FTP/Filezilla%20-%20Basic%20Setup%20for%20FTP%20or%20SFTP/9.png"><br>
<br>
 <strong>Important note:</strong> After clicking Connect or OK this site will now be saved to the Site Manager for future use or using quick connects as shown in image 3.<br>
<br>
You have now completed the basic steps for creating a profiles and connecting to your slot using Filezilla. You can stop here.<br>
<br>
<h2>Optional Step - Using a public&#x2F;private key pair:</h2><br>
 <strong>Important note:</strong> This step is OPTIONAL and does not need to be completed to access your slot.<br>
<br>
If you need to use a keyfile for connecting please follow the steps in these images below for adding your key to Filezilla according to these rules:<br>
<br>
<strong>1:</strong> Your keyfile must be in the Putty tools <code>.PPK</code> format on Windows. See this guide for keyfile creation:<br>
<br>
<a href="https://www.feralhosting.com/faq/view?question=13">Setting up Public Key Authentication for Password-less Login</a><br>
<br>
<strong>2:</strong> Filezilla does not directly support passphrase protected keyfiles, PAGEANT must be used in windows to load the passphrase into memory. See this guide: <a href="https://www.feralhosting.com/faq/view?question=241">PAGEANT</a><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SFTP%20and%20FTP/Filezilla%20-%20Basic%20Setup%20for%20FTP%20or%20SFTP/10.png"><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SFTP%20and%20FTP/Filezilla%20-%20Basic%20Setup%20for%20FTP%20or%20SFTP/11.png"><br>
<br>
