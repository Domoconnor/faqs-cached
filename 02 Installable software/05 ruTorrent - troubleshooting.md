<h1>ruTorrent - troubleshooting</h1>

        
<h3>ruTorrent Is Not a Bittorrent client</h3><br>
It is important that you understand that ruTorrent is not a bittorrent client, which is why it cannot crash and cannot be restarted. It is a web application that runs in the browser and is dependant on things like apache&#x2F;nginx and php.<br>
<br>
ruTorrent is a web-based user interface (WebUi) for <a href="http://www.feralhosting.com/faq/view?question=2">rTorrent</a> which is a bittorrent client. rTorrent runs quietly in shell and you do not get to see it most of the time unless you want to. You use your web browser to load ruTorrent â€” ruTorrent connects to rTorrent behind the scenes and shows you what goes on in rTorrent, your bittorrent client.<br>
<br>
You might compare ruTorrent to a remote control, and rTorrent to a TV set.<br>
<br>
Apart from having an excellent, very much uTorrent-like user interface, ruTorrent extends rTorrent&#x27;s functionality considerably through the use of plugins. You will be able to create torrents, use RSS feeds, delete torrents with data, choose custom locations for data, use labels, sort your torrents by label, tracker, ratio, name, state, peers, seeds, creation date and more.<br>
<br>
<h3>Plugins</h3><br>
On Feral servers ruTorrent is autoinstalled (using the Software Manager page) with a recommended set of plugins.<br>
<br>
Explore all the <a href="https://github.com/Novik/ruTorrent/wiki/Plugins">available plugins</a>. Should you wish to try any of them apart from those that came preinstalled with your ruTorrent, just upload them to <code>&#x2F;rutorrent&#x2F;plugins</code>.<br>
<br>
<a href="https://www.feralhosting.com/faq/view?question=209">Rutorrent - Installing the mediashare plugin</a><br>
<a href="https://www.feralhosting.com/faq/view?question=184">Rutorrent - Colored Ratio Column Plugin</a><br>
<a href="https://www.feralhosting.com/faq/view?question=210">Rutorrent - Installing the fileshare plugin</a><br>
<a href="https://www.feralhosting.com/faq/view?question=126">Feralstats plugin for ruTorrent</a><br>
<br>
The idea is a simple one. You upload the plugin folder to your <code>rutorrent&#x2F;plugins</code> folder.<br>
<br>
<pre><code>~&#x2F;www&#x2F;username.server.feralhosting.com&#x2F;public_html&#x2F;rutorrent&#x2F;plugins</code></pre><br>
Where <code>username</code> is your Feral username and <code>server</code> is the name of the server that is hosting rutorrent.<br>
<br>
<h3>Troubleshooting</h3><br>
<strong>Error:</strong> ruTorrent fails to load and gets stuck showing the <code>loading</code> spinner<br>
<br>
Clear your browser cache (also known as <code>temporary files</code>, not just history), restart your browser and reload ruTorrent, in this particular order.<br>
<br>
<a href="http://support.mozilla.org/en-US/kb/how-clear-firefox-cache">Firefox</a><br>
<br>
<a href="https://support.google.com/chrome/answer/95582?hl=en">Chrome</a><br>
<br>
If this doesn&#x27;t work, one of your browser extensions&#x2F;plugins may be conflicting with ruTorrent. Test ruTorrent in your browser&#x27;s incognito&#x2F;private browsing mode. If this works, try disabling your extensions&#x2F;plugins one by one to see which is causing the conflict.<br>
<br>
<strong>Important note:</strong> AdBlock users on Eros: AdBlock blocks what it thinks are ads coming from domains that match the <code>&#x2F;eros.</code> rule, which includes <code>eros.feralhosting.com</code>. This will stop ruTorrent loading correctly over HTTPS, causing it to look like: <br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/eros.png"><br>
<br>
To prevent this, simply add <code>*.feralhosting.com</code> to your AdBlock exceptions list, or disable AdBlock.<br>
<br>
<strong>Error:</strong> <code>could not connect to rTorrent â€” check if rTorrent is really running</code> in message in the logger:<br>
<br>
This error means that ruTorrent failed to connect to rTorrent â€” rTorrent probably crashed.<br>
<br>
In most cases rTorrent will be restarted by the system automatically within 10 minutes, after which you&#x27;ll be able to load ruTorrent.<br>
<br>
If after 10 minutes you are still unable to load ruTorrent, then something is preventing rTorrent from being restarted.<br>
<br>
To manually restart your client, please refer to the following FAQ: <a href="https://www.feralhosting.com/faq/view?question=158">Restarting rtorrent, Deluge, Transmission, or MySQL</a><br>
<br>
<strong>Error:</strong> <code>Torrent was not passed to rTorrent</code> - This error mostly happens when the size of the <code>.torrent</code> you&#x27;re trying to load using ruTorrent is too big. As a workaround, upload the <code>.torrent</code> via FTP&#x2F;SFTP to<br>
<br>
<pre><code>~&#x2F;private&#x2F;rtorrent&#x2F;watch</code></pre><br>
This folder is called a <code>watch</code> folder â€” any torrent you put there will be loaded automatically in rTorrent within seconds.<br>
<br>
<h2>Common Issues</h2><br>
If you see this error with rutorrent error:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/nginxrutorrent.png"><br>
<br>
<pre><code>Webserver user doesn&#x27;t have read&#x2F;write&#x2F;execute access to the torrents directory. You cannot add torrents via ruTorrent.
rTorrent user must have read&#x2F;execute access to the torrents directory. You cannot add torrents via ruTorrent.</code></pre><br>
<h3>In Apache (The default on a new slot)</h3><br>
<pre><code>mkdir -p ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;rutorrent&#x2F;share&#x2F;users&#x2F;$(whoami)&#x2F;torrents</code></pre><br>
Then in your browser press&nbsp; <code>CTRL</code> + <code>F5</code> to refresh ruTorrent.<br>
<br>
<h3>In nginx:</h3><br>
Run this command in <a href="https://www.feralhosting.com/faq/view?question=12">SSH</a> and then reload rutorrent:<br>
<br>
<pre><code>mkdir -p ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;rutorrent&#x2F;share&#x2F;users&#x2F;$(whoami)&#x2F;torrents
wget -qO ~&#x2F;rutnginx.sh <a href="http://git.io/9vlcyw">http:&#x2F;&#x2F;git.io&#x2F;9vlcyw</a> &amp;&amp; bash ~&#x2F;rutnginx.sh</code></pre><br>
If neither solution works after refreshing rutorrent you may be experiencing some disk issues and should <a href="https://www.feralhosting.com/manager/tickets/new">open a ticket</a>.<br>
<br>
<h3>Public Trackers are red &#x2F; unreachable</h3><br>
In the rutorrent WebUi do this:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Installable%20software/ruTorrent%20-%20troubleshooting/publictorrents.png"><br>
<br>
