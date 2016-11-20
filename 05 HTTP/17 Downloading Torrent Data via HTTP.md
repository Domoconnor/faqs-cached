<h1>Downloading Torrent Data via HTTP</h1>

        
You&#x27;ll need to execute some commands via SSH (secure shell). If you&#x27;ve never used SSH commands the idea of using a terminal window may seem daunting. There is a guide on simply getting connected to your slot through SSH <a href="https://www.feralhosting.com/faq/view?question=12">here</a>. Commands are kept as simple as possible and in most cases will simply need to be copied and pasted into the terminal window (then executed by pressing the <code>Enter</code> key).<br>
<br>
This guide will help you to download your torrent data from the client via HTTP, so you can download through your browser if you like. This might be particularly useful if your ISP applies quality of service measures (i.e. throttling) on FTP traffic, since HTTP traffic is typically prioritised.<br>
<br>
<br>
<h2>Creating Symbolic Links</h2>To download via HTTP you&#x27;ll need to put the thing to download in your public_html folder. You could copy&#x2F;move the data directly but that has several downsides, so the easiest way is to use symbolic links.<br>
<br>
Firstly, create a links directory using this command:<br>
<br>
<pre><code>mkdir -p ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;links</code></pre><br>
Then we can add the relevant symbolic links for your torrent client using these commands. You can link to more than one torrent client if you like. Please note that the links assume the default location for the torrent client&#x27;s data directory:<br>
<br>
rTorrent<br>
<pre><code>ln -s ~&#x2F;private&#x2F;rtorrent&#x2F;data&#x2F; ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;links&#x2F;rtorrent_data</code></pre><br>
Deluge<br>
<pre><code>ln -s ~&#x2F;private&#x2F;deluge&#x2F;data&#x2F; ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;links&#x2F;deluge_data</code></pre><br>
Transmission<br>
<pre><code>ln -s ~&#x2F;private&#x2F;transmission&#x2F;data&#x2F; ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;links&#x2F;transmission_data</code></pre><br>
<br>
<h2>Accessing Your Page</h2>Anything in public_html can be accessed by appending it to your base URL. This base URL will change depending on whether you want HTTP or HTTPS - for HTTP you would use the following:<br>
<br>
<pre><code><a href="http://">http:&#x2F;&#x2F;</a><em>username</em>.<em>server</em>.feralhosting.com&#x2F;</code></pre><br>
For HTTPS it would be:<br>
<br>
<pre><code><a href="https://">https:&#x2F;&#x2F;</a><em>server</em>.feralhosting.com&#x2F;<em>username</em>&#x2F;</code></pre><br>
In both cases <em>username</em> is replaced with your username and <em>server</em> is replaced by your server name.<br>
<br>
By default you will access the symbolic links via HTTP but you can follow the linked-to guide in the section below, &quot;Using HTTPS&quot; if you wish to connect securely.<br>
<br>
<br>
<h2>Password Protecting</h2>It&#x27;s a good idea to password protect your links directory to stop it being accessible to anyone and everyone - including web crawlers. There is a guide to password protecting your links directory with an easy-to-use bash script on <a href="https://www.feralhosting.com/faq/view?question=22">this</a> page. <br>
<br>
<br>
<h2>Using HTTPS</h2>By default you&#x27;ll be redirected to the HTTP version of your links page. You can change this and force traffic to be sent and received over HTTPS by using <a href="https://www.feralhosting.com/faq/view?question=161">this</a> guide.<br>
<br>
Please note that the certificates here at Feral currently cover feralhosting.com and <em>server</em>.feralhosting.com but do not cover <em>username</em>.<em>server</em>.feralhosting.com.<br>
<br>
