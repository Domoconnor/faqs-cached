<h1>How to Get Your Server IP Address in SSH or in IRC</h1>

        
<br>
<h2>Find your IP Address in SSH</h2><br>
<strong>To find the IP address for your server, use this command:</strong><br>
<br>
This command will show you your IPv4 address.<code>-i</code> is for IP addresses for the host name:<br>
<br>
<pre><code>hostname -i</code></pre><br>
This shows the hostname and <code>IPv6</code> address:<br>
<br>
<pre><code>host $(hostname -f)</code></pre><br>
<h2>External checks on the slot via SSH</h2><br>
<a href="http://major.io/icanhazip-com-faq/">http:&#x2F;&#x2F;icanhazip.com&#x2F;</a><br>
<br>
This is an external check and will return your IPv4 address.<br>
<br>
<pre><code>curl -4 icanhazip.com</code></pre><br>
This is an external check and will return your IPv6 address.<br>
<br>
<pre><code>curl -6 icanhazip.com</code></pre><br>
<h2>Checking via IRC </h2><br>
<a href="https://www.feralhosting.com/chat">https:&#x2F;&#x2F;www.feralhosting.com&#x2F;chat</a><br>
<br>
In IRC do this command:<br>
<br>
<pre><code>$ip servername</code></pre><br>
Where <code>servername</code> is the name of your server.<br>
<br>
<pre><code>$ip aphrodite</code></pre><br>
Returns:<br>
<br>
<pre><code>aphrodite.feralhosting.com resolves to 185.21.216.161&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 
aphrodite.feralhosting.com resolves to 2a04:1980:3100:1aac:21b:21ff:feda:4d53 (IPv6)</code></pre><br>
<h2>Checking from your home location:</h2><br>
Alternatively, you can just simply use the <strong>ping</strong> command from any computer:<br>
<br>
<strong>Important note:</strong> When running this command in Windows, press and hold the <a href="http://support.microsoft.com/kb/126449">windows logo key and press R</a> to bring up the run dialogue then type <code>cmd</code>.<br>
<br>
<pre><code>ping server.feralhosting.com</code></pre><br>
<strong>Example:</strong><br>
<br>
<pre><code>ping aphrodite.feralhosting.com</code></pre><br>
The output will be your server&#x27;s IP address, and some other information.<br>
<br>
Since this is GNU&#x2F;Linux, there are many ways to to the same thing and here is one more way.<br>
<br>
<pre><code>host server.feralhosting.com</code></pre><br>
 <br>
Replace server with your server name.<br>
<br>
<strong>Example:</strong><br>
<br>
<pre><code>host rabbit.feralhosting.com
rabbit.feralhosting.com has address 85.17.27.70</code></pre><br>
<h2>Notes:</h2><br>
Also, if you have OpenVPN installed on your slot, the IP given for OpenVPN on your <a href="https://www.feralhosting.com/heron/manager/software/">Software Status page</a> is the IP address of your server.<br>
<br>
