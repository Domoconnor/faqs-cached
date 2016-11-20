<h1>Deluge Daemon - Remote control with the local Thin client </h1>

        
<br>
This FAQ requires you have already installed Deluge using the <a href="https://www.feralhosting.com/manager/">[b]Install Software[&#x2F;b] link in your Manager</a> link in the manager for your slot.<br>
<br>
In SSH do these commands. Use this FAQ if you do not know how to SSH into your slot: <a href="https://www.feralhosting.com/faq/view?question=12">SSH basics - Putty</a><br>
<br>
To be able to connect your local deluge client to your remote daemon and interact with it as if it were running locally is easy and just takes a few steps.<br>
<br>
<h2>Bash Script:</h2><br>
This bash script will do the following things for you.:<br>
<br>
<strong>1:</strong> Print your hostname and daemon port <br>
<strong>2:</strong> Print your username and password<br>
<br>
You will then be able to connect to deluge using the thin client with the information printed by the script.<br>
<br>
<pre><code>wget -qO ~&#x2F;delugethin.sh <a href="http://git.io/obe0mA">http:&#x2F;&#x2F;git.io&#x2F;obe0mA</a> &amp;&amp; bash ~&#x2F;delugethin.sh</code></pre><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Installable%20software/Deluge%20Daemon%20-%20Remote%20control%20with%20the%20local%20Thin%20client/script.png"><br>
<br>
<h2>Manual Installation Steps:</h2><br>
You need to know some settings and passwords on the server first. To do this, <a href="http://www.feralhosting.com/faq/view?question=12">SSH</a> into your Feral slot and execute the following commands:<br>
<br>
<strong>1:</strong> Get your connection details.<br>
<br>
Copy and paste this one liner to retrieve all the required info in a single copy and paste command:<br>
<br>
<pre><code>printf &quot;$(hostname -f)\n$(whoami)\n$(sed -rn &#x27;s&#x2F;(.*)&quot;daemon_port&quot;: (.*),&#x2F;\2&#x2F;p&#x27; ~&#x2F;.config&#x2F;deluge&#x2F;core.conf)\n$(sed -rn &quot;s&#x2F;$(whoami):(.*):(.*)&#x2F;\1&#x2F;p&quot; ~&#x2F;.config&#x2F;deluge&#x2F;auth)\n&quot;</code></pre><br>
Here are the individual components of the one liner command:<br>
<br>
Your hostname:<br>
<br>
<pre><code>hostname -f</code></pre><br>
Your username:<br>
<br>
<pre><code>whoami</code></pre><br>
Your connection port:<br>
<br>
<pre><code>sed -rn &#x27;s&#x2F;(.*)&quot;daemon_port&quot;: (.*),&#x2F;\2&#x2F;p&#x27; ~&#x2F;.config&#x2F;deluge&#x2F;core.conf</code></pre><br>
This is the password you will need to connect the thin client to the remote daemon.<br>
<br>
<pre><code>sed -rn &quot;s&#x2F;$(whoami):(.*):(.*)&#x2F;\1&#x2F;p&quot; ~&#x2F;.config&#x2F;deluge&#x2F;auth</code></pre><br>
<strong>Step 2:</strong> Local Client (Thin Client) Set-up<br>
<br>
Download <a href="http://dev.deluge-torrent.org/wiki/Download">deluge</a> (make sure the version matches the daemon version running on the server).<br>
<br>
Install and run deluge on your local machine and then run it.<br>
<br>
Go to <code>Preferences -&gt; Interface</code> and un-check<code>Enable</code> under <code>Classic Mode</code>.<br>
<br>
You should now see a connection manager box pop up.<br>
<br>
Remove the localhost daemon<br>
<br>
Click <code>Add</code> and enter the address of your Feral server, for example: <code>athena.feralhosting.com</code> found from the commands in <strong>Step 1</strong>.<br>
<br>
Set the port to the port you got in <strong>Step 1</strong>. <br>
<br>
Enter the username and password you got from <strong>Step 1</strong>.<br>
<br>
Click <code>Add</code> to add your server&#x27;s daemon — you should now see a green icon as the status for the host you just added. #<br>
<br>
If the light stays red, remove the connection start again.<br>
<br>
<strong>Optional:</strong> <br>
<br>
Expand <code>Options</code> and select <code>Automatically connect to selected host on startup</code> and <code>Do not show this dialogue on start-up</code><br>
Click <code>Connect</code>, and the connection manager pop up box should disappear. You should find deluge is now functioning as a local client while manipulating the remote deluge daemon on your Feral slot<br>
<br>
To see more information regarding running deluge as a Thin Client visit <a href="http://dev.deluge-torrent.org/wiki/UserGuide/ThinClient">http:&#x2F;&#x2F;dev.deluge-torrent.org&#x2F;wiki&#x2F;UserGuide&#x2F;ThinClient</a>.<br>
<br>

