<h1>RSS - Using Rssdler on your Feral slot</h1>

        
<a href="http://code.google.com/p/rssdler/">Rssdler</a> is a utility to automatically download enclosures and other objects linked to from various types of RSS feeds. Works well on podcasts, videocasts, and torrents. This tutorial will guide you through setting up rssdler on your Feral box. (note: Waffles.FM prevents accessing RSS feeds directly on your Feral box. See <a href="https://www.feralhosting.com/faq//view?question=39">this guide</a> for a possible workaround.)<br>
<br>
<h3>Downloading and Installing Rssdler Using SSH (recommended):</h3><br>
Connect to your server using an SSH client: Here is a guide on <a href="https://www.feralhosting.com/faq/view?question=12">using putty</a>:<br>
<br>
<pre><code>cd</code></pre><br>
Moves you to your home directory. You should be here by default, but just to be safe execute this command to start.<br>
<br>
<pre><code>mkdir -p ~&#x2F;bin ~&#x2F;.rssdler</code></pre><br>
Makes directories named <code>.rssdler</code> and <code>bin</code> at <code>~&#x2F;</code> which is short your your HOME directory.<br>
<br>
<h3>Download and prepare rssdler</h3><br>
<pre><code>wget -qO ~&#x2F;rssdler.tar.gz <a href="http://rssdler.googlecode.com/files/rssdler-0.4.2.tar.gz">http:&#x2F;&#x2F;rssdler.googlecode.com&#x2F;files&#x2F;rssdler-0.4.2.tar.gz</a>
tar -xzf ~&#x2F;rssdler.tar.gz
cp -rf ~&#x2F;rssdler042&#x2F;. ~&#x2F;.rssdler
rm -f ~&#x2F;rssdler.tar.gz &amp;&amp; rm -rf ~&#x2F;rssdler042&#x2F;</code></pre><br>
Downloads rssdler, extracts it, copies the contents, removes the tar and unpacked folder.<br>
<br>
<pre><code>touch ~&#x2F;.rssdler&#x2F;config.txt</code></pre><br>
Creates the config.txt<br>
<br>
<pre><code>echo -e &#x27;#!&#x2F;bin&#x2F;bash\npython &#x27;$HOME&#x27;&#x2F;.rssdler&#x2F;rssdler.py --run&#x27; &gt; ~&#x2F;bin&#x2F;rssdler
chmod 700 ~&#x2F;bin&#x2F;rssdler</code></pre><br>
This echo creates a simple script in the <code>~&#x2F;bin</code> directory so we can easily run rssdler with a screen in a moment. We must then make it executable. If you get permission errors when running the screen command you did not do this step. Execute these two commands and that is the bash script created using SSH.<br>
<br>
<pre><code>echo $HOME</code></pre><br>
The last command with show you the path info you need to edit the <code>config.txt</code><br>
<br>
<em>Optional:&nbsp; Using the nano command below you can edit the file:</em><br>
<br>
<pre><code>nano -w ~&#x2F;.rssdler&#x2F;config.txt</code></pre><br>
Opens the blank new file in nano ready to paste in the custom config details in the paste bin link:<br>
<br>
Or you can edit the new <code>~&#x2F;.rssdler&#x2F;config.txt</code> file with ftp and a text editor.<br>
<br>
<h3>The example config.txt</h3><br>
<a href="http://pastebin.com/QTakP9mj">Use this pastebin example config.txt</a><br>
<br>
This <code>config.txt</code> must be edited a little to work on your slot. Please read the next section.<br>
<br>
A commented config file with all available options can be found <a href="http://code.google.com/p/rssdler/wiki/CommentedConfig">commented config here</a>. Also here, a <a href="http://pastebin.com/4VHjFPwX">pastebin rssdler commented version</a><br>
<br>
The <code>config.txt</code> you need to populate with the content of the example file can be found here:<br>
<br>
<pre><code>&#x2F;media&#x2F;DISKiD&#x2F;home&#x2F;USERNAME&#x2F;.rssdler&#x2F;config.txt</code></pre><br>
Note: The previous SSH commands created this file four you using the <code>touch</code> command.<br>
<br>
<h3>config.txt settings:</h3><br>
1: We suggest that you use the temporary download directories to test your set-up before using it properly as used in the config.txt:<br>
<br>
These are already configured in the example <code>config.txt</code> linked above. You just need to change the path to that used on your slot. These are the parts you must edit:<br>
<br>
In the Global section:<br>
<br>
<pre><code>downloadDir = &#x2F;media&#x2F;DISKiD&#x2F;home&#x2F;USERNAME&#x2F;private&#x2F;TESTdownload
workingDir = &#x2F;media&#x2F;DISKiD&#x2F;home&#x2F;USERNAME&#x2F;.rssdler</code></pre><br>
And in the example sections:<br>
<br>
<pre><code>directory = &#x2F;media&#x2F;DISKiD&#x2F;home&#x2F;USERNAME&#x2F;private&#x2F;TESTlegittorrents
directory = &#x2F;media&#x2F;DISKiD&#x2F;home&#x2F;USERNAME&#x2F;private&#x2F;TESTmininova</code></pre><br>
Be sure to substitute <code>DISKiD</code> and <code>USERNAME</code> with your actual disk ID username in the config file. use this command to find your info:<br>
<br>
Remember to use this command in SSH:<br>
<br>
<pre><code>echo $HOME</code></pre><br>
This will give you the info you need to copy and replace in the <code>config.txt</code><br>
<br>
2: In the last section of the <code>config.txt</code> we have three profiles, one for each feed. You create a new profile by creating a square bracketed name, for example: <code>[Cartoons]</code> . All info after that comes after this is related to this profile until you create a new square bracketed profile such ass <code>[Movies]</code>. <br>
<br>
What makes this quite useful is that if you can specify which feed goes where using the <code>directory = field. If you leave this blank things will be download to the folder specified in the </code>[Global]<code> section. In this the example config.txt the global value is </code>~&#x2F;private&#x2F;TESTdownload` <br>
<br>
The example <code>config.txt</code> has three working profiles, two with custom directories and one that has no directory specified and will therefore use the global value. This is so you can easily see how to set up your profiles.<br>
<br>
- Mininova - custom directory ~ 20 torrents in the feed<br>
- Legittorrents - custom directory ~ 20 torrents in the feed<br>
- OpenOffice - global directory ~ 940 torrents in the feed. Uses filters to only return ~ 38 Linux x86_64 results.<br>
<br>
In my testing TESTmininova was populated first, then TESTdownload then TESTlegittorrents. This might not be the same for you though.<br>
 <br>
Please see the example <code>config.txt</code> and Configuring Filters section&nbsp; further on for examples of this.<br>
<br>
3: This application seems to downloads one rss feed at a time and takes a second or more per rss item. This means if your feed has hundreds of items that the app needs to get in order to be up to date, you might be in for a long wait.<br>
<br>
So if you are using a feed with many many items consider this before you think something is not working. Try using some filters on this feed first.<br>
<br>
There are some demo filters with the OpenOffice Linux feed.<br>
<br>
4: URL encoding: This link below caused the application to fail because of <code>%</code> in the url. You must escape it with another <code>%</code> symbol for it to work so:<br>
<br>
This:<br>
<br>
<pre><code>link = <a href="http://borft.student.utwente.nl/%7Emike/oo/bt.rss">http:&#x2F;&#x2F;borft.student.utwente.nl&#x2F;%7Emike&#x2F;oo&#x2F;bt.rss</a></code></pre><br>
becomes:<br>
<br>
<pre><code>link = <a href="http://borft.student.utwente.nl/%%7Emike/oo/bt.rss">http:&#x2F;&#x2F;borft.student.utwente.nl&#x2F;%%7Emike&#x2F;oo&#x2F;bt.rss</a></code></pre><br>
Now it will work.<br>
<br>
5: The working directory: this is set to use the <code>~&#x2F;.rssdler&#x2F;</code> directory by default. This means that anything that does not use a full path is treated and being relative to this location.<br>
<br>
6: Pay special attention to the <code>scanMins</code> setting â€” this is how often rssdler will be checking the feed. Don&#x27;t set this value too low â€” 15 minutes should be safe to start with. Consult with your tracker regarding the minimum allowed Rss poll frequency on this specific tracker. Don&#x27;t joke with it â€” your IP will most likely get banned by the tracker if you check the feed way too frequently.<br>
<br>
7: Please note that we are specifying no filters for our tests feed apart from the Linux ones (since there was over 900) â€” this means that rssdler will download all .torrents in the feed not filtering them for now by any criteria.<br>
<br>
It&#x27;s time to test our set-up.<br>
<br>
<h3>Launching rssdler in Screen and testing Your set-up</h3><br>
<a href="https://www.feralhosting.com/faq/view?question=12">SSH</a> to your server. Type:<br>
<br>
<pre><code>screen -dmS myrssdler rssdler</code></pre><br>
This command will start a screen session in the background called <code>myrssdler</code> using the bash script we created in <code>~&#x2F;bin&#x2F;rssdler</code><br>
<br>
After you have done this type:<br>
<br>
<pre><code>screen -ls</code></pre><br>
This will show you all active screens and we are looking for something like this:<br>
<br>
<pre><code>11431.myrssdler	(30&#x2F;04&#x2F;13 16:51:12)	(Detached)</code></pre><br>
If you do not see this then most likely something went wrong when rssdler tried to start based on your <code>config.txt</code> additions (all examples have been tested to work). You can check the <code>~&#x2F;.rssdler&#x2F;downloads.log</code> for any information.<br>
<br>
I found the easiest way to figure out was wrong when the app would not start was to open and attach to a screen then run the application to see the error:<br>
<br>
<pre><code>screen -S myrssdler</code></pre><br>
Then inside the screen type:<br>
<br>
<pre><code>rssdler</code></pre><br>
You should now see what was causing the error and know where to start troubleshooting.<br>
<br>
To check on rssdler, you will just reattach this screen session by typing <code>screen -r myrssdler</code>. You will be able to leave rssdler running in the background by detaching the screen session <code>ctrl + a + d</code>. Read our <a href="https://www.feralhosting.com/faq/view?question=2">rTorrent tutorial</a> or the more general tutorial on <a href="https://www.feralhosting.com/faq/view?question=16">using Screen</a> to familiarize yourself with the concept.<br>
<br>
If everything was set up correctly and you made no typos in the configuration file, rssdler should start up, read the config file, download .torrents from your test feed and store them in your test directory.<br>
<br>
<em>(Please note that there&#x27;s no need to restart rssdler for it to pick the changes you make to the config file. You can edit the config, and rssdler will pick up the changes on the fly.)</em><br>
<br>
Leave rssdler running for a while and observe it in Screen. Once you are satisfied with the results, you can edit config.txt and change the download directory to your actual watch folder.<br>
<br>
Please be very careful with this script. Filters need to be set-up correctly for rssdler to download only what you want, and not everything in the feed. Errors in the config may harm your ratio or, in the worst scenario, destroy it completely.<br>
<br>
<strong>ATTENTION: Do test your set-up properly before sending .torrents to your actual watch folder! Configure your filters and leave rssdler running for about a day, then examine the download directory to see what it actually downloaded and if your filters are actually filtering out the right stuff!</strong><br>
<br>
<h3>Configuring Filters</h3><br>
This part of the tutorial needs to be expanded on. For now please consult <a href="http://code.google.com/p/rssdler/wiki/CommentedConfig">this file</a> for reference.<br>
<br>
<strong>Example 1:</strong><br>
<br>
<pre><code>[Example1]
link = <a href="http://rss.torrentleech.org/rss.php?passkey=XXXXXXXXX--EDIT-ME--XXXXXXXXXX">http:&#x2F;&#x2F;rss.torrentleech.org&#x2F;rss.php?passkey=XXXXXXXXX--EDIT-ME--XXXXXXXXXX</a>
maxSize = 400
directory =&#x2F;media&#x2F;DISKiD&#x2F;home&#x2F;USERNAME&#x2F;private&#x2F;rtorrent&#x2F;TEST
regextrue = (Dexter)
regexfalse = (hr|720|1080|ntsc|x264|sct)
nosave = False</code></pre><br>
<strong>Example 2:</strong><br>
<br>
<pre><code>[Example2]
link = <a href="http://rss.torrentleech.org/rss.php?passkey=XXXXXXXXX--EDIT-ME--XXXXXXXXXX">http:&#x2F;&#x2F;rss.torrentleech.org&#x2F;rss.php?passkey=XXXXXXXXX--EDIT-ME--XXXXXXXXXX</a>
maxSize = 0
minSize = 195
nosave = False
# checkTime1Day = Mon
# checkTime1Start = 18
# checkTime1Stop = 21
regextrue = (Prison.Break|Heroes|Gossip.Girl|Sons.of.Anarchy|Fringe)
regexfalse = (HEBSUB|D0|DVDR|DVD-R|DVDRip)</code></pre><br>
Please note that no download directory was specified in <code>Example 2</code> â€” rssdler will use the global setting in this case.<br>
<br>
The lines starting with a # are commented out â€” this means rssdler will ignore these settings when parsing the config.<br>
<br>
You can learn about all available settings <a href="http://code.google.com/p/rssdler/wiki/HelpMessage">here</a>.<br>
<br>
If you need help on using regular expressions, you can find it <a href="http://www.regular-expressions.info/quickstart.html">here</a>. You can use this <a href="http://erik.eae.net/playground/regexp/regexp.html">online tool</a> for testing your regex.<br>
<br>
Provided your filters are configured correctly, these settings should suffice for running rssdler on most trackers.<br>
<br>
<strong>For some trackers however it&#x27;s necessary to have a properly formatted cookies.txt file in the .rssdler dir. Please search the tracker&#x27;s forum for information on how to configure this file.</strong><br>
<br>
<h3>Advanced: Command Line Options</h3><br>
To add these commands all you have to do is edit the <code>~&#x2F;bin&#x2F;rssdler</code> bash script and add your options there. The kill the PID and run the screen command above again.<br>
<br>
<pre><code>--config&#x2F;-c can be used with all the options except --comment-config, --help
--comment-config: Prints a commented config file to stdout
--help&#x2F;-h: print the short help message (command line options)
--full-help&#x2F;-f: print the complete help message (quite long)
--run&#x2F;-r: run according to the configuration file
--runonce&#x2F;-o: run only once then exit
--daemon&#x2F;-d: run in the background (Unix-like only)
--kill&#x2F;-k: kill the currently running instance (may not work on Windows)
--config&#x2F;-c: specify a config file (default &#x2F;home&#x2F;james&#x2F;.rssdler&#x2F;config.txt).
--list-failed: Will list the urls of all the failed downloads
--purge-failed: Use to clear the failed download queue. 
Use when you have a download stuck (perhaps removed from the site or 
wrong url in RSS feed) and you no longer care about RSSDler attempting 
to grab it. Will be appended to the saved download list to prevent 
readdition to the failed queue.
Should be used alone or with -c&#x2F;--config. Exits after completion.
--list-saved: Will list everything that has been registered as downloaded.
--purge-saved: Clear the list of saved downloads, not stored anywhere.
--state&#x2F;-s: Will return the process ID if another instance is running with.
Otherwise exits with return code 1
Note for Windows: will return the pid found in daemonInfo,
regardless of whether it is currently running.</code></pre><br>
<h3>Dealing with Unicode Related Issues in Rssdler</h3><br>
rssdler is known to crash on encountering Unicode characters in file names. If the feeds you&#x27;ll be using do not normally contain those, there&#x27;s no further action required. If however you plan on using what.cd feeds, patching rssdler to ignore errors is a must.<br>
<br>
Open the <code>rssdler.py</code> file. Locate the line:<br>
<br>
<pre><code>if not isinstance(s, basestring): s= unicode(s) # __str__ for exceptions etc</code></pre><br>
Erase it, and paste the following instead:<br>
<br>
<pre><code>if not isinstance(s, basestring):
try:
&nbsp; &nbsp; s= unicode(s) # __str__ for exceptions etc
except:
&nbsp; &nbsp; s= unicode(s.__str__(), errors=&#x27;ignore&#x27;)
if isinstance(s, str): s = unicode(s, &#x27;utf-8&#x27;, &#x27;replace&#x27;)
if not isinstance(s, unicode): 
raise UnicodeEncodeError(u&#x27;could not encode %s to unicode&#x27; % s)</code></pre><br>
Be careful while editing the file. Indentation is important. Do not use tab for indentation, use the space key. The screen shot below shows what this section of the file must look like (with whitespace marked):<br>
<br>
<img src="http://i29.tinypic.com/1zntkyr.jpg"><br>
<br>
An already modified rssdler.py can be found <a href="http://rusak.pastebin.com/f624298d3">here</a>.<br>
<br>
<h3>Other Known Issues</h3><br>
<code>WAFFLES.FM</code>:<br>
<br>
Until further notice, Waffles.FM banned OVH IP ranges from accessing the website, while still allowing access to the tracker. You will thus be able to use your Feral box to download&#x2F;upload stuff from&#x2F;to Waffles.FM, but you will not be able to access Waffles.FM website using Feral VPN &#x2F; SSH tunnel or use Waffles.FM RSS feeds directly on your Feral box. See <a href="https://www.feralhosting.com/faq/view?question=39">this guide</a> for a possible workaround.<br>
<br>
