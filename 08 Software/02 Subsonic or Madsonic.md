<h1>Subsonic or Madsonic</h1>

        
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
<h2>Important notes:</h2><br>
- Default mp3 bitrate is set in <code>Settings&#x2F;Players&#x2F;Max bitrate</code> per selected player<br>
- Subsonic will ask for a license key after 30 days, that you can get by donating to the creator of the program. After 30 days, video streaming and mobile application support are deactivated. You can use the bash script to install Madsonic instead, that has no such restrictions but you have to pay for the Madsonic mobile app.<br>
- HTML5 - <a href="https://chrome.google.com/webstore/detail/minisub/jccdpflnecheidefpofmlblgebobbloc">Minisub Chrome App</a> (if you use https you must visit the subsonic server URL and accept the cert first<br>
- Works with the IOS and Android apps. Madsonic may behave differently with some apps that were designed to support Subsonic.<br>
<br>
<a href="http://www.subsonic.org/pages/apps.jsp">Subsonic Device options</a><br>
<br>
<a href="https://play.google.com/store/apps/details?id=github.madmarty.madsonic">Madsonic Android Play Store</a><br>
<br>
<a href="http://www.amazon.com/Madsonic-Media-Streamer/dp/B00COJ4G1O">Madsonic Android Amazon Store</a><br>
<br>
<h2>Subsonic or Madsonic automatic installation using a bash script:</h2><br>
<strong>install.subsonic.sh&#x2F;install.madsonic.sh bash script features:</strong><br>
<br>
- Installs Java 1.7 (kept up to date with current updates)<br>
- Installs Subsonic or Madsonic servers. Can be installed side by side since they use separate locations and URLs<br>
- Detects previous installations giving the option to remove, update or quit.<br>
- Fully configures the start-up script. Unique to each user.<br>
- Option to enter a path to a media folder during installation.<br>
- Creates a custom script to <code>restart&#x2F;start&#x2F;kill</code> subsonic&#x2F;madsonic (RSK) when the script is executed.<br>
- Will <code>proxypass</code> automatically on Nginx or Apache so the URL will be in the valid SSL format <code><a href="https://server.feralhosting.com/username/subsonic">https:&#x2F;&#x2F;server.feralhosting.com&#x2F;username&#x2F;subsonic</a></code> or <code><a href="https://server.feralhosting.com/username/madsonic">https:&#x2F;&#x2F;server.feralhosting.com&#x2F;username&#x2F;madsonic</a></code>. <br>
- Lets you easily move between Apache or nginx. You can simply run current the script to apply the proxypass to an existing installation if you update to nginx.<br>
<br>
<strong>For Subsonic:</strong><br>
<br>
<pre><code>wget -qO ~&#x2F;install.subsonic <a href="http://git.io/bGZT">http:&#x2F;&#x2F;git.io&#x2F;bGZT</a> &amp;&amp; bash ~&#x2F;install.subsonic</code></pre><br>
<strong>For Madsonic:</strong><br>
<br>
<pre><code>wget -qO ~&#x2F;install.madsonic <a href="http://git.io/Eq97bg">http:&#x2F;&#x2F;git.io&#x2F;Eq97bg</a> &amp;&amp; bash ~&#x2F;install.madsonic</code></pre><br>
Then follow the progress in your terminal. Some steps require user input. You will be asked whether you want to install Subsonic or Madsonic.<br>
<br>
Once this script has been executed once, the <code>install.subsonic.sh</code>&#x2F;<code>install.madsonic.sh</code> is copied to the <code>~&#x2F;bin</code> directory as <code>install.madsonic</code> and the <code>subsonicrsk</code>&#x2F;<code>madsonicrsk</code> is created in the <code>~&#x2F;bin</code><br>
<br>
Now you can simply type this from anywhere in SSH to execute the installer script: <br>
<br>
<pre><code>install.subsonic
install.madsonic</code></pre><br>
<h2>Subsonic removal</h2><br>
Run the script again to kill all be given the option to remove Subsonic or Madsonic. It will kill all Java processes and removes the folders and files the script created. Then you can simply run the script again to reinstall.<br>
<br>
<h2>subsonicrsk &#x2F; madsonicrsk</h2><br>
Execute the <code>restart&#x2F;start&#x2F;kill</code> script like this (requires you ran the relevant installer script at least once):<br>
<br>
<pre><code>subsonicrsk
madsonicrsk</code></pre><br>
The <code>restart&#x2F;start&#x2F;kill</code> (rsk) script does these things:<br>
<br>
- Displays the URL used to access Subsonic when installed.<br>
- Displays the last generated PID for the process when was installed using the <code>install.subsonic.sh</code> or started using the <code>subsonicrsk</code><br>
- Lists all Java processes<br>
- Offers to Kill the PID that was generated the last time subsonic was installed using the <code>install.subsonic.sh</code> or started using the <code>subsonicrsk</code><br>
- Offers to Kill ALL java processes currently running.<br>
- Start the <code>install.subsonic.sh</code> or manually installed version.<br>
<br>
To update these scripts you must run the <code>install.subsonic.sh</code> script again.<br>
<br>
<h2>Crontab and Subsonic.</h2><br>
This script creates a special mini bash script for restarting the Subsonic process located at <code>~&#x2F;bin&#x2F;subsonicron</code>. This bash script will check to if the <code>PID</code> created by Subsonic or Madsonic the last time it was run is currently alive. If it is alive, the script does nothing, to prevent duplicate processes being run. If the process is not alive the script will restart Subsonic or Madsonic. So if you add it to your crontab using the command below you can make sure the process is always available.<br>
<br>
Use these commands to edit your crontab:<br>
<br>
This crontab command will check to restart at reboot:<br>
<br>
Run at reboot:<br>
<br>
Subsonic:<br>
<br>
<pre><code>@reboot bash -l ~&#x2F;bin&#x2F;subsonicron</code></pre><br>
Madsonic:<br>
<br>
<pre><code>@reboot bash -l ~&#x2F;bin&#x2F;madsonicron</code></pre><br>
Check every minute. You can customise the timing before you use the command:<br>
<br>
Subsonic:<br>
<br>
<pre><code>* * * * * bash -l ~&#x2F;bin&#x2F;subsonicron</code></pre><br>
Madsonic:<br>
<br>
<pre><code>* * * * * bash -l ~&#x2F;bin&#x2F;madsonicron</code></pre><br>
<h2>Notes:</h2><br>
To install or upgrade to the latest stable Madsonic, edit the relevant lines in the Custom Variables section of install.madsonic to point to the <a href="https://github.com/feralhosting/feralfilehosting/releases">current release</a>.<br>
<br>
Avconv: A static build found here can also be used.<br>
<br>
<a href="http://johnvansickle.com/libav/">http:&#x2F;&#x2F;johnvansickle.com&#x2F;libav&#x2F;</a><br>
<br>
<a href="https://bitbucket.org/feralhosting/feralfiles/downloads/libav.09.02.2014.zip">libav.09.02.2014.zip</a><br>
<br>
Use these commands to download and extract a static build 06.14.2013 ready for use:<br>
<br>
<pre><code>wget -qO ~&#x2F;avconv.zip <a href="https://bitbucket.org/feralhosting/feralfiles/downloads/libav.09.02.2014.zip">https:&#x2F;&#x2F;bitbucket.org&#x2F;feralhosting&#x2F;feralfiles&#x2F;downloads&#x2F;libav.09.02.2014.zip</a>
mkdir -p ~&#x2F;private&#x2F;subsonic&#x2F;transcode
unzip -qo ~&#x2F;avconv.zip -d ~&#x2F;private&#x2F;subsonic&#x2F;transcode
chmod 700 ~&#x2F;private&#x2F;subsonic&#x2F;transcode&#x2F;{avconv,avconv-10bit,avprobe,qt-faststart}
rm -f ~&#x2F;avconv.zip</code></pre><br>
The you need to add a new <code>Settings&#x2F;Transcoding&#x2F;Add transcoding</code> in Subsonic or Madsonic:<br>
<br>
<pre><code>Name: avconv mp3
Convert From: ogg oga aac m4a flac wav wma aif aiff ape mpc shn
Convert To: mp3
Step 1: avconv -i %s -b %bk -q 0 -loglevel error -f mp3 -
Step 2: is blank since its not needed</code></pre><br>
credits: <a href="http://forum.subsonic.org/forum/viewtopic.php?f=2&#x26;t=10655">subsonic forum</a>
<br>