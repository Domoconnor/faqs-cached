<h1>Deluge - Running more than one instance</h1>

        
<h2>How to run multiple instances of Deluge on a Feral Slot</h2><br>
<strong>Important note:</strong> This is a community supported FAQ. Feralhosting does not officially support this document.<br>
<br>
Please seek help in the feralhosting.com IRC channel if you need assistance. Many Feral customers volunteer their time to create and support these FAQs. Please be considerate of their time -- they will help when they can, but are not always available.<br>
<br>
These instructions are intended to be run over <a href="https://www.feralhosting.com/faq/view?question=12">SSH</a>. You may be able to modify them to work under another method, if you desire.<br>
<br>
<h2>Make a copy of the existing config:</h2><br>
<strong>Copy&#x2F;Paste exactly as given</strong><br>
<br>
<pre><code>cp -r ~&#x2F;.config&#x2F;deluge ~&#x2F;.config&#x2F;deluge2</code></pre><br>
<h2>Clean up the config:</h2><br>
<strong>Copy&#x2F;Paste exactly as given</strong><br>
<br>
<pre><code># Delete the .pid file
find ~&#x2F;.config&#x2F;deluge2 -name deluged.pid -exec rm &#x27;{}&#x27; \;

# Delete the torrents already added
find ~&#x2F;.config&#x2F;deluge2&#x2F;state -name \*torrent -exec rm &#x27;{}&#x27; \;

# Update the locations in the config
sed -i &#x27;s|&#x2F;private&#x2F;deluge&#x2F;|&#x2F;private&#x2F;deluge2&#x2F;|g&#x27; ~&#x2F;.config&#x2F;deluge2&#x2F;core.conf*</code></pre><br>
<h2>Update the port in use:</h2><br>
<strong>Copy&#x2F;Paste exactly as given</strong><br>
<br>
<pre><code>OLD_PORT=$(grep daemon_port ~&#x2F;.config&#x2F;deluge2&#x2F;core.conf | awk &#x27;{print $2}&#x27; | cut -d\,&nbsp; -f1)
NEW_PORT=$((RANDOM%10000+40000))
sed -i &quot;s|${OLD_PORT}|${NEW_PORT}|g&quot; ~&#x2F;.config&#x2F;deluge2&#x2F;core.conf*</code></pre><br>
<h2>Retrieve important information:</h2><br>
<strong>Copy&#x2F;Paste exactly as given</strong><br>
<br>
<pre><code>PASSWORD=$(cat ~&#x2F;.config&#x2F;deluge2&#x2F;auth | grep $(whoami) | cut -d\:&nbsp; -f2)
echo &quot;Your deluge web interface connection information is as follows:&quot;; echo &quot;HOST=10.0.0.1&quot;; echo &quot;PORT=${NEW_PORT}&quot;; echo &quot;USERNAME=$(whoami)&quot;; echo &quot;PASSWORD=${PASSWORD}&quot;; echo &quot;###&quot;;

echo &quot;Your deluge thin client connection information is as follows:&quot;; echo &quot;HOST=$(hostname -f)&quot;; echo &quot;PORT=${NEW_PORT}&quot;; echo &quot;USERNAME=$(whoami)&quot;; echo &quot;PASSWORD=${PASSWORD}&quot;;</code></pre><br>
<h2>Start new instance:</h2><br>
<strong>Ignore any of the following errors:</strong><br>
<br>
<code>ERROR&nbsp; &nbsp; 14:26:39 torrentmanager:372 Unable to add torrent!</code><br>
<br>
<strong>Copy&#x2F;Paste exactly as given</strong><br>
<br>
<pre><code>deluged -c ~&#x2F;.config&#x2F;deluge2&#x2F;</code></pre><br>
If, and <strong>only if</strong>, you get the error:<br>
<br>
<code>ERROR&nbsp; &nbsp; 15:04:01 rpcserver:375 Couldn&#x27;t listen on any:52055: Errno 98 Address already in use.</code> re-run the &quot;Update the port in use&quot; and &quot;Retrieve important information&quot; sections. You may safely run these commands as many times as needed.<br>
<br>
<h2>Create the needed folders:</h2><br>
<strong>Copy&#x2F;Paste exactly as given</strong><br>
<br>
<pre><code>mkdir -p ~&#x2F;private&#x2F;deluge2&#x2F;{completed,data,torrents,watch}</code></pre><br>
<h2>To connect to your new instance:</h2><br>
<h3>To add to the web interface:</h3><br>
Load up your Deluge web interface<br>
<br>
Connection Manager -&gt; Add. Fill in the details with the details above for the web interface.<br>
<br>
<h3>To add to the <a href="https://www.feralhosting.com/faq/view?question=76">thin</a> client:</h3><br>
Load up your Deluge thin client<br>
<br>
Connection Manager -&gt; Add. Fill in the details with the details above for the web interface.<br>
<br>
<h2>Important caveats </h2><br>
1) If you run the command ‘killall -9 deluged’, <em>all</em> instance of deluge will be killed and need to be restarted.<br>
<br>
2) If you want this instance of deluge to restart automatically if and when the server reboots, you can add a ‘crontab’ entry to do that:<br>
<br>
<pre><code>crontab -e</code></pre><br>
This will open up your crontab. At the bottom of the file, add the following:<br>
<br>
<pre><code>@reboot &#x2F;usr&#x2F;local&#x2F;bin&#x2F;deluged -c ${HOME}&#x2F;.config&#x2F;deluge2</code></pre><br>
<br>
