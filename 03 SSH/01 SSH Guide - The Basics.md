<h1>SSH Guide - The Basics</h1>

        
<br>
Your FTP &#x2F; SFTP &#x2F; SSH login information can be found on the Slot Details page for the relevant slot. Use this link in your Account Manager to access the relevant slot:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/slot_detail_link.png"><br>
<br>
You login information for the relevant slot will be shown here:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/slot_detail_ssh.png"><br>
<br>
<h2>Kitty SSH Client</h2><br>
<a href="http://www.9bis.net/kitty/?page=Download">Kitty SSH client</a><br>
<br>
<a href="http://www.fosshub.com/KiTTY.html">Main Kitty Download Page</a><br>
<br>
 <strong>Important note:</strong> You can rename <code>kitty.exe</code> to <code>putty.exe</code> and use it wherever an application has putty integration. For example, Bitkinex and WinSCP.<br>
<br>
<h2>Basic Connection</h2><br>
We need to force the <code>UTF-8</code> language option to avoid some visual issues when connecting. If you are having Unicode character issues it is because you forgot to set this here before connecting.<br>
<br>
<strong>1:</strong> Navigate to the <code>Window</code> panel.<br>
<br>
<strong>2:</strong> Select the <code>Translation</code> panel.<br>
<br>
<strong>3:</strong> Select <code>UTF-8</code> in the drop down menu.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Kitty%20-%20SSH%20-%20Private%20Keys%20-%20SSH%20tunnels/1.png"><br>
<br>
 <strong>Important note:</strong> This optional but recommended step will save your Feral username and SSH password for the session to connect without requiring you to enter this information.<br>
<br>
<strong>1:</strong> Navigate to the <code>Connection</code> panel.<br>
<br>
<strong>2:</strong> Select the <code>Data</code> panel.<br>
<br>
<strong>3:</strong> Enter your Feral username in the <code>Auto-login username</code> field.<br>
<br>
<strong>4:</strong> Enter your Feral FTP &#x2F; SFTP &#x2F; SSH Access password found in the slots details pages for the relevant slot into the <code>Auto-login password</code> field.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Kitty%20-%20SSH%20-%20Private%20Keys%20-%20SSH%20tunnels/2.png"><br>
<br>
<strong>1:</strong> Navigate to the <code>Session</code> panel if not already there.<br>
<br>
<strong>2:</strong> Enter the hostname of the Feral server that hosts your slot.<br>
<br>
<strong>3:</strong> The SSH port is always <code>22</code>.<br>
<br>
<strong>4:</strong> Make sure the <code>SSH</code> radio option is selected (it should be selected by default).<br>
<br>
<strong>5:</strong> Give this session a name for when we save so you can identify and load it after.<br>
<br>
<strong>6:</strong> Save this session with all the information you have provided and settings you have configured.<br>
<br>
 <strong>Important note:</strong> Make sure you have saved your session once you have provided all the core details.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Kitty%20-%20SSH%20-%20Private%20Keys%20-%20SSH%20tunnels/3.png"><br>
<br>
Once you have saved your&nbsp; new session then you would normally follow this process when opening KiTTY to work with saved sessions:<br>
<br>
<strong>1:</strong> Navigate to the <code>Session</code> panel if not already there (this panel is the default when opening KiTTY)<br>
<br>
<strong>2:</strong> Select the session you want to load<br>
<br>
<strong>3:</strong> Click on <code>Load</code> to load this session and all configurations associated with it.<br>
<br>
<strong>4:</strong> Click <code>Open</code> to start the connection.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Kitty%20-%20SSH%20-%20Private%20Keys%20-%20SSH%20tunnels/4.png"><br>
<br>
 <strong>Important note:</strong> Check you are connecting to the right host before accepting. If you connecting to the correct host and are asked to save the server&#x27;s host Key say <code>yes</code> and check and box that says to remember&#x2F;always do this.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Kitty%20-%20SSH%20-%20Private%20Keys%20-%20SSH%20tunnels/5.png"><br>
<br>
 <strong>Important note:</strong> Don&#x27;t forget to save this session after making any new changes.<br>
<br>
<h2>OS X - Connecting with Terminal</h2><br>
Mac OS X comes with its own implementation of OpenSSH, so you don&#x27;t need to install any third-party software to take advantage of the extra security SSH offers â€” just open a terminal window and jump in.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/macterminal1.png"><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/macterminal2.png"><br>
<br>
If you haven&#x27;t already created a dock icon for &quot;Terminal&quot; then&nbsp; go to the Applications folder, then Utilities from within that. Terminal is in the Utilities folder. Just drag it on to the Dock, and it&#x27;ll make a permanent Dock icon.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/terminalicon.png"><br>
<br>
<h2>OS X Built-in SSH Client</h2><br>
When you open the terminal you will see something like this:<br>
<br>
<img src="https://raw.githubusercontent.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/SSH%20Guide%20-%20The%20Basics/OS%20X/3.png"><br>
<br>
Now we enter the SSH command to connect to the slot, where <code>username</code> is your Feral username and <code>server</code> is the name of the server you wish to SSH into:<br>
<br>
<pre><code>ssh username@server.feralhosting.com</code></pre><br>
<img src="https://raw.githubusercontent.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/SSH%20Guide%20-%20The%20Basics/OS%20X/4.png"><br>
<br>
If this is the first time connecting to this host you will see something like this.<br>
<br>
<img src="https://raw.githubusercontent.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/SSH%20Guide%20-%20The%20Basics/OS%20X/5.png"><br>
<br>
Type <code>yes</code> to save the host&#x27;s key.<br>
<br>
<img src="https://raw.githubusercontent.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/SSH%20Guide%20-%20The%20Basics/OS%20X/6.png"><br>
<br>
Now enter your Feral SSH&#x2F;SFTP password at the prompt found on your slot details page for the relevant slot:<br>
<br>
<strong>Do not type it in</strong> â€” copy it (be careful not too introduce extra white spaces) paste it by pressing: <br>
<br>
<strong>command-v</strong> or a <strong>middle-click on a 3-button mouse</strong> to paste it in.<br>
<br>
<strong>There will be no visual response when you paste in your password</strong> â€” this is a security measure so that your password cannot be stolen by someone looking over your shoulder. Simply paste it and press <strong>enter</strong> to send the password to the server.<br>
<br>
<img src="https://raw.githubusercontent.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/SSH%20Guide%20-%20The%20Basics/OS%20X/7.png"><br>
<br>
At this point you should be logged into your Feral server and ready to execute commands in shell.<br>
<br>
After you have saved the host key and use the command shown in this FAQ it will look like this when connecting.<br>
<br>
<img src="https://raw.githubusercontent.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/SSH%20Guide%20-%20The%20Basics/OS%20X/8.png"><br>
<br>
You have now successfully connected to your slot via SSH using terminal on OS X.<br>
<br>

