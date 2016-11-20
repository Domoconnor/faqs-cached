<h1>ZNC - Basic Setup</h1>

        
ZNC is a portable, open source IRC bouncer written in C++.<br>
<br>
Current latest stable version of ZNC is: <code>1.6</code><br>
<br>
In SSH do the commands described in this FAQ. If you do not know how to SSH into your slot use this FAQ: <a href="https://www.feralhosting.com/faq/view?question=12">SSH basics - Putty</a><br>
<br>
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
<h3>Upgrading:</h3><br>
When upgrading from a previous version of <code>znc</code> you do this:<br>
<br>
Shutdown the <code>znc</code> server properly using the server command (see below for details):<br>
<br>
<pre><code>&#x2F;znc shutdown</code></pre><br>
Once the server is shutdown simply follow the installation steps in the installation section below to update the core server.<br>
<br>
When the core server has finished building and is installed then update and install any extra modules like the <code>znc push</code> you may be using so they are compiled for this new version of <code>znc</code><br>
<br>
Now start the new server in SSH using the command:<br>
<br>
<pre><code>znc</code></pre><br>
<h3>Your configs</h3><br>
If you update using the manual method your previous configuration file will be backed up and&nbsp; znc will create a new version and merge the old data with the new configuration file.<br>
<br>
If you install znc using the script your configuration file will be backed up in the <code>~&#x2F;.znc&#x2F;configs&#x2F;</code> and then a new config will be created from a template. You can then merge in your details manually.<br>
<br>
<h2>ZNC installation</h2><br>
<h3>Automatic basic install</h3><br>
This script essentially performs the basic install according to the steps below.<br>
<br>
<br>
<br>
<pre><code>wget -qO ~&#x2F;install.znc <a href="http://git.io/vfKaT">http:&#x2F;&#x2F;git.io&#x2F;vfKaT</a> &amp;&amp; bash ~&#x2F;install.znc</code></pre><br>
<h3>Manual install</h3><br>
Use this command to create the <code>~&#x2F;bin</code> directory and reload your shell for this change to take effect.<br>
<br>
<pre><code>mkdir -p ~&#x2F;bin &amp;&amp; bash</code></pre><br>
<h3>Download and configure</h3><br>
Download and configure <code>znc</code> using these commands:<br>
<br>
<pre><code>wget -qO ~&#x2F;znc.tar.gz <a href="http://znc.in/releases/znc-latest.tar.gz">http:&#x2F;&#x2F;znc.in&#x2F;releases&#x2F;znc-latest.tar.gz</a>
tar xf ~&#x2F;znc.tar.gz &amp;&amp; cd ~&#x2F;znc-1.*
.&#x2F;configure --prefix=$HOME</code></pre><br>
Now we need to check something before we continue. If you require extended charset support you will need to have a dependency installed. After running the configure command and it has completed you can check to see if there is charset support.<br>
<br>
 <strong>Important note:</strong> This dependency is not required to successfully build and use ZNC 1.6. It just means that without it certain charset specific option in the webadmin will be greyed out and unavailable to the admin&#x2F;user when configuring networks.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Software/ZNC%20-%20Basic%20Setup/config.png"><br>
<br>
If you require this optional dependency please <a href="https://www.feralhosting.com/manager/tickets/new">open a ticket</a> and ask for the dependency by copy and pasting this into a ticket:<br>
<br>
<pre><code>Please can you install the ZNC 1.6 dependency for charset

<a href="https://packages.debian.org/wheezy/libicu-dev">https:&#x2F;&#x2F;packages.debian.org&#x2F;wheezy&#x2F;libicu-dev</a>

apt-get install libicu-dev

Thank you.</code></pre><br>
<h3>Build ZNC:</h3><br>
<pre><code>make &amp;&amp; make install
cd &amp;&amp; rm -rf znc{-1.*,.tar.gz}</code></pre><br>
Once it is installed and ready we can start to configure <code>znc</code> using this command:<br>
<br>
<pre><code>znc --makeconf</code></pre><br>
If you get a <code>command not found</code> error:<br>
<br>
<strong>Option 1 (recommended):</strong> Start a new SSH session so that <code>PATH</code> is correctly set upon login then try again in this new session.<br>
<br>
<strong>Option 2:</strong> Alternatively you can use this command to call the binary directly:<br>
<br>
<pre><code>~&#x2F;bin&#x2F;znc --makeconf</code></pre><br>
<h2>ZNC Starting or Restarting:</h2><br>
<h3>Start znc</h3><br>
To start <code>znc</code> you will need to SSH into your slot and use this command:<br>
<br>
<pre><code>znc</code></pre><br>
The binary is located in the <code>~&#x2F;bin</code> directory so it should be in the <code>PATH</code>. If you need to call it directly use this command:<br>
<br>
<pre><code>~&#x2F;bin&#x2F;znc</code></pre><br>
<h3>Restart or Shutdown znc</h3><br>
To properly restart or stop <code>znc</code> you connect to your server as the Admin user and execute one of these commands:<br>
<br>
 <strong>Important note:</strong> When configuring <code>znc</code> for the first time you should have created this user with administrator privileges:<br>
<br>
<pre><code>&#x2F;znc restart
&#x2F;znc shutdown</code></pre><br>
See here for more commands: <a href="http://wiki.znc.in/Using_commands">http:&#x2F;&#x2F;wiki.znc.in&#x2F;Using_commands</a><br>
<br>
<h2>Crontab</h2><br>
To make sure <code>znc</code> is restarted after a reboot use cronjob.<br>
<br>
<pre><code>@reboot ~&#x2F;bin&#x2F;znc</code></pre><br>
<h2>Web Admin</h2><br>
If you enable the Web Admin module and configure it while setting up <code>znc</code> using the <code>--makeconf</code> command you can access it via these URLS:<br>
<br>
 <strong>Important note:</strong> In both examples you will need to accept the invalid SSL certificate.<br>
<br>
Where <code>PORT</code> is the port you configured <code>znc</code> to use.<br>
<br>
<pre><code><a href="https://server.feralhosting.com:PORT">https:&#x2F;&#x2F;server.feralhosting.com:PORT</a></code></pre><br>
Or<br>
<br>
<pre><code><a href="https://username.server.feralhosting.com:PORT">https:&#x2F;&#x2F;username.server.feralhosting.com:PORT</a></code></pre><br>
<h2>Notifications:</h2><br>
Install this module to configure notifications via various platforms.<br>
<br>
 <strong>Important note:</strong> In order to use the <code>libcurl</code> transport layer you would need to ask for this dependency to be installed via a ticket if it is not present.<br>
<br>
<pre><code>libcurl4-openssl-dev</code></pre><br>
The you would use <code>make curl=yes</code> instead of <code>znc-buildmod push.cpp</code><br>
<br>
<pre><code>git clone <a href="https://github.com/jreese/znc-push.git">https:&#x2F;&#x2F;github.com&#x2F;jreese&#x2F;znc-push.git</a>
cd ~&#x2F;znc-push
znc-buildmod push.cpp
make install</code></pre><br>
with curl (recommended):<br>
<br>
<pre><code>git clone <a href="https://github.com/jreese/znc-push.git">https:&#x2F;&#x2F;github.com&#x2F;jreese&#x2F;znc-push.git</a>
cd ~&#x2F;znc-push
make curl=yes
make install</code></pre><br>
Then in you connected network use these commands:<br>
<br>
First load the module:<br>
<br>
<pre><code>&#x2F;msg *status loadmod push</code></pre><br>
Then configure it using this command template:<br>
<br>
<pre><code>&#x2F;msg *push set option value</code></pre><br>
So for example:<br>
<br>
<pre><code>&#x2F;msg *push set service pushbullet</code></pre><br>
Then You would set your credentials:<br>
<br>
Username:<br>
<br>
<pre><code>&#x2F;msg *push set username my_pushover_user_key</code></pre><br>
Secret:<br>
<br>
<pre><code>&#x2F;msg *push set secret my_pushover_api_for_this_appliction</code></pre><br>
Please see here for more options and services:<br>
<br>
<a href="https://github.com/jreese/znc-push">https:&#x2F;&#x2F;github.com&#x2F;jreese&#x2F;znc-push</a><br>
<br>
If you see this error from znc you read why here <a href="https://github.com/jreese/znc-push/issues/127">https:&#x2F;&#x2F;github.com&#x2F;jreese&#x2F;znc-push&#x2F;issues&#x2F;127</a><br>
<br>
<pre><code>*push&gt; Error: service type not selected</code></pre><br>
<br>
