<h1>ruTorrent Plugin - Feralstats</h1>

        
Feralstats is a user-created plugin for ruTorrent which displays your usage page information within the ruTorrent UI. As it is user-created it has <br>
<br>
You&#x27;ll need to execute some commands via SSH (secure shell). If you&#x27;ve never used SSH commands the idea of using a terminal window may seem daunting. There is a guide on simply getting connected to your slot through SSH <a href="https://www.feralhosting.com/faq/view?question=12">here</a>. Commands are kept as simple as possible and in most cases will simply need to be copied and pasted into the terminal window (then executed by pressing the <code>Enter</code> key).<br>
<br>
<h2>Installing and Authenticating Feralstats</h2>To install and use first run these commands:<br>
<br>
<pre><code>cd ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;rutorrent&#x2F;plugins&#x2F;
wget -qO feralstats.zip <a href="http://git.io/nB1WyA">http:&#x2F;&#x2F;git.io&#x2F;nB1WyA</a>
unzip -qo feralstats.zip &amp;&amp; rm -f feralstats.zip
</code></pre><br>
In order to actually use the plugin you need to refresh ruTorrent, select to &quot;Authorize the statustool&quot; and grant permissions for each of the three requests. Then access ruTorrent again and your usage should be displayed.<br>
<br>
<br>
<h2>Usage Notes</h2> Feralstats was made by a user and is therefore not something that Feral maintains. It&#x27;s an improvement over the default ruTorrent plugin for disk space since that plugin merely provides the total disk space left, not space left in your quota.<br>
<br>
However, it works by displaying the information from your usage page - therefore it only changes when the usage page changes (which is when done manually, or automatically every 24 hours). Feral&#x27;s slots have also moved to an unrestricted bandwidth model and therefore the bandwidth display is no longer relevant.<br>
<br>
<br>
<h2>Troubleshooting</h2><em>It just says &quot;Authorize the statustool&quot; in ruTorrent even though I already have</em><br>
Please make sure you&#x27;ve selected to grant permission to all three requests as the plugin will not work otherwise. If you have done this, please try removing the plugin and reinstalling it.
<br>
