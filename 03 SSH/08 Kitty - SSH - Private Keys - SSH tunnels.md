<h1>Kitty - SSH - Private Keys - SSH tunnels</h1>

        
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
<h2>Information</h2><br>
Completing the whole guide is not Required. To use Kitty to connect to your slot you only need to complete the steps in Part 1 of this FAQ. This will use Kitty to connect in the traditional way you would when using putty.<br>
<br>
<h2>Part 1: Basic Connection</h2><br>
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
 <strong>Important note:</strong> Check you are connecting to the right host before accepting. If you connecting to the correct host and are asked to save the HOSTs Key say <code>yes</code> and check and box that says to remember&#x2F;always do this.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Kitty%20-%20SSH%20-%20Private%20Keys%20-%20SSH%20tunnels/5.png"><br>
<br>
 <strong>Important note:</strong> Don&#x27;t forget to save this session after making any new changes.<br>
<br>
<h2>Part 2: Using a&nbsp; putty format ppk keyfile.</h2><br>
This guide assumes you have created a private key according to this <strong>Guide :</strong> <a href="https://www.feralhosting.com/faq/view?question=13">Setting up Public Key Authentication for Password-less Login</a><br>
<br>
<strong>1:</strong> Navigate to the <code>Session</code> panel if not already there (this panel is the default when opening KiTTY)<br>
<strong>2:</strong> Select the session you want to load<br>
<strong>3:</strong> Click on <code>Load</code> to load this session and all configurations associated with it.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Kitty%20-%20SSH%20-%20Private%20Keys%20-%20SSH%20tunnels/6.png"><br>
<br>
<strong>1:</strong> Navigate to the <code>Connection</code> panel.<br>
<strong>2:</strong> Navigate down to the `SSH Panel.<br>
<strong>3:</strong> Select the <code>Auth</code> panel.<br>
<strong>4:</strong> Click on <code>Browse</code> to look for and load a <code>ppk</code> format keyfile.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Kitty%20-%20SSH%20-%20Private%20Keys%20-%20SSH%20tunnels/7.png"><br>
<br>
Once loaded into kitty the path to the keyfile will be shown.<br>
<br>
<strong>1:</strong> Once loaded into kitty the path to the keyfile will be shown in the field.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Kitty%20-%20SSH%20-%20Private%20Keys%20-%20SSH%20tunnels/8.png"><br>
<br>
 <strong>Important note:</strong> Don&#x27;t forget to save this session after making any new changes.<br>
<br>
<strong>1:</strong> Navigate back to the <code>Session</code> panel.<br>
<strong>2:</strong> Select the session you want to save and merge the new configuration settings with.<br>
<strong>3:</strong> Click on <code>Save</code> to have these new settings saved to the selected session.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Kitty%20-%20SSH%20-%20Private%20Keys%20-%20SSH%20tunnels/9.png"><br>
<br>
<h2>Part 3: Creating an SSH Tunnel to use as a local SOCKS proxy.</h2><br>
 <strong>Important note:</strong> You can add and create more than one tunnel per session if needed.<br>
<br>
<strong>1:</strong> Navigate to the <code>Session</code> panel if not already there (this panel is the default when opening KiTTY)<br>
<strong>2:</strong> Select the session you want to load<br>
<strong>3:</strong> Click on <code>Load</code> to load this session and all configurations associated with it.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Kitty%20-%20SSH%20-%20Private%20Keys%20-%20SSH%20tunnels/10.png"><br>
<br>
<strong>1:</strong> Navigate to the <code>Connection</code> panel.<br>
<strong>2:</strong> Navigate down to the `SSH Panel.<br>
<strong>3:</strong> Select the <code>Tunnels</code> panel.<br>
<strong>4:</strong> Configure the new dynamic forwarded port that will act as a local SOCKS proxy (see next image for details)<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Kitty%20-%20SSH%20-%20Private%20Keys%20-%20SSH%20tunnels/11.png"><br>
<br>
<strong>1:</strong> Select the <code>Auto</code> radio (this should already be selected by default)<br>
<strong>2:</strong> Select the <code>Dynamic</code> radio<br>
<strong>3:</strong> Select and enter a port between the range of <code>10001</code> to <code>49999</code><br>
<strong>4:</strong> Click <code>Add</code> to add this SSH tunnel.<br>
<strong>5:</strong> Once added you will see the tunnel listed in the <code>Forwarded ports</code> window.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Kitty%20-%20SSH%20-%20Private%20Keys%20-%20SSH%20tunnels/12.png"><br>
<br>
 <strong>Important note:</strong> Don&#x27;t forget to save this session after making any new changes.<br>
<br>
<strong>1:</strong> Navigate back to the <code>Session</code> panel.<br>
<strong>2:</strong> Select the session you want to save and merge the new configuration settings with.<br>
<strong>3:</strong> Click on <code>Save</code> to have these new settings saved to the selected session.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Kitty%20-%20SSH%20-%20Private%20Keys%20-%20SSH%20tunnels/13.png"><br>
<br>

