<h1>rTorrent - Notifications</h1>

        
There are different ways you can be notified of when torrents are added or completed in rTorrent. This guide covers just two of these services - Growl and Pushbullet.<br>
<br>
You&#x27;ll need to execute some commands via SSH (secure shell). If you&#x27;ve never used SSH commands the idea of using a terminal window may seem daunting. There is a guide on simply getting connected to your slot through SSH <a href="https://www.feralhosting.com/faq/view?question=12">here</a>. Commands are kept as simple as possible and in most cases will simply need to be copied and pasted into the terminal window (then executed by pressing the <code>Enter</code> key).<br>
<br>
<br>
<h2>Growl</h2>This script will send a Growl notification when you add a torrent and when the torrent is completed. By default it sends a notification for every torrent, but it can be customized based on watch folder or torrent label.<br>
<br>
Growl is available for <a href="http://www.prowlapp.com/faq.php&#x23;windows">Windows</a>, <a href="http://growl.info/">Mac</a> and <a href="http://mattn.github.io/growl-for-linux/">Linux</a>.<br>
<br>
<br>
<h3>Installing Growl</h3>Execute these commands to install the necessary script and libraries, and to configure rTorrent to use them:<br>
<br>
<pre><code>wget -qO ~&#x2F;growltorrent.py <a href="http://btp.pw/growltorrent.py">http:&#x2F;&#x2F;btp.pw&#x2F;growltorrent.py</a>
echo &quot;system.method.set_key = event.download.finished,notify_finished,&quot;execute=python,$PWD&#x2F;growltorrent.py,--finished,$d.get_name=&quot;&quot; &gt;&gt; ~&#x2F;.rtorrent.rc
echo &quot;system.method.set_key = event.download.inserted_new,notify_inserted_new,&quot;execute=python,$PWD&#x2F;growltorrent.py,--inserted-new,$d.get_name=&quot;&quot; &gt;&gt; ~&#x2F;.rtorrent.rc
pkill -fu &quot;$(whoami)&quot; &#x27;SCREEN -S rtorrent&#x27;
screen -dmS rtorrent rtorrent
easy_install --user gntp
</code></pre><br>
<br>
<h3>Configuring Growl</h3>You&#x27;ll need to edit the script to supply the relevant details. You can do this easily via SSH by executing <code>nano ~&#x2F;growltorrent.py</code><br>
<br>
In the following section replace the IP address with yours. The password field is optional but sensible - change test in the config file and set the same password within Growl itself. If you don&#x27;t want a password simply remove the word test (leaving the double quotes)<br>
<br>
<pre><code>CONFIG = {
&quot;hostname&quot;: &quot;123.45.67.89&quot;,
&quot;password&quot;: &quot;test&quot;
}
</code></pre><br>
Make sure that port <code>23053</code> is opened&#x2F;forwarded on your router and that Growl is set to allow network connections. You can test your setup by running the following commands on your slot (feel free to change the message!):<br>
<br>
<pre><code>python ~&#x2F;growltorrent.py --finished &quot;A torrent was finished&quot;
python ~&#x2F;growltorrent.py --inserted-new &quot;A torrent was added&quot;
</code></pre><br>
<br>
<h2>Pushbullet</h2>First of all you need an account at <a href="https://www.pushbullet.com/">Pushbullet</a> and the necessary API access token. You can get this from the My Account section of the Pushbullet site, clicking Create Access Token. You should make a note of this as it&#x27;s necessary to make use of the API.<br>
<br>
<br>
<h3>Creating and Configuring a Pushbullet Script</h3>Create the necessary file by executing this command:<br>
<br>
<pre><code>nano ~&#x2F;pushbullet.sh</code></pre><br>
Then paste the following, replacing <em>access_token</em> with the API access token you obtained earlier:<br>
<br>
<pre><code>#!&#x2F;bin&#x2F;bash
tname=$1
curl -u <em>access_token</em>: <a href="https://api.pushbullet.com/v2/pushes">https:&#x2F;&#x2F;api.pushbullet.com&#x2F;v2&#x2F;pushes</a> -d type=note -d title=&quot;$tname added to rTorrent&quot;
</code></pre><br>
You should then make it executable with this command:<br>
<br>
<pre><code>chmod +x ~&#x2F;pushbullet.sh</code></pre><br>
To test, execute this command:<br>
<br>
<pre><code>~&#x2F;pushbullet.sh push test</code></pre><br>
<br>
<h3>Configuring rTorrent</h3>To configure rTorrent to use the script simply execute the following:<br>
<br>
<pre><code>echo &quot;system.method.set_key = event.download.inserted_new,push_me,\&quot;execute=$PWD&#x2F;pushbullet.sh,\$d.get_name=\&quot;&quot; &gt;&gt; ~&#x2F;.rtorrent.rc
pkill -fu &quot;$(whoami)&quot; &#x27;SCREEN -S rtorrent&#x27; 
screen -dmS rtorrent rtorrent
</code></pre><br>
<br>
