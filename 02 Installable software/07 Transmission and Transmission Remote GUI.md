<h1>Transmission and Transmission Remote GUI</h1>

        
Transmission can be installed from the <a href="https://www.feralhosting.com/manager/">Install Software</a> link in your Manager for the slot you wish to use it on.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Installable%20software/Transmission%20and%20Transmission%20Remote%20GUI/transslotdetail.png"><br>
<br>
If you wish to set up an RPC client you will need to take note of your server name (in green), it&#x27;s also listed in the menu.<br>
<br>
<h3>Remote GUI Client for Transmission</h3><br>
Transmisson Remote GUI is a stand-alone client that runs on your computer and allows you to control your instance of Transmission running on the server remotely. It supports the following platforms: Windows, Mac, and Linux<br>
<br>
To start, <a href="https://sourceforge.net/projects/transgui/">download the latest version</a> then follow the configuration instructions below.<br>
<br>
<strong>Important note:</strong> The similarly named <a href="http://code.google.com/p/transmission-remote-dotnet/">transmission-remote-dotnet</a> does not work with our installations.<br>
<br>
<h3>Configuring Remote GUI</h3><br>
Opening the client you should see something similar to the following image. Click the down arrow by the connection symbol to open the menu:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Installable%20software/Transmission%20and%20Transmission%20Remote%20GUI/1.png"><br>
<br>
Select &quot;New connection...&quot;:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Installable%20software/Transmission%20and%20Transmission%20Remote%20GUI/2.png"><br>
<br>
You will then be presented with the &quot;Connection options&quot; window like so:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Installable%20software/Transmission%20and%20Transmission%20Remote%20GUI/3.png"><br>
<br>
We will need to fill it with information similar to below. If you want the RPC connection to be unsecured then use something similar to:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Installable%20software/Transmission%20and%20Transmission%20Remote%20GUI/4.png"><br>
<br>
For a secure connection (always recommended) then please select SSL and use the following port:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Installable%20software/Transmission%20and%20Transmission%20Remote%20GUI/5.png"><br>
<br>
<strong>Connection:</strong> You may choose a name or leave it blank for it to be automatically filled by the <code>Remote host</code> field.<br>
<br>
<strong>Remote host:</strong> Enter the host <code>transmission.username.server.feralhosting.com</code> replacing <code>username</code> with your Feral username in lowercase and <code>server</code> with your server name, for example:<br>
<br>
<pre><code>transmission.peterpan.aphrodite.feralhosting.com</code></pre><br>
<strong>Port:</strong> If you check <code>Use SSL</code> then use port <code>443</code> otherwise, port <code>80</code>. SSL will encrypt your connection and is recommended.<br>
<br>
<code>User name:</code> Your Feral username.<br>
<br>
<code>Password:</code> As listed under the Transmission section of your &quot;Slot Detail&quot; page.<br>
<br>
<code>RPC path:</code> Simply a forward slash: <code>&#x2F;</code><br>
<br>
Once filled in, click OK and it will save then connect to the profile.<br>
<br>
<h3>Using transmission-remote (CLI)</h3><br>
If you want to use <strong>transmission-remote</strong> CLI from a remote location to your Slot, just use the following command:<br>
<br>
<pre><code>
transmission-remote <a href="http://server.feralhosting.com:80/username/transmission">http:&#x2F;&#x2F;server.feralhosting.com:80&#x2F;username&#x2F;transmission</a> -n username:password -&lt;your transmission-remote command&gt;
</code></pre><br>
Example with user peterpan on server aphrodite:<br>
<pre><code>transmission-remote <a href="http://aphrodite.feralhosting:80/peterpan/transmission">http:&#x2F;&#x2F;aphrodite.feralhosting:80&#x2F;peterpan&#x2F;transmission</a> -n peterpan:PASSWORD -st</code></pre><br>
<br>
<h3>Troubleshooting Transmission</h3><br>
If Transmission is acting abnormally e.g., has become unresponsive then a restart is in order<br>
<br>
If transmission is acting abnormally (e.g., has become unresponsive or frozen) you will need to restart it. Log into your slot via <a href="https://www.feralhosting.com/faq/view?question=12">SSH</a>, and run this command:<br>
<br>
<pre><code>killall -9 -u $(whoami) transmission-daemon</code></pre><br>
It will then be restart automatically in the next 5 minutes.<br>
<br>
If the problem persists or Transmission is not restarted then please open a support ticket.<br>
<br>
<h3>What version of Transmission am I running?</h3><br>
Login to the Web Gui, press the &quot;gears&quot; button on the bottom left hand corner and select &quot;About&quot;. You will then be presented with a dialogue showing the version number.<br>
<br>
