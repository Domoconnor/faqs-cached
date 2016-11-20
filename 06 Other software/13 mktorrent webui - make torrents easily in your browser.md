<h1>mktorrent webui - make torrents easily in your browser</h1>

        
Related FAQs:<br>
<br>
<a href="https://www.feralhosting.com/faq/view?question=12">How to SSH into your slot</a><br>
<a href="https://www.feralhosting.com/faq/view?question=22">Password Protect Your WWW Page(s)</a><br>
<a href="https://www.feralhosting.com/faq/view?question=20">Putting your WWW folder to use</a><br>
<a href="https://www.feralhosting.com/faq/view?question=26"> Upload a Downloaded Torrent to Another Tracker</a>.<br>
<br>
This FAQ also assumes you know <a href="https://www.feralhosting.com/faq/view?question=12">how to SSH into your slot</a>.&nbsp; This FAQ will be done via SSH, but can realistically all be done on your home computer.<br>
<br>
<a href="http://sourceforge.net/projects/mktorrentwebui/">MkTorrent Webui</a><br>
<br>
A Web Frontend for MkTorrent. To avoid the need of user accounts and SSH access.<br>
<br>
<strong>1:</strong> Download the the <a href="http://sourceforge.net/projects/mktorrentwebui/files/latest/download?source=files">mktorrent webui archive</a><br>
<br>
<pre><code>wget -qO ~&#x2F;mk.tar.gz <a href="http://sourceforge.net/projects/mktorrentwebui/files/latest/download?source=files">http:&#x2F;&#x2F;sourceforge.net&#x2F;projects&#x2F;mktorrentwebui&#x2F;files&#x2F;latest&#x2F;download?source=files</a></code></pre><br>
<strong>2:</strong> Extract the tar file and <code>cd</code> into the folder<br>
<br>
<pre><code>tar xfz mk.tar.gz &amp;&amp; cd ~&#x2F;mktorrent&#x2F;</code></pre><br>
<strong>3:</strong>&nbsp; Find the full path to your client&#x27;s data folder.&nbsp; The easiest way to do this in SSH to to just type &#x27;pwd&#x27; and it will return the full path to whatever folder you&#x27;re currently in:<br>
<br>
<pre><code>pwd</code></pre><br>
For example:<br>
<br>
<pre><code>cd ~&#x2F;private&#x2F;rtorrent&#x2F;data</code></pre><br>
Then do:<br>
<br>
<pre><code>pwd</code></pre><br>
Will return something like:<br>
<br>
<pre><code>&#x2F;media&#x2F;sdk1&#x2F;home&#x2F;bobtentpeg&#x2F;private&#x2F;rtorrent&#x2F;data</code></pre><br>
For those of you using an FTP client, you can find your full path usually by looking at the remote path in your FTP client&#x27;s path bar. In FileZilla its the path listed in the <code>remote site</code> box.&nbsp; If your client doesn&#x27;t have this, you can also find the appropriate DiskID, which in my example is:<br>
<br>
<pre><code>sdk1</code></pre><br>
by going up two directories in the file listing<br>
<br>
<strong>4:</strong> Edit the index.php to include the proper root folder path. To edit the file:<br>
<br>
<pre><code>nano index.php</code></pre><br>
Change the the line below to include the proper path:<br>
<br>
<pre><code>$root = &quot;&#x2F;home&#x2F;rtorrent&quot;;</code></pre><br>
The corrected line for me looks like:<br>
<br>
<pre><code>$root = &quot;&#x2F;media&#x2F;sdk1&#x2F;home&#x2F;bobtentpeg&#x2F;private&#x2F;rtorrent&#x2F;data&#x2F;&quot;;</code></pre><br>
Save the file by pressing Control+x and accepting with Y.<br>
<br>
<strong>5:</strong> Move the <code>index.php</code> to be visible by HTTP.&nbsp; If you&#x27;re an rutorrent user, the easiest way to to move it to your rutorrent folder with the below command<br>
<br>
<pre><code>mv index.php ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;rutorrent&#x2F;make.php</code></pre><br>
.<br>
5b. If you aren&#x27;t an rutorrent user, be sure to put the php file in a folder that is password protected.&nbsp; You can find directions to pass protect your WWW folders in the introduction for this FAQ.<br>
<br>
<strong>6:</strong> Visit it in your browser.&nbsp; If you&#x27;re an rutorrent user, visit your rutorrent URL and login then add &quot;make.php&quot; to the end of the URL.&nbsp; It will look like:<br>
<br>
<pre><code><a href="https://server.feralhosting.com/username/rutorrent/make.php">https:&#x2F;&#x2F;server.feralhosting.com&#x2F;username&#x2F;rutorrent&#x2F;make.php</a></code></pre><br>
<br>
