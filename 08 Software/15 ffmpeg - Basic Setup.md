<h1>ffmpeg - Basic Setup</h1>

        
In SSH do the commands described in this FAQ. If you do not know how to SSH into your slot use this FAQ: <a href="https://www.feralhosting.com/faq/view?question=12">SSH basics - Putty</a><br>
<br>
Your FTP &#x2F; SFTP &#x2F; SSH login information can be found on the Slot Details page for the relevant slot. Use this link in your Account Manager to access the relevant slot:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/slot_detail_link.png"><br>
<br>
You login information for the relevant slot will be shown here:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/slot_detail_ssh.png"><br>
<br>
<h2>ffmpeg installation (static)</h2><br>
We will use the statically linked, pre-compiled version of <code>ffmepg</code> from <a href="http://johnvansickle.com/ffmpeg/">http:&#x2F;&#x2F;johnvansickle.com&#x2F;ffmpeg&#x2F;</a><br>
<br>
Use this command to create the <code>~&#x2F;bin</code> directory and reload your shell for this change to take effect.<br>
<br>
<pre><code>mkdir -p ~&#x2F;bin &amp;&amp; bash</code></pre><br>
<strong>1:</strong> Install the program using these commands:<br>
<br>
<pre><code>wget -qO ~&#x2F;ffmpeg.tar.gz <a href="http://johnvansickle.com/ffmpeg/releases/ffmpeg-release-64bit-static.tar.xz">http:&#x2F;&#x2F;johnvansickle.com&#x2F;ffmpeg&#x2F;releases&#x2F;ffmpeg-release-64bit-static.tar.xz</a>
tar xf ~&#x2F;ffmpeg.tar.gz &amp;&amp; cd &amp;&amp; rm -rf ffmpeg-*-64bit-static&#x2F;{manpages,presets,readme.txt}
cp ~&#x2F;ffmpeg-*-64bit-static&#x2F;* ~&#x2F;bin
chmod 700 ~&#x2F;bin&#x2F;{ffmpeg,ffprobe,ffmpeg-10bit,qt-faststart}
cd &amp;&amp; rm -rf ffmpeg{.tar.gz,-*-64bit-static}</code></pre><br>
<strong>2:</strong> Check your version:<br>
<br>
 <strong>Important note:</strong> If you keep getting the old version please start a new SSH session and try again.<br>
<br>
<pre><code>ffmpeg -version</code></pre><br>
<pre><code>~&#x2F;bin&#x2F;ffmpeg -version</code></pre><br>
<br>
The path to the binary will be:<br>
<br>
<pre><code>~&#x2F;bin&#x2F;ffmpeg</code></pre><br>
<br>
