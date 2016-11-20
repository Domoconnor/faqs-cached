<h1>CouchPotato - An automatic NZB and torrent downloader for Films</h1>

        
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
<h2>Installation</h2><br>
This script will set-up couchpotato and automatically proxypass it for you on Apache and&#x2F;or nginx, if it is installed and then run it in the background.<br>
<br>
<pre><code>wget -qO ~&#x2F;install.couchpotato <a href="http://git.io/3_iozg">http:&#x2F;&#x2F;git.io&#x2F;3_iozg</a> &amp;&amp; bash ~&#x2F;install.couchpotato</code></pre><br>
<strong>Important notes:</strong> <br>
<br>
<strong>1:</strong> If you get an empty blue screen in your browser press F5 (or CTRL + F5) to reload the page. That is all you should need to do.<br>
<br>
<strong>2:</strong> It may take a minute or two for the URL given in the script to work so be patient. Press F5 to reload the URL.<br>
<br>
<strong>Run the CouchPotato Wizard</strong><br>
<br>
Visit the URL shown in SSH after the script completes. It will be in this format:<br>
<br>
<pre><code><a href="https://server.feralhosting.com/username/couchpotato">https:&#x2F;&#x2F;server.feralhosting.com&#x2F;username&#x2F;couchpotato</a></code></pre><br>
<strong>Set a username and password</strong><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Software/CouchPotato%20-%20An%20automatic%20NZB%20and%20torrent%20downloader%20for%20Films/1.png"><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Software/CouchPotato%20-%20An%20automatic%20NZB%20and%20torrent%20downloader%20for%20Films/2.png"><br>
<br>
Make sure to set a username and password. This is important, otherwise anyone can get access, and automatically start downloads on your slot.<br>
<br>
<strong>Set the directory to download the NZB&#x2F;torrent to</strong><br>
<br>
<br>
Under Downloaders, the default option is Black Hole, which will just download the NZB&#x2F;torrent to a folder. You should set the directory to wherever your client watches.<br>
<br>
By default, that should be:<br>
<br>
<pre><code>&#x2F;media&#x2F;DiskID&#x2F;home&#x2F;username&#x2F;private&#x2F;client&#x2F;watch</code></pre><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Software/CouchPotato%20-%20An%20automatic%20NZB%20and%20torrent%20downloader%20for%20Films/3.png"><br>
<br>
Make sure to replace <strong>client</strong> with whichever client you use, for example, <code>&#x2F;private&#x2F;rtorrent&#x2F;watch</code>.<br>
<br>
CouchPotato also has support for other clients, such as Transmission, which allows it to interact directly with the client, but information for these isn&#x27;t be included here.<br>
<br>
<strong>6: Complete the rest of the wizard</strong><br>
<br>
Fill in any sites that you are a member of. <br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Software/CouchPotato%20-%20An%20automatic%20NZB%20and%20torrent%20downloader%20for%20Films/4.png"><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Software/CouchPotato%20-%20An%20automatic%20NZB%20and%20torrent%20downloader%20for%20Films/5.png"><br>
<br>
Enabling renaming is optional, and isn&#x27;t covered in this FAQ.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Software/CouchPotato%20-%20An%20automatic%20NZB%20and%20torrent%20downloader%20for%20Films/6.png"><br>
<br>
Optional:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Software/CouchPotato%20-%20An%20automatic%20NZB%20and%20torrent%20downloader%20for%20Films/7.png"><br>
<br>
Click this Green link to finish the wizard:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Software/CouchPotato%20-%20An%20automatic%20NZB%20and%20torrent%20downloader%20for%20Films/8.png"><br>
<br>
Login to couchpotato and enjoy!<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Software/CouchPotato%20-%20An%20automatic%20NZB%20and%20torrent%20downloader%20for%20Films/9.png"><br>
<br>
<h2>Rtorrent RPC:</h2><br>
<strong>Important note:</strong> You must have updated to nginx for this to work. Please see this FAQ: <a href="https://www.feralhosting.com/faq/view?question=231">Updating Apache to nginx</a><br>
<br>
<h3>Prerequisites:</h3><br>
1: You have installed rTorrent&#x2F;Rutorrent via your Feralhosting Manager for the relevant slot.<br>
<br>
2: You have updated to nginx<br>
<br>
<h3>Configuring the rTorrent rpc:</h3><br>
If you done both of these then you can proceed to use the rTorrent option for the Downloaders.<br>
<br>
Navigate to Settings&#x2F;Downloaders. Once there un-check the Blackhole option:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Software/CouchPotato%20-%20An%20automatic%20NZB%20and%20torrent%20downloader%20for%20Films/rpc1.png"><br>
<br>
Now select the <code>rTorrent</code> checkbox:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Software/CouchPotato%20-%20An%20automatic%20NZB%20and%20torrent%20downloader%20for%20Films/rpc2.png"><br>
<br>
Fill in the information like this:<br>
<br>
Where <code>username</code> is your Feral username and <code>server</code> is the name of the Feral server your slot is hosted on:<br>
<br>
<strong>Host:</strong> <code><a href="https://server.feralhosting.com/username/rtorrent/rpc">https:&#x2F;&#x2F;server.feralhosting.com&#x2F;username&#x2F;rtorrent&#x2F;rpc</a></code><br>
<strong>username:</strong> <code>rutorrent</code><br>
<strong>password:</strong> Is you Rutorrent WebUi password visiable in the Slot Details page for the relevant slot in your Feral Manager<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Software/CouchPotato%20-%20An%20automatic%20NZB%20and%20torrent%20downloader%20for%20Films/rpc3.png"><br>
<br>
The click on Test and you should get a successful connection.<br>
<br>
<h2>Deluge</h2><br>
To connect your Deluge daemon you&#x27;l need to obtain the daemon&#x27;s login details using the following commands:<br>
<br>
For the host and port (whichshould be specified together in the format <code>server.feralhosting.com:PORT</code>)<br>
<pre><code>hostname -f
sed -rn &#x27;s&#x2F;(.*)&quot;daemon_port&quot;: (.*),&#x2F;\2&#x2F;p&#x27; ~&#x2F;.config&#x2F;deluge&#x2F;core.conf</code></pre><br>
For the username and password:<br>
<pre><code>whoami
sed -rn &quot;s&#x2F;$(whoami):(.*):(.*)&#x2F;\1&#x2F;p&quot; ~&#x2F;.config&#x2F;deluge&#x2F;auth</code></pre><br>
<h2>Starting and restarting</h2>In order to restart the software the existing process should be killed. If the check below does not display a process number please proceed to step 3. These steps are tailored towards processes started by this FAQ.<br>
<br>
1.&nbsp; &nbsp; Check:<br>
<pre><code>pgrep -fu &quot;$(whoami)&quot; &quot;CouchPotato.py&quot;</code></pre>&nbsp; &nbsp; <br>
2.&nbsp; &nbsp; Kill:<br>
<pre><code>kill &quot;$(pgrep -fu &quot;$(whoami)&quot; &quot;CouchPotato.py&quot;)&quot;</code></pre>&nbsp; &nbsp; <br>
3.&nbsp; &nbsp; Restart: <br>
<pre><code>python ~&#x2F;.couchpotato&#x2F;CouchPotato.py --daemon</code></pre><br>
<strong>Important note:</strong> You can repeat step 1 after attempting to kill to check if it&#x27;s been shut down. Give the program at least 10 seconds to shut down at step 2 before trying to restart. If it refuses to exit then you have to force it to quit using this command instead:<br>
<br>
<pre><code>kill -9 &quot;$(pgrep -fu &quot;$(whoami)&quot; &quot;CouchPotato.py&quot;)&quot;</code></pre><br>
<br>

