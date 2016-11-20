<h1>Restarting - rtorrent - Deluge - Transmission -  MySQL</h1>

        
<br>
<strong>Important note:</strong> An optional way to restart&#x2F;reset software is to install it again from the software page - this will leave data intact, but will reset configuration, passwords, RSS feeds and custom folders.<br>
<br>
<h2>Bash script</h2><br>
Here is a simple bash script for restarting rtorrent,deluge, transmission (kill only) and mysql with some checks to see they restarted. The script performs the basic kill and restart (where applicable) functions outlined in this FAQ.<br>
<br>
If you get errors on restarting a particular program or they fail to start, refer back to this FAQ for troubleshooting.<br>
<br>
<pre><code>wget -qO ~&#x2F;restart.sh <a href="http://git.io/5Uw8Gw">http:&#x2F;&#x2F;git.io&#x2F;5Uw8Gw</a> &amp;&amp; bash ~&#x2F;restart.sh</code></pre><br>
<h2>Manually restarting programs</h2><br>
Copy and paste commands directly as written in this FAQ.<br>
<br>
<h2>Restarting rtorrent</h2><br>
Run the following commands through <a href="https://www.feralhosting.com/faq/view?question=12">SSH</a>.<br>
<br>
<strong>Step 1:</strong> Kill rtorrent<br>
 <br>
<pre><code>killall -9 -u $(whoami) rtorrent</code></pre><br>
<strong>Step 2:</strong> Start it again in a screen<br>
<br>
<pre><code>screen -S rtorrent rtorrent</code></pre><br>
If all goes well, you should be greeted with your rtorrent&nbsp; and you should see your torrents. To exit rtorrent (and keep it running) press and hold <code>CTRL</code> and <code>a</code> then press <code>d</code> to detach from the screen once you are sure rtorrent is running.<br>
<br>
If you are given a <code>screen is terminating</code> error, please consult the commands in Step 3.0<br>
<br>
<strong>Step 3.0:</strong> Screen is terminating error<br>
<br>
Attempt to start rtorrent using this command:<br>
<br>
<pre><code>rtorrent</code></pre><br>
You will now usually see the error that rtorrent it throwing out.<br>
 <br>
You can try this in some cases: <br>
<br>
<pre><code>rm -rf ~&#x2F;private&#x2F;rtorrent&#x2F;work&#x2F;rtorrent.*</code></pre><br>
If the error means nothing to you can <a href="https://www.feralhosting.com/manager/tickets/new">open a ticket</a> or ask on <a href="https://www.feralhosting.com/chat">IRC</a> for help.<br>
<br>
<strong>3.1:</strong> Start it again in a screen once you have resolved the errors:<br>
<br>
<pre><code>screen -S rtorrent rtorrent</code></pre><br>
If all goes well, you should be greeted with your rtorrent&nbsp; and you should see your torrents. To exit rtorrent (and keep it running) press and hold <code>CTRL</code> and <code>a</code> then press <code>d</code> to detach from the screen once you are sure rtorrent is running.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Installable%20software/Restarting%20-%20rtorrent%20-%20Deluge%20-%20Transmission%20-%20MySQL/1.png"><br>
<br>
<h2>Restarting Transmission</h2><br>
Run the following commands in <a href="https://www.feralhosting.com/faq/view?question=12">SSH</a>.<br>
<br>
<strong>1:</strong> Kill transmission<br>
<br>
<pre><code>killall -9 -u $(whoami) transmission-daemon</code></pre><br>
<strong>Important note:</strong>&nbsp; Transmission cannot be started by the user and will be started by the system instead. After killing the process allow up to 5 minutes for it to automatically to restart.<br>
<br>
You can do this to see if the process has restarted:<br>
<br>
<pre><code>ps x | grep transmission | grep -v grep</code></pre><br>
You will see this if the process is running.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Installable%20software/Restarting%20-%20rtorrent%20-%20Deluge%20-%20Transmission%20-%20MySQL/transmission.png"><br>
<br>
<h2>Restarting Deluge</h2><br>
Run the following commands through <a href="https://www.feralhosting.com/faq/view?question=12"> SSH</a>.<br>
<br>
Use the commands you need to kill and start the deluge daemon and Web Gui:<br>
<br>
<h2>Kill the deluge daemon and Web Gui</h2><br>
<strong>Option 1:</strong> Kill deluge only<br>
<br>
<pre><code>killall -9 -u $(whoami) deluged</code></pre><br>
<strong>Option 2:</strong> Kill the Web Gui only<br>
<br>
<pre><code>killall -9 -u $(whoami) deluge-web</code></pre><br>
<strong>Option 3</strong> This command would kill the deluge process and the WebUi together<br>
<br>
<pre><code>killall -9 -u $(whoami) deluged deluge-web</code></pre><br>
<h2>Restart the deluge daemon and WebUi</h2><br>
<strong>Important note:</strong> <code>deluged</code> can be started by the user but <code>deluge-web</code> cannot be started by the user and will be started by the system instead. After killing the process allow up to 5 minutes for it to automatically to restart.<br>
<br>
If you get this error when starting <code>deluged</code> you will need to open a <a href="https://www.feralhosting.com/manager/tickets/new">support ticket</a> with a relevant title. This problem requires Staff to fix.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Installable%20software/Restarting%20-%20rtorrent%20-%20Deluge%20-%20Transmission%20-%20MySQL/twisted.png"><br>
<br>
<h3>Restart deluged</h3><br>
<pre><code>deluged</code></pre><br>
<h3>Restart deluge-web</h3><br>
Please wait up to 5 minutes for the system to restart the <code>deluge-web</code> process.<br>
<br>
You can do this to see if the process has restarted, You will see this if the process is running:<br>
<br>
<pre><code>ps x | grep deluge | grep -v grep</code></pre><br>
If the processes are running the result will look like this:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Installable%20software/Restarting%20-%20rtorrent%20-%20Deluge%20-%20Transmission%20-%20MySQL/deluge.png"><br>
<br>
<h2>Restarting MySQL</h2><br>
Run the following commands through <a href="https://www.feralhosting.com/faq/view?question=12"> SSH</a>. (Copy and paste these commands directly as written). <br>
<br>
<strong>1:</strong> Kill mysql<br>
<br>
<pre><code>killall -9 -u $(whoami) mysqld mysqld_safe</code></pre><br>
<strong>2:</strong> Start mysql<br>
<br>
<pre><code>bash ~&#x2F;private&#x2F;mysql&#x2F;launch.sh</code></pre><br>
If all goes well, you should be greeted by two messages like the ones below<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Installable%20software/Restarting%20-%20rtorrent%20-%20Deluge%20-%20Transmission%20-%20MySQL/4.png"><br>
<br>
<strong>Finally...</strong><br>
<br>
If you continue to have problems after following these steps closely, please open a support ticket providing details of the error message you are receiving for which software and we will gladly help you.<br>
<br>
