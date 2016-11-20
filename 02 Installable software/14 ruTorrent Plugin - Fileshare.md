<h1>ruTorrent Plugin - Fileshare</h1>

        
You&#x27;ll need to execute some commands via SSH (secure shell). If you&#x27;ve never used SSH commands the idea of using a terminal window may seem daunting. There is a guide on simply getting connected to your slot through SSH <a href="https://www.feralhosting.com/faq/view?question=12">here</a>. Commands are kept as simple as possible and in most cases will simply need to be copied and pasted into the terminal window (then executed by pressing the <code>Enter</code> key).<br>
<br>
<h2>Installing Fileshare</h2>Fileshare requires Filemanager and both can be installed using the following commands:<br>
<br>
<pre><code>cd ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;rutorrent&#x2F;plugins&#x2F;
svn co -q <a href="https://github.com/nelu/rutorrent-thirdparty-plugins/trunk/filemanager">https:&#x2F;&#x2F;github.com&#x2F;nelu&#x2F;rutorrent-thirdparty-plugins&#x2F;trunk&#x2F;filemanager</a>
svn co -q <a href="https://github.com/nelu/rutorrent-thirdparty-plugins/trunk/fileshare">https:&#x2F;&#x2F;github.com&#x2F;nelu&#x2F;rutorrent-thirdparty-plugins&#x2F;trunk&#x2F;fileshare</a>
</code></pre><br>
Further information on Filemanager can be found <a href="https://www.feralhosting.com/faq/view?question=330">here</a>.<br>
<br>
<br>
<h2>Configuring Fileshare</h2>These commands will configure the plugin to run on your slot:<br>
<br>
<pre><code>ln -s ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;rutorrent&#x2F;plugins&#x2F;fileshare&#x2F;share.php ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;
sed &quot;&#x2F;if(getConfFile(&#x2F;d&quot; -i ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;rutorrent&#x2F;plugins&#x2F;fileshare&#x2F;share.php
sed -i &quot;s|&#x27;<a href="http://mydomain.com/share.php">http:&#x2F;&#x2F;mydomain.com&#x2F;share.php</a>&#x27;;|&#x27;<a href="http://">http:&#x2F;&#x2F;</a>$(whoami).$(hostname -f)&#x2F;share.php&#x27;;|g&quot; ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;rutorrent&#x2F;plugins&#x2F;fileshare&#x2F;conf.php
</code></pre><br>
<br>
