<h1>SABnzbd - A how to</h1>

        
<strong>Please note that this software is not officially supported by Feral Hosting.</strong><br>
<br>
<strong>1:</strong> Download SABnzbd from <a href="http://sabnzbd.org/download/">here</a> to your slot. You can do this either by downloading it on your computer and then uploading it using FTP&#x2F;SFTP, or with the following command on your server using SSH:<br>
<br>
<pre><code>wget -qO ~&#x2F;SABnzbd.tar.gz <a href="https://github.com/sabnzbd/sabnzbd/releases/download/1.1.0/SABnzbd-1.1.0-src.tar.gz">https:&#x2F;&#x2F;github.com&#x2F;sabnzbd&#x2F;sabnzbd&#x2F;releases&#x2F;download&#x2F;1.1.0&#x2F;SABnzbd-1.1.0-src.tar.gz</a></code></pre><br>
<strong>2:</strong> Extract the files from the archive.<br>
<br>
<pre><code>tar xf ~&#x2F;SABnzbd.tar.gz</code></pre><br>
<strong>3:</strong> Edit the command needed to run SABnzbd.py and then run it.<br>
<br>
This is the command you will need to edit:<br>
<br>
<pre><code>screen -fa -dmS sabnzbd python ~&#x2F;SABnzbd-*&#x2F;SABnzbd.py --browser 0 --server $(hostname -f):PORT --https PORT</code></pre><br>
Please replace each <code>PORT</code> with a different number between <strong>6000</strong> and <strong>50000</strong>. Putting the https port one port above or below is easiest. Press enter to execute the command.<br>
<br>
If you pick the same port as someone else for either http or https you&#x27;ll see problems:<br>
<br>
1) You might get an error message, or;<br>
2) When you try to access it through your browser you&#x27;ll be greeted with a password prompt for someone else&#x27;s SABnzbd<br>
<br>
In either case you&#x27;ll need to kill the process and start it using a different port.<br>
<br>
You will be required to accept the invalid certificate in order to connect to the https port.<br>
<br>
For example:<br>
<br>
<pre><code>screen -fa -dmS sabnzbd python ~&#x2F;SABnzbd-*&#x2F;SABnzbd.py --browser 0 --server $(hostname -f):12345 --https 12346</code></pre><br>
<strong>4:</strong> Access SABnzbd through your browser.<br>
<br>
<strong>Important note:</strong> Make sure to use the https port in the URL,<br>
<br>
<pre><code><a href="https://server.feralhosting.com:PORT/sabnzbd/">https:&#x2F;&#x2F;server.feralhosting.com:PORT&#x2F;sabnzbd&#x2F;</a></code></pre><br>
For example:<br>
<br>
<pre><code><a href="https://peterpan.feralhosting.com:12346/sabnzbd/">https:&#x2F;&#x2F;peterpan.feralhosting.com:12346&#x2F;sabnzbd&#x2F;</a></code></pre><br>
You won&#x27;t have been given <br>
<br>
<strong>5:</strong> Follow the SABnzbd wizard to set up your Usenet account.<br>
<br>
<strong> Make sure you set-up a username and password under <code>Config &gt; General</code></strong><br>
<br>
<strong>6:</strong>&nbsp; You&#x27;ll need to make 3 folders, you can make the top level &#x27;downloads&#x27; folder wherever you wish:<br>
<br>
<pre><code>downloads</code></pre><br>
Inside this new folder make another 2 folder with these names:<br>
<br>
<pre><code>complete</code></pre><br>
<pre><code>incomplete</code></pre><br>
(<strong>Note, the two subfolders are required</strong>)<br>
<br>
Make sure you&#x27;ve set the proper path to these under <code>Config</code> in the web interface. <strong>You will need to use the full path</strong>. Below you&#x27;ll find a sample path:<br>
<br>
<pre><code>&#x2F;media&#x2F;DiskID&#x2F;home&#x2F;username&#x2F;private&#x2F;sab&#x2F;downloads&#x2F;</code></pre><br>
Connecting in SSH and restarting sabnzbd<br>
----<br>
<br>
<strong>Attach to the screen:</strong><br>
<br>
To the screen process using this command:<br>
<br>
<pre><code>screen -r sabnzbd</code></pre><br>
<strong>Kill the screen:</strong><br>
<br>
Use this command to kill the screen and the process if needed:<br>
<br>
<pre><code>screen -S sabnzbd -X quit</code></pre><br>
<strong>Restart&nbsp; the screen</strong><br>
<br>
You can restart it using just this command once you have used the main command above once as it configures the <code>ini</code> file.<br>
<br>
<pre><code>screen -fa -dmS sabnzbd python SABnzbd-*&#x2F;SABnzbd.py</code></pre><br>
<strong>Added NZB&#x27;s don&#x27;t download</strong><br>
<br>
There&#x27;s a bug in SabNZB that will prevent things from downloading if there&#x27;s a <code>www-browser</code> session running in the background. You can check for and quit any <code>www-browser</code> with the below&quot;<br>
<br>
<pre><code>ps x | grep www-browser | grep -v grep</code></pre><br>
If this returns a line containing &quot;www-browser&quot; run the below<br>
<br>
<pre><code>killall -9 -u $(whoami) www-browser</code></pre><br>
<br>
