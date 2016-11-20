<h1>Sick Beard - Installation and Configuration</h1>

        
<strong>Please note!</strong> Though this software runs in nearly all cases without problems, Feral cannot provide much support for its use or help should anything go wrong. Please make sure you&#x27;ve read this FAQ fully as help on the problem may be covered already.<br>
<br>
This notice absolutely does not prevent you from raising a ticket should anything go wrong but please bear in mind staff may not be able to assist beyond basic troubleshooting (for example restarting, clarifying error messages and so on).<br>
<br>
<h2>Preparation</h2>You&#x27;ll need to execute some commands via SSH (secure shell). If you&#x27;ve never used SSH commands the idea of using a terminal window may seem daunting. There is a guide on simply getting connected to your slot through SSH <a href="https://www.feralhosting.com/faq/view?question=12">here</a>. Commands are kept as simple as possible and in most cases will simply need to be copied and pasted into the terminal window (then executed by pressing the <code>Enter</code> key).<br>
<br>
<br>
<h2>Installation - using the automated bash script</h2>Features of the bash script:<br>
<br>
&nbsp; 1.&nbsp; Installs Sick Beard or SickRage from GitHub (this guide only covers Sick Beard - for SickRage please see <a href="https://www.feralhosting.com/faq/view?question=281">this guide</a>)<br>
&nbsp; 2. Configures the proxypass to provide an https URL<br>
&nbsp; 3. Can to choose to update the software and&#x2F;or install only the proxypass<br>
<br>
To use the script just use this command:<br>
<br>
<pre><code>wget -qO ~&#x2F;install.sick <a href="http://git.io/vfGch">http:&#x2F;&#x2F;git.io&#x2F;vfGch</a> &amp;&amp; bash ~&#x2F;install.sick</code></pre><br>
<br>
<h2>Installation - manual</h2>Manual installation allows a greater degree of control but the automated script should be sufficient for the majority of use cases.<br>
<br>
<br>
<h3>Clone Sick Beard from GitHub</h3><br>
First you need to download Sick Beard by cloning the repository onto your slot. To do that, copy-paste the following:<br>
<br>
<pre><code>git clone <a href="https://github.com/midgetspy/Sick-Beard">https:&#x2F;&#x2F;github.com&#x2F;midgetspy&#x2F;Sick-Beard</a> ~&#x2F;.sickbeard</code></pre><br>
<br>
<h3>Start up Sick Beard</h3>To start up Sick Beard we need to pick a port for it to run on. In the command below replace <em>port</em> with a number between <strong>10001</strong> and <strong>49999</strong>:<br>
<br>
<pre><code>python ~&#x2F;.sickbeard&#x2F;SickBeard.py -d -p <em>port</em> --pidfile=&quot;$HOME&#x2F;.sickbeard&#x2F;sickbeard.pid&quot;</code></pre><br>
If nothing happens or there is an error it could be that the port you picked is in use. Simply try with a different number.<br>
<br>
Once started up you can visit Sick Beard by visiting <a href="http://">http:&#x2F;&#x2F;</a><em>server</em>.feralhosting.com:<em>port</em>[&#x2F;code] where <em>server</em> is the name of your server and <em>port</em> is the port you picked earlier.<br>
<br>
Within the Sick Beard UI, click the Config button and then click General. In the section named &#x27;Web Interface&#x27; you&#x27;ll be able to set a username and password for the web UI. Whilst it&#x27;s not mandatory you do this, it is a sensible thing to do.<br>
<br>
<br>
<h3>Configure the proxypass</h3>The bash script in the first Installation section can set up the proxypass for you without installing Sick Beard, so even if you wish to use a different repository you can still make use of the script for this purpose.<br>
<br>
<br>
<h2>Configuring</h2>This section covers connecting Sick Beard to <a href="https://www.feralhosting.com/faq/view?question=125">here</a>.<br>
<br>
Enter the details as follows:<br>
<br>
<code>SABnzbd URL</code>: <a href="https://">https:&#x2F;&#x2F;</a><em>server</em>.feralhosting.com:<em>port</em>&#x2F;sabnzbd&#x2F; (replace <em>server</em> with your server name and <em>port</em> with your HTTPS port for SABnzbd)<br>
<br>
<code>SABnzbd Username</code>: The username you set for the SABnzbd UI<br>
<br>
<code>SABnzbd Password</code>: The password you set for the SABnzbd UI<br>
<br>
<code>SABnzbd API Key</code>: Find this in the General section of SABnzbd&#x27;s settings<br>
<br>
<br>
<h2>Starting and restarting</h2>In order to restart the software the existing process should be killed. If the check below does not display a process number please proceed to step 3. These steps are tailored towards processes started by this FAQ.<br>
<br>
<br>
1.&nbsp; &nbsp; Check:<br>
<pre><code>pgrep -fu &quot;$(whoami)&quot; &quot;python $HOME&#x2F;.sickbeard&#x2F;SickBeard.py -d&quot;</code></pre><br>
2.&nbsp; &nbsp; Kill:<br>
<pre><code>kill &quot;$(pgrep -fu &quot;$(whoami)&quot; &quot;python $HOME&#x2F;.sickbeard&#x2F;SickBeard.py -d&quot;)&quot;</code></pre><br>
3.&nbsp; &nbsp; Restart:<br>
<pre><code>python ~&#x2F;.sickbeard&#x2F;SickBeard.py -d --pidfile=&quot;$HOME&#x2F;.sickbeard&#x2F;sickbeard.pid&quot;</code></pre><br>
<strong>Important note:</strong> You can repeat step 1 after attempting to kill to check if it&#x27;s been shut down. Give the program at least 10 seconds to shut down at step 2 before trying to restart. If it refuses to exit then you have to force it to quit using this command instead:<br>
<br>
<pre><code>kill -9 &quot;$(pgrep -fu &quot;$(whoami)&quot; &quot;python $HOME&#x2F;.sickbeard&#x2F;SickBeard.py -d&quot;)&quot;</code></pre><br>
<br>
<h2>Cron - start up automatically if the server is rebooted</h2>Unfortunately sometimes the server needs to be rebooted. When this happens the system will start up a lot of the processes automatically on your slot. It will not however start up custom software. We need to manually set something up to make this happen.<br>
<br>
To bring up the crontab editor use the following command:<br>
<br>
<pre><code>crontab -e</code></pre><br>
If this is your very first time you&#x27;ll be given a choice of editors. Nano is fine to use so unless you specifically want something else just press enter.<br>
<br>
There will already be some basic information on crontabs in the screen that appears - you can keep it if you like, or get rid of it if you prefer. The lines are commented out so are for information purposes only and don&#x27;t affect any cron jobs added.<br>
<br>
At a new line in the file copy-paste the following:<br>
<br>
<pre><code>@reboot rm -rf ~&#x2F;.sickbeard&#x2F;sickbeard.pid
@reboot python ~&#x2F;.sickbeard&#x2F;SickBeard.py -d --pidfile=&quot;$HOME&#x2F;.sickbeard&#x2F;sickbeard.pid&quot;&quot;
</code></pre><br>
<br>
<h2>Troubleshooting</h2><em>I went to start up Sick Beard and received an error &#x27;...sickbeard.pid already exists. Exiting.&#x27;</em><br>
Assuming you&#x27;re using the default locations please run the following command before trying the start up command again:<br>
<br>
<pre><code>rm ~&#x2F;.sickbeard&#x2F;sickbeard.pid</code></pre><br>
<br>
