<h1>Multiple instances - rtorrent and rutorrent</h1>

        
<br>
<strong>Important notice:</strong> These custom installations are <strong>NOT</strong> restarted automatically. If you need to restart the process look for this file: <code>~&#x2F;multirtru.restart.txt</code> in your slot root. This file has the custom restart commands for any custom installation you have created using the bash script. Copy and paste the command you need into your SSH window.<br>
<br>
<h2>Bash script</h2><br>
This script will:<br>
<br>
<strong>1:</strong> Ask you for a suffix for this unique instance of rtorrent and rutorrent.<br>
<strong>2:</strong> Create you a fresh install based on the Feral rtorrent and rutorrent installation. Colored ratio and Feralstats plugins included.<br>
<strong>3:</strong> Make the required edits to some using this suffix so it becomes an independent installation.<br>
<strong>4:</strong> Ask you for a username and password to password protect the folder. All instances are unique and will not clash even if the same username and password is used in another instance.<br>
<strong>5:</strong> Start rtorrent in a screen using the unique <code>rtorrent.rc</code> for this instance.<br>
<strong>6:</strong> Create a file called <code>~&#x2F;multirtru.restart.txt</code> in your slot root that contains the restart command for any custom installation you have created.<br>
<strong>7:</strong> If you are using nginx it will also create the <code>rpc</code> info required to use transdroid with this custom installation.<br>
<strong>8:</strong> Lets you delete a custom installation and all associated files and folders and reloads Apache&#x2F;Nginx<br>
<br>
It will <strong>NOT</strong> damage your existing installation or overwrite custom instances if the same suffix is used.<br>
<br>
<pre><code>wget -qO ~&#x2F;install.multirtru <a href="http://git.io/_zVu0A">http:&#x2F;&#x2F;git.io&#x2F;_zVu0A</a> &amp;&amp; bash ~&#x2F;install.multirtru</code></pre><br>
<h2>Important: Read this first</h2><br>
When creating a new instance of rutorrent there is an important behaviour using the <code>.htaccess</code> and <code>.htpasswd</code> combo that you need to understand.<br>
<br>
The default rutorrent <code>.htaccess</code> has a line like this:<br>
<br>
<pre><code>AuthName &quot;username&quot;</code></pre><br>
And the default rutorrent <code>.htpasswd</code> has a line like this, which is the md5 salted password for this user:<br>
<br>
<pre><code>username:$apr1$MPG6YdI6$8qwQtGQj5jHoL62L2&#x2F;rhg1</code></pre><br>
If you have a new instance that uses the same AuthName but the relevant <code>.htpasswd</code> does not contain a matching username and md5 salt you will start to confuse rutorrent because this is how it authorizes you.<br>
<br>
The script deals with this by giving each instance a unique AuthName based on the suffix used, such as:<br>
<br>
<pre><code>AuthName &quot;rutorrent-3&quot;</code></pre><br>
When you clone the existing installation you will need to take this into account, so to sum it up:<br>
<br>
When you want to be able to log into a single instance and be logged into multiple instance simultaneously you will need to:<br>
<br>
1: Make sure all instances and their <code>.htaccess</code> have the same AuthName. The default is<br>
<br>
<pre><code>AuthName &quot;username&quot;</code></pre><br>
2: All linked to <code>.htpasswd</code> files have the the same user and more importantly, the same md5 salt. Having the same username and password in not enough. It must be the same salt.<br>
<br>
<h2>Running multiple instances of rtorrent and rutorrent</h2><br>
You can do this in two ways.<br>
<br>
<strong>1:</strong> You can clone an existing installation. So this can be useful if you want to preserve customisations and settings.<br>
<br>
<strong>2:</strong> You can use template files which mimics almost identically a Feral fresh install. The bash script uses this option<br>
<br>
If you want to use option 2 then use the bash script.<br>
<br>
If you want to clone an existing installation in whatever state it currently is use the FAQ.<br>
<br>
<strong>Important note:</strong> Please make sure you have installed rtorrent&#x2F;rutorrent using the <a href="https://www.feralhosting.com/manager/">[b]Install Software[&#x2F;b] link in your Manager</a><br>
<br>
This is quite easy to do once you have understood the basic idea. We will:<br>
<br>
<strong>1:</strong> Clone the existing installation and related files and folders, giving them a new name.<br>
<strong>2:</strong> We edit some files to reflect the new paths.<br>
<strong>3:</strong> We run our new instance in a custom named screen.<br>
<strong>4:</strong> Visit the new Web Gui in your WWW and use it.<br>
<strong>5:</strong> Repeat as many times as needed.<br>
<br>
<h2>Clone our existing installation</h2><br>
<strong>1:</strong> Clone our <code>~&#x2F;rtorrent.rc</code><br>
<br>
<pre><code>cp -f ~&#x2F;.rtorrent.rc ~&#x2F;.rtorrent-1.rc</code></pre><br>
<strong>2:</strong> Clone the rutorrent Web Gui<br>
<br>
<pre><code>cp -rf ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;rutorrent&#x2F;. ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;rutorrent-1</code></pre><br>
<strong>3:</strong> Create some directories for our new instance.<br>
<br>
<pre><code>mkdir -p ~&#x2F;private&#x2F;rtorrent-1&#x2F;data ~&#x2F;private&#x2F;rtorrent-1&#x2F;watch ~&#x2F;private&#x2F;rtorrent-1&#x2F;work</code></pre><br>
<strong>Important note:</strong> Take note of the suffix <code>-1</code> used in all cases. rtorrent to rtorrent-1 and rutorrent to rutorrent-1.<br>
<br>
<h2>Edit the files - rtorrent</h2><br>
We must now make some edits to these files so that our new rtorrent and rutorrent will work together.<br>
<br>
<pre><code>~&#x2F;rtorrent-1.rc</code></pre><br>
<pre><code>~&#x2F;www&#x2F;username.feralhosting.com&#x2F;public_html&#x2F;rutorrent-1&#x2F;conf&#x2F;config.php</code></pre><br>
<strong>Important note:</strong> EOL is important for this file, it must be UNIX&#x2F;LF if using a text editor over FTP. Please see this FAQ: <a href="https://www.feralhosting.com/faq/view?question=219">Text editing - Over FTP or SFTP</a><br>
<br>
Open the <code>~&#x2F;rtorrent-1.rc</code>:<br>
<br>
<pre><code>nano -w ~&#x2F;.rtorrent-1.rc</code></pre><br>
Edit these 5 lines in you <code>~&#x2F;rtorrent-1.rc</code>, changing the paths to reflect the new locations with the new suffix. This FAQ uses the examples of <code>-1</code>:<br>
<br>
<pre><code>directory = media&#x2F;DiskID&#x2F;home&#x2F;username&#x2F;private&#x2F;rtorrent&#x2F;data
session = media&#x2F;DiskID&#x2F;home&#x2F;username&#x2F;private&#x2F;rtorrent&#x2F;work
schedule = watch_directory, 5, 60, load_start=media&#x2F;DiskID&#x2F;home&#x2F;username&#x2F;private&#x2F;rtorrent&#x2F;watch&#x2F;*.torrent
execute = {sh,-c,&#x2F;usr&#x2F;bin&#x2F;php media&#x2F;DiskID&#x2F;home&#x2F;username&#x2F;www&#x2F;username.server.feralhosting.com&#x2F;public_html&#x2F;rutorrent&#x2F;php&#x2F;initplugins.php username &amp;}
scgi_local = media&#x2F;DiskID&#x2F;home&#x2F;username&#x2F;private&#x2F;rtorrent&#x2F;.socket</code></pre><br>
For this example we make these changes:<br>
<br>
<code>rtorrent</code> to <code>rtorrent-1</code><br>
<br>
<pre><code>directory = media&#x2F;DiskID&#x2F;home&#x2F;username&#x2F;private&#x2F;rtorrent-1&#x2F;data</code></pre><br>
<code>rtorrent</code> to <code>rtorrent-1</code><br>
<br>
<pre><code>session = media&#x2F;DiskID&#x2F;home&#x2F;username&#x2F;private&#x2F;rtorrent-1&#x2F;work</code></pre><br>
<code>rtorrent</code> to <code>rtorrent-1</code><br>
<br>
<pre><code>schedule = watch_directory, 5, 60, load_start=media&#x2F;DiskID&#x2F;home&#x2F;username&#x2F;private&#x2F;rtorrent-1&#x2F;watch&#x2F;*.torrent</code></pre><br>
<code>rutorrent</code> to <code>rutorrent-1</code><br>
<br>
<pre><code>execute = {sh,-c,&#x2F;usr&#x2F;bin&#x2F;php media&#x2F;DiskID&#x2F;home&#x2F;username&#x2F;www&#x2F;username.server.feralhosting.com&#x2F;public_html&#x2F;rutorrent-1&#x2F;php&#x2F;initplugins.php username &amp;}</code></pre><br>
<code>rtorrent</code> to <code>rtorrent-1</code><br>
<br>
<pre><code>scgi_local = media&#x2F;DiskID&#x2F;home&#x2F;username&#x2F;private&#x2F;rtorrent-1&#x2F;.socket</code></pre><br>
And then save the changes. in nano you would press and hold <code>CTRL</code> and then press <code>x</code>. Press <code>y</code> to confirm and exit<br>
<br>
<h2>Edit the files - rutorrent</h2><br>
Open your <code>~&#x2F;www&#x2F;username.feralhosting.com&#x2F;public_html&#x2F;rutorrent-1&#x2F;conf&#x2F;config.php</code><br>
<br>
<pre><code>nano -w ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;rutorrent-1&#x2F;conf&#x2F;config.php</code></pre><br>
Edit this line, changing the paths to reflect the new locations.<br>
<br>
<pre><code>$scgi_host = &#x27;unix:&#x2F;&#x2F;&#x27;.$_pw[&#x27;dir&#x27;].&#x27;&#x2F;private&#x2F;rtorrent&#x2F;.socket&#x27;;</code></pre><br>
For this example it is:<br>
<br>
<pre><code>$scgi_host = &#x27;unix:&#x2F;&#x2F;&#x27;.$_pw[&#x27;dir&#x27;].&#x27;&#x2F;private&#x2F;rtorrent-1&#x2F;.socket&#x27;;</code></pre><br>
<h2>Starting your new instance</h2><br>
Load your custom instance in a new screen window.<br>
<br>
<pre><code>screen -fa -dmS rtorrent-1 rtorrent -n -o import=~&#x2F;.rtorrent-1.rc</code></pre><br>
If you see the screen is terminating error, do this:<br>
<br>
<pre><code>screen -fa -S rtorrent-1</code></pre><br>
The do this:<br>
<br>
<pre><code>rtorrent -n -o import=~&#x2F;.rtorrent-1.rc</code></pre><br>
You will now see what the actual error is.<br>
<br>
Press and hold <code>CTRL</code> and <code>a</code>, then press <code>d</code> to detach from this screen session.<br>
<br>
<h2>More instances</h2><br>
Bascially follow this FAQ again, as many times as you want and just change the suffix.<br>
<br>
<pre><code>rtorrent-2 and rutorrent-2
rtorrent-3 and rutorrent-3
rtorrent-4 and rutorrent-4
rtorrent-5 and rutorrent-5
rtorrent-6 and rutorrent-6</code></pre><br>
And so on. It is pretty much that simple.<br>
<br>

