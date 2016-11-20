<h1>Dropbox - How to install</h1>

        
In SSH do the commands described in this FAQ. If you do not know how to SSH into your slot use this FAQ: <a href="https://www.feralhosting.com/faq/view?question=12">SSH basics - Putty</a><br>
<br>
Your FTP &#x2F; SFTP &#x2F; SSH login information can be found on the Slot Details page for the relevant slot. Use this link in your Account Manager to access the relevant slot:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/slot_detail_link.png"><br>
<br>
You login information for the relevant slot will be shown here:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/slot_detail_ssh.png"><br>
<br>
<h2>Download Dropbox to your serve</h2><br>
This is a basic guide downloading and installing Dropbox onto your slot and syncing with an account.<br>
<br>
In SSH do these commands. Use this faq if you do not know how to SSH into your slot: <a href="https://www.feralhosting.com/faq/view?question=12">SSH basics - Putty</a><br>
<br>
<pre><code>mkdir -p ~&#x2F;bin &amp;&amp; bash
wget -qO ~&#x2F;dropbox.tar.gz &quot;<a href="http://www.dropbox.com/download/?plat=lnx.x86_64">http:&#x2F;&#x2F;www.dropbox.com&#x2F;download&#x2F;?plat=lnx.x86_64</a>&quot; &amp;&amp; tar -xzf dropbox.tar.gz
wget -qO ~&#x2F;bin&#x2F;dropbox.py &quot;<a href="http://www.dropbox.com/download?dl=packages/dropbox.py">http:&#x2F;&#x2F;www.dropbox.com&#x2F;download?dl=packages&#x2F;dropbox.py</a>&quot; &amp;&amp; chmod 700 ~&#x2F;bin&#x2F;dropbox.py
source ~&#x2F;.bashrc &amp;&amp; source ~&#x2F;.profile
rm -f ~&#x2F;dropbox.tar.gz</code></pre><br>
<h2>Linking to your dropbox account</h2><br>
If you&#x27;re running Dropbox on your server for the first time you will have to interact with the process to get a special URL used to link your accounts. You&#x27;ll then be asked to copy and paste the URL link into a web browser:<br>
<br>
When you paste this link you will be asked to<br>
<br>
<strong>1:</strong> Sign in or create a new account if you do not have one<br>
<br>
Then<br>
<br>
<strong>2:</strong> Add&#x2F;Link your server to an existing account with a password confirmation.<br>
<br>
Run these commands to link to your drop box account:<br>
<br>
<strong>Important note:</strong> if you have already linked your account you can skip this command and use the start and send to background command below.<br>
<br>
<pre><code>HOME=$HOME&#x2F; ~&#x2F;.dropbox-dist&#x2F;dropboxd</code></pre><br>
<br>
If you encounter this error message:<br>
&#x27;&#x27;Couldn&#x27;t start Dropbox.<br>
This is usually because of a permissions error. Storing your home folder on a network share can also cause an error.<br>
<br>
Get more help at <a href="https://www.dropbox.com/c/help/permissions_error">https:&#x2F;&#x2F;www.dropbox.com&#x2F;c&#x2F;help&#x2F;permissions_error</a>&#x27;&#x27;<br>
it&#x27;s possible that you may have to change the above command into:<br>
<pre><code>LC_ALL=&quot;en_US.UTF-8&quot; LANGUAGE=&quot;en_US.UTF-8&quot; HOME=$HOME&#x2F; ~&#x2F;.dropbox-dist&#x2F;dropboxd</code></pre><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Software/Dropbox%20-%20How%20to%20install/firstrun.png"><br>
<br>
Copy and paste the link into a browser and follow the instructions to link your account.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Software/Dropbox%20-%20How%20to%20install/success.png"><br>
<br>
Dropbox is now successfully installed and linked to your account. You are ready to start using it. You default dropbox folder is located at <code>~&#x2F;Dropbox</code><br>
<br>
Close and kill this process by pressing, then holding, <code>CTRL</code> then press <code>c</code>. We needed to interact with the process to link our account but this step is now complete. So we want our terminal back and the process running as a background process.<br>
<br>
We will now restart the daemon and send it to the background as process.<br>
<br>
<pre><code>HOME=$HOME&#x2F; ~&#x2F;.dropbox-dist&#x2F;dropboxd &amp;</code></pre><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Software/Dropbox%20-%20How%20to%20install/firstinstance.png"><br>
<br>
And that is it. Dropbox is running in the background syncing your files.<br>
<br>
<h2>Multiple Dropbox accounts simultaneously</h2><br>
You can run multiple daemons linking different accounts at the same time.<br>
<br>
First, you will need to create a folder where you want your alternate dropbox folder to be located.<br>
<br>
The default dropbox is already using our <code>~&#x2F;</code> or home directory so we need to specify another using the command below:<br>
<br>
<pre><code>mkdir -p ~&#x2F;dropbox2</code></pre><br>
Inside this folder the following command will create the <code>Dropbox</code> and <code>.dropbox</code> folders for this link.<br>
<br>
Second we must now link this process to your other dropbox account. We specify the folder we created above as the new <code>HOME</code>:<br>
<br>
<strong>Important note:</strong> if you have already linked your account you can skip this command and use the start and send to background command below.<br>
<br>
<pre><code>HOME=$HOME&#x2F;dropbox2 ~&#x2F;.dropbox-dist&#x2F;dropboxd</code></pre><br>
Now you will have to follow the same process as previously described to link this account. Once it is done close and kill this process by pressing, then holding, <code>CTRL</code> then press <code>c</code>.<br>
<br>
Now restart is as a process in the background:<br>
<br>
<pre><code>HOME=$HOME&#x2F;dropbox2 ~&#x2F;.dropbox-dist&#x2F;dropboxd &amp;</code></pre><br>
<h2>Extra stuff:</h2><br>
<strong>It is recommended you start the processes using the commands above.</strong>&nbsp; and only use the <code>dropbox.py</code> to complete other tasks.<br>
<br>
We have already installed the Dropbox CLI (Command-line Interface) to your ~&#x2F;bin directory ready for use.<br>
<br>
<pre><code>dropbox.py help</code></pre><br>
Your new dropbox folder is located at:<br>
<br>
<pre><code>~&#x2F;Dropbox</code></pre><br>
Running Dropbox as a process:<br>
<br>
<pre><code>dropbox.py start</code></pre><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Software/Dropbox%20-%20How%20to%20install/start.png"><br>
<br>
You can get helpf or anyone of these arguments by doing this:<br>
<br>
<pre><code>dropbox.py help something</code></pre><br>
For example:<br>
<br>
<pre><code>dropbox.py help exclude</code></pre><br>
A list dropbox.py arguments, returned from the <code>dropbox.py help</code> command<br>
<br>
<pre><code> status&nbsp;  get current status of the dropboxd
 help&nbsp; &nbsp;  provide help
 puburl&nbsp;  get public url of a file in your dropbox
 stop&nbsp; &nbsp;  stop dropboxd
 running&nbsp; return whether dropbox is running
 start&nbsp; &nbsp; start dropboxd
 filestatus&nbsp;  get current sync status of one or more files
 ls&nbsp; &nbsp; &nbsp;  list directory contents with current sync status
 autostartautomatically start dropbox at login
 exclude&nbsp; ignores&#x2F;excludes a directory from syncing
 lansync&nbsp; enables or disables LAN sync</code></pre><br>
<h2>Useful Links</h2><br>
<a href="http://www.dropboxwiki.com/Using_Dropbox_CLI">Using_Dropbox_CLI</a><br>
<br>
