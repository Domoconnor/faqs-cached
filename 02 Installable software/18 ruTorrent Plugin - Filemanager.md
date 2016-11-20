<h1>ruTorrent Plugin - Filemanager</h1>

        
You&#x27;ll need to execute some commands via SSH (secure shell). If you&#x27;ve never used SSH commands the idea of using a terminal window may seem daunting. There is a guide on simply getting connected to your slot through SSH <a href="https://www.feralhosting.com/faq/view?question=12">here</a>. Commands are kept as simple as possible and in most cases will simply need to be copied and pasted into the terminal window (then executed by pressing the <code>Enter</code> key).<br>
<br>
<h2>Installing Filemanager</h2>To install Filemanager execute these commands:<br>
<br>
<pre><code>cd ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;rutorrent&#x2F;plugins&#x2F;
svn co -q <a href="https://github.com/nelu/rutorrent-thirdparty-plugins/trunk/filemanager">https:&#x2F;&#x2F;github.com&#x2F;nelu&#x2F;rutorrent-thirdparty-plugins&#x2F;trunk&#x2F;filemanager</a>
</code></pre><br>
As with all plugins, you&#x27;ll need to refresh ruTorrent if it&#x27;s open in a browser to get any changes recognised.<br>
<br>
<br>
<h2>Using the Screenshots Function of Filemanager</h2><h3>Installing ffmpeg</h3>The plugin uses ffmpeg to generate screenshots and due to the removal of this software from Debian stable you&#x27;ll need to install it to your slot instead. This is easily done by executing the following commands:<br>
<br>
<pre><code>mkdir -p ~&#x2F;bin &amp;&amp; bash
wget -qO ~&#x2F;ffmpeg.tar.gz <a href="http://johnvansickle.com/ffmpeg/releases/ffmpeg-release-64bit-static.tar.xz">http:&#x2F;&#x2F;johnvansickle.com&#x2F;ffmpeg&#x2F;releases&#x2F;ffmpeg-release-64bit-static.tar.xz</a>
tar xf ~&#x2F;ffmpeg.tar.gz 
rm -rf ffmpeg-*-64bit-static&#x2F;{manpages,presets,readme.txt}
cp ~&#x2F;ffmpeg-*-64bit-static&#x2F;* ~&#x2F;bin
chmod 700 ~&#x2F;bin&#x2F;{ffmpeg,ffprobe,ffmpeg-10bit,qt-faststart}
rm -rf ffmpeg{.tar.gz,-*-64bit-static}
</code></pre><br>
<br>
<h3>Configuring Filemanager to Use ffmpeg</h3>Execute these commands to properly configure Filemanager to use your version of ffmpeg and ffprobe:<br>
<br>
<pre><code>cd &amp;&amp; sed -i &quot;s|(getExternal(\&quot;ffprobe\&quot;)|(getExternal(\&quot;~&#x2F;bin&#x2F;ffprobe\&quot;)|g&quot; ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;rutorrent&#x2F;plugins&#x2F;filemanager&#x2F;flm.class.php
sed -i &quot;s|(getExternal(&#x27;ffmpeg&#x27;)|(getExternal(&#x27;$(pwd)&#x2F;bin&#x2F;ffmpeg&#x27;)|g&quot; ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;rutorrent&#x2F;plugins&#x2F;filemanager&#x2F;flm.class.php
</code></pre><br>
<br>
<h2>Troubleshooting</h2><em>When I do something (create an archive, move a file etc.) the action seems to complete but nothing has changed</em><br>
Make sure you&#x27;ve set the permissions correctly in Filemanager&#x27;s scripts directory.<br>
<br>
<em>When I try to generate screenshots I get ffmpeg&#x2F;ffprobe related errors</em><br>
Make sure you&#x27;ve configured screenshots to point to the instance of ffmpeg running on your slot. If in doubt, follow this guide from top to bottom again and refresh ruTorrent.<br>
<br>

