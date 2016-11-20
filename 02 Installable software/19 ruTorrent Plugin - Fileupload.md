<h1>ruTorrent Plugin - Fileupload</h1>

        
This plugin will allow you to use Plowshare to upload to various filesharing services via ruTorrent.<br>
<br>
<h2>Preparation</h2>You&#x27;ll need to execute some commands via SSH (secure shell). If you&#x27;ve never used SSH commands the idea of using a terminal window may seem daunting. There is a guide on simply getting connected to your slot through SSH <a href="https://www.feralhosting.com/faq/view?question=12">here</a>. Commands are kept as simple as possible and in most cases will simply need to be copied and pasted into the terminal window (then executed by pressing the <code>Enter</code> key).<br>
<br>
As it&#x27;s not possible to set a path to plowup (Plowshare&#x27;s uploading software) within the plugin&#x27;s configuration files you&#x27;ll need to make sure that plowup is in your PATH. Otherwise you&#x27;ll receive an error that rTorrent is not able to access it. To do this, please log in via SSH and execute the following commands:<br>
<br>
<pre><code>echo &quot;PATH=$HOME&#x2F;bin:$PATH&quot; &gt; ~&#x2F;.bashrc
source ~&#x2F;.bashrc
</code></pre><br>
<br>
<h2>Installing Fileupload</h2><h3>Installing Plowshare</h3>To install Plowshare execute the following commands:<br>
<br>
<pre><code>mkdir -p ~&#x2F;bin &amp;&amp; bash
git clone <a href="https://github.com/mcrapet/plowshare.git">https:&#x2F;&#x2F;github.com&#x2F;mcrapet&#x2F;plowshare.git</a> ~&#x2F;.plowshare-source &amp;&amp; cd ~&#x2F;.plowshare-source
make install PREFIX=$HOME
cd &amp;&amp; rm -rf .plowshare-source
</code></pre><br>
<br>
<h3>Configuring Plowshare</h3>Run this command to install the plowshare modules:<br>
<br>
<pre><code>plowmod --install</code></pre><br>
If you get &quot;command not found&quot; then you need to revisit the preparation steps above because your ~&#x2F;bin&#x2F; directory is not in PATH.<br>
<br>
<br>
<h3>Installing the Fileupload Plugin</h3>Execute these commands to install the plugin:<br>
<br>
<pre><code>cd ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;rutorrent&#x2F;plugins&#x2F;
svn co -q <a href="https://github.com/nelu/rutorrent-thirdparty-plugins/trunk/fileupload">https:&#x2F;&#x2F;github.com&#x2F;nelu&#x2F;rutorrent-thirdparty-plugins&#x2F;trunk&#x2F;fileupload</a>
</code></pre><br>
You should then refresh ruTorrent to make sure the plugin can communicate with your plowup binary correctly. If you get an error (&quot;fileupload: Plugin will not work. rTorrent user can&#x27;t access external program (plowup).&quot;), kill and restart rTorrent like so:<br>
<br>
<pre><code>pkill -fu &quot;$(whoami)&quot; &#x27;SCREEN -S rtorrent&#x27;
screen -S rtorrent rtorrent
</code></pre><br>
<br>
