<h1>BitTorrent Sync and Resilio Sync - basic setup</h1>

        
<strong>Important Note:</strong> There is a conflict between the new version of btsync released <code>1.4.75</code> and the previously configured conf file used in this FAQ. You will need to do these three things:<br>
<br>
<strong>1:</strong> Download the conf file again and follow the steps below this notice to configure it. You do not need to set a username or password this time. You will be prompted to create this when you visits the WebUi.<br>
<br>
<strong>2:</strong> restart btsync using this command in SSH:<br>
<br>
<pre><code>killall -u $(whoami) btsync &amp;&amp; ~&#x2F;btsync&#x2F;.&#x2F;btsync --config ~&#x2F;btsync&#x2F;sync.conf</code></pre><br>
<strong>3:</strong> Clear your browser history and cache completely and then reload the WebUi<br>
<br>
<strong>End of Notice</strong><br>
<br>
In SSH do the commands described in this FAQ. If you do not know how to SSH into your slot use this FAQ: <a href="https://www.feralhosting.com/faq/view?question=12">SSH basics - Putty</a><br>
<br>
Your FTP &#x2F; SFTP &#x2F; SSH login information can be found on the Slot Details page for the relevant slot. Use this link in your Account Manager to access the relevant slot:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/slot_detail_link.png"><br>
<br>
Your login information for the relevant slot will be shown here:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/slot_detail_ssh.png"><br>
<br>
<h2>btsync manual installation</h2><br>
Here are some basic set-up steps for btsync.<br>
<br>
Info: Automatically sync files via secure, distributed technology. <a href="http://labs.bittorrent.com/experiments/sync.html">btsync homepage</a><br>
<br>
You will need to execute these commands in <a href="https://www.feralhosting.com/faq/view?question=12">SSH</a><br>
<br>
<br>
<h3>btsync 1.4</h3><br>
<pre><code>mkdir -p ~&#x2F;btsync
wget -qO ~&#x2F;btsync&#x2F;btsync.tar.gz <a href="http://download.getsyncapp.com/endpoint/btsync/os/linux-x64/track/stable">http:&#x2F;&#x2F;download.getsyncapp.com&#x2F;endpoint&#x2F;btsync&#x2F;os&#x2F;linux-x64&#x2F;track&#x2F;stable</a>
tar xf ~&#x2F;btsync&#x2F;btsync.tar.gz -C ~&#x2F;btsync &amp;&amp; cd &amp;&amp; rm -f btsync&#x2F;btsync.tar.gz</code></pre><br>
<h3>rslsync</h3><br>
BTSync has been rebranded to Resilio Sync:<br>
<br>
<pre><code>wget <a href="https://download-cdn.getsync.com/stable/linux-x64/resilio-sync_x64.tar.gz">https:&#x2F;&#x2F;download-cdn.getsync.com&#x2F;stable&#x2F;linux-x64&#x2F;resilio-sync_x64.tar.gz</a>
mkdir -p ~&#x2F;rslsync; tar xvzf resilio-sync_x64.tar.gz -C ~&#x2F;rslsync
mkdir -p ~&#x2F;.rslsync; ~&#x2F;rslsync&#x2F;rslsync --dump-sample-config &gt; ~&#x2F;.rslsync&#x2F;rslsync.conf &amp;&amp; rm resilio-sync_x64.tar.gz</code></pre><br>
<h2>Configure the conf file:</h2><br>
Now run this command to set a few variables we need:<br>
<br>
<pre><code>sed -i &#x27;s|MYHOME|&#x27;&quot;$HOME&quot;&#x27;|g&#x27; ~&#x2F;.rslsync&#x2F;rslsync.conf
sed -i &#x27;s|8888|&#x27;$(shuf -i 10001-49000 -n 1)&#x27;|g&#x27; ~&#x2F;.rslsync&#x2F;rslsync.conf</code></pre><br>
<h2>Start Resilio Sync:</h2><br>
Now start Resilio Sync using this command:<br>
<br>
<pre><code>~&#x2F;rslsync&#x2F;rslsync --config ~&#x2F;.rslsync&#x2F;rslsync.conf</code></pre><br>
It is now running in the background ready for us to use.<br>
<br>
<h2>Accessing the WebUi</h2><br>
To access the Web Gui you must use a browser and visit the URL, where <code>username</code> is your Feral username and <code>server</code> is the name of your Feral server that hosts the slot Resilio Sync is installed on:<br>
<br>
<strong>Important note:</strong> to use https you can use the URL format <code>username.server.feralhosting.com</code> without editing the conf. You may have to press <code>F5</code> a few times for the Gui to load after accepting the invalid cert.<br>
<br>
Use this command&nbsp; to see the generated WebUI port via SSH:<br>
<br>
<pre><code>sed -rn &#x27;s|.*&quot;listen&quot; : &quot;0.0.0.0:(.*)&quot;.*|\1|p&#x27; ~&#x2F;.rslsync&#x2F;rslsync.conf</code></pre><br>
Then modify the example URL below with your server information and WebUI port listed by the previous command:<br>
<br>
<pre><code>server.feralhosting.com:PORT</code></pre><br>
For example:<br>
<br>
<pre><code>chronos.feralhosting.com:34567</code></pre><br>
or<br>
<br>
<pre><code>username.server.feralhosting.com:PORT</code></pre><br>
For example:<br>
<br>
<pre><code>superman.chronos.feralhosting.com:34567</code></pre><br>
Either will work.<br>
<br>
<h2>Using the WebUI</h2>Once you are at the WebUI you will be prompted to create a user account. This is only for accessing and using the WebUI.<br>
<br>
Once you have done this step you will be prompted to log in and then you&#x27;re ready to use it!<br>
<br>
<h2> Network &amp; Speed Tweaks </h2>Please be aware that these were tweaks were first suggested before BTSync was rebranded to Resilio Sync - options may be worded differently, located elsewhere or removed entirely.<br>
<br>
Mileage may vary, remember the default values to go back to. I&#x27;ll also mention them here. <br>
<br>
<pre><code>Setting disk_low_priority to False</code></pre><br>
<br>
Allows for more disk usage, specially if you&#x27;re Syncing to a secondary hard drive, no reason to have it set to low priority. <br>
<br>
<pre><code>send_buf_size and recv_buf_size</code></pre><br>
The default values are 10 per variable. I slowly increased them by 5 each time and see if I saw any improvement. I didn&#x27;t see any improvement till I set both variables to 35. Like I said, you may change them further and see if you find any improvement, but don&#x27;t go to crazy. <br>
<br>
<br>
<h2>Kill btsync</h2>To Kill the processes use this command to find running instances:<br>
<br>
<pre><code>ps x | grep btsync | grep -v grep</code></pre><br>
Kill all btsync processes this way:<br>
<br>
<pre><code>killall -u $(whoami) btsync</code></pre><br>
<br>
<h2>Kill Resilio Sync</h2>To Kill the processes use this command to find running instances:<br>
<br>
<pre><code>ps x | grep rslsync| grep -v grep</code></pre><br>
Kill all rslsync processes this way:<br>
<br>
<pre><code>killall -u $(whoami) rslsync</code></pre><br>
<br>
