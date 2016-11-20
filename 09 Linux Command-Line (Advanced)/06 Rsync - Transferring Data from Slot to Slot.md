<h1>Rsync - Transferring Data from Slot to Slot</h1>

        
<h2>Rsync toolkit bash script</h2><br>
Do this command on your <strong>NEW</strong> slot:<br>
<br>
<pre><code>wget -qO ~&#x2F;rsynctk.sh <a href="http://git.io/ikae7Q">http:&#x2F;&#x2F;git.io&#x2F;ikae7Q</a> &amp;&amp; bash ~&#x2F;rsynctk.sh</code></pre><br>
This script basically does 2 things.<br>
<br>
<strong>1:</strong> Asks you for inputs such as username and server name and will then generate you a working command that you can do inside a screen window.<br>
<br>
<strong>2:</strong> You can continue and have the script create a screen and add the command. This stage requires your SSH passwords for your old slot. If you complete the steps correctly, it will create a screen and start the transfer based on your input.<br>
<br>
If anything, you can just do stage one to get a working command. Remember, you run this script on your <strong>NEW</strong> slot. It copies files from your old slot to the new. The process is started and runs on the new slot.<br>
<br>
<h2>Manual steps: rysnc Intro</h2><br>
Let us say that you have just purchased an upgraded slot and would like to move files over from the old slot over to your newer slot. This can be done through a ticket and usually is, but here I will explain how to do this partially or completely by yourself in SSH with very reliable results using a program called screen with another program called rsync.<br>
<br>
<strong>Step 1:</strong> First though, a couple of preparation steps to make life and the task a bit easier. There are several ways to do this part -- pick what is easiest for you. <br>
<br>
Don&#x27;t forget that you can open a ticket and ask Staff to do this for you if you are struggling:<br>
<br>
If you plan on cloning&#x2F;copying your entire HOME folder or a particular and existing folder like <code>~&#x2F;private</code> to <code>~&#x2F;private</code>, you do not need to move the files first. You can just skip to <strong>Step 2</strong>. <br>
<br>
<strong>Step 1:</strong> describes preparing a method for easily and selectively copying files from one slot to another. <br>
<br>
<strong>Step 2:</strong> further describes the use of rysnc to copy files.<br>
<br>
<h2>Step 1: Prepare our NEW slot</h2><br>
<strong>1</strong> <a href="https://www.feralhosting.com/faq/view?question=12">SSH</a> to your NEW slot.<br>
<br>
Here we will now create the folder where you wish to store the transferred files. Staff use a naming scheme like <code>data-from-old</code> of similar. Here we will use <code>rysnc</code>:<br>
<br>
<pre><code>mkdir -p ~&#x2F;rysnc</code></pre><br>
This means there is now a folder called <code>rysnc</code> within your <code>~&#x2F;</code> or slot root on the NEW server.<br>
<br>
Now the process below will describe how to copy all or parts of your old slot&#x27;s data to the newly created <code>rsync</code> folder on your new slot.<br>
<br>
<h2>Step 2: Using <code>rysnc</code></h2><br>
<strong>2.1</strong><br>
<br>
<strong>Important note:</strong> It is best to start transfers inside a screen window. This is a pretty simple thing to do.<br>
<br>
Use this command to create a screen for us to use:<br>
<br>
<pre><code>screen -S transfer</code></pre><br>
If it already exists, reconnect to it using this command:<br>
<br>
<pre><code>screen -r transfer</code></pre><br>
Once it has opened you will be placed inside the new screen window.<br>
<br>
<strong>2.2</strong> rsync, the command and structure<br>
<br>
<strong>Important note:</strong> Please see the end of the FAQ for a breakdown of the arguments used as well as some optional extras.<br>
<br>
This is the command we will use to copy files from our old slot to our new slot, while connected to our new slot via SSH.<br>
<br>
<pre><code>rsync -avhPS usename@server.feralhosting.com:&#x27;&quot;~&#x2F;location&#x2F;of&#x2F;files&quot;&#x27; &quot;~&#x2F;destination&#x2F;of&#x2F;files&#x2F;&quot;</code></pre><br>
For example, using the directories we created in <strong>Step 1</strong> we can do this:<br>
<br>
<pre><code>rsync -avhPS usename@server.feralhosting.com:&#x27;&quot;~&#x2F;private&#x2F;rtorrent&#x2F;data&quot;&#x27; &quot;~&#x2F;rsync&#x2F;&quot;</code></pre><br>
This will copy the folder and the contents of the <code>~&#x2F;private&#x2F;rtorrent&#x2F;data</code> directory from the <code>usename@server.feralhosting.com</code> used in the command into the <code>~&#x2F;rsync</code> directory of the slot you are currently SSH&#x27;d into.<br>
<br>
If you need to use a different port for the remote location, after -avhPS add -e &quot;ssh -p portnumber&quot;<br>
<br>
For Feral internal transfers you can also use this command which will be faster than the default method:]<br>
<br>
<strong>1:</strong> Make sure you are in the root folder by entering this command:<br>
<br>
<pre><code>cd</code></pre><br>
Then edit this command, where:<br>
<br>
<strong>1:</strong> <code>username</code> is your Feral username and <code>server</code> is the name of the Feral server your slot is hosted on:<br>
<strong>2:</strong> <code>location&#x2F;of&#x2F;files</code> is the relative path to the data you want transferred.<br>
<strong>3:</strong> <code>destination&#x2F;of&#x2F;files&#x2F;</code> is the relative path to the location you want the data moved on the new slot.<br>
<br>
<pre><code>rsync -avhPSe &quot;ssh -T -c arcfour -o Compression=no&quot; usename@server.feralhosting.com:&#x27;&quot;location&#x2F;of&#x2F;files&quot;&#x27; &quot;destination&#x2F;of&#x2F;files&#x2F;&quot;</code></pre><br>
<strong>2.3</strong> Understanding trailing slashes <code>&#x2F;</code> in paths.<br>
<br>
rysnc will be very specific about the use of a trailing slash in your paths. It has an important meaning to rsync and should be explained, so let us look at the example command above:<br>
<br>
Here, rsync is copying from the left to the right. There is no trailing slash on our <code>~&#x2F;private&#x2F;rtorrent&#x2F;data</code> path.<br>
<br>
To help with the example, our <code>~&#x2F;private&#x2F;rtorrent&#x2F;data</code> contains a single folder called <code>some.film.2013.720p</code><br>
<br>
<pre><code>~&#x2F;private&#x2F;rtorrent&#x2F;data ~&#x2F;rsync&#x2F;</code></pre><br>
This means that rsync will copy the whole folder <code>data</code> into the <code>~&#x2F;rsync&#x2F;</code> directory on our new slot like this:<br>
<br>
<pre><code>~&#x2F;rsync&#x2F;data&#x2F;some.film.2013.720p</code></pre><br>
If we had used a trailing slash, we would be telling rsync that we want to copy the contents of the folder and not the actual folder itself.<br>
<br>
<pre><code>~&#x2F;private&#x2F;rtorrent&#x2F;data&#x2F; ~&#x2F;rsync&#x2F;</code></pre><br>
This command has a trailing slash, so the outcome will be different. The <strong>contents</strong> of the <code>~&#x2F;private&#x2F;rtorrent&#x2F;data</code> will be copied to the <code>~&#x2F;rsync&#x2F;</code> directory on our new slot.<br>
<br>
All files from within the data directory on our old slot will be copied to the <code>~&#x2F;rsync&#x2F;</code> directory.<br>
<br>
<pre><code>~&#x2F;rsync&#x2F;some.film.2013.720p</code></pre><br>
Be careful with the use of a trailing slash. You could use the general rule of telling rsync to look <code>inside this directory</code> when deciding whether to apply a trailing slash.<br>
<br>
Here is a useful explanation of the use of a trailing slash: <a href="http://devblog.virtage.com/2013/01/to-trailing-slash-or-not-to-trailing-slash-to-rsync-path/">External link</a><br>
<br>
<h2>Step 3: Applying our command:</h2><br>
Once we have the correct command, with the relevant paths to your directories, let&#x27;s do a quick check:<br>
<br>
<strong>3.1:</strong> We have SSH&#x27;d to the server we want to copy the files to. This means your <strong>NEW</strong> slot.<br>
<br>
<strong>3.2:</strong> We have opened a screen window in SSH and given it a name we can easily recognize ( that is what the -S does), in this example the screen name is <strong>transfer</strong>.<br>
<br>
<strong>3.3:</strong> We have edited the command to be relevant to our details. So <code>username@server.feralhosting.com</code> has been edited to contain your relevant info such as the host where the files are we want to copy, for example: <code>huzzah378@lemur.feralhosting.com</code><br>
<br>
<strong>3.4:</strong> We have used existing directories that we either created in <strong>Step 1</strong> or that already exist.<br>
<br>
<strong>3.5:</strong> Our command now looks something like this:<br>
<br>
<pre><code>rsync -avhPS huzzah378@lemur.feralhosting.com:&#x27;&quot;~&#x2F;private&#x2F;rtorrent&#x2F;data&quot;&#x27; &quot;~&#x2F;rsync&#x2F;&quot;</code></pre><br>
Then in your screen window copy or type this command (in putty or Linux a right click will paste the contents of your clip board including a password, even if you don&#x27;t see it.)<br>
<br>
<strong>Important note:</strong> It does not matter if you have set up public or private key Auth for your SSH. The password that SSH will ask for is the one that is shown in your Slot Details page in your <a href="https://www.feralhosting.com/manager/">Account Manager</a>. This is the one that you received upon the creation of your slot.<br>
<br>
If all goes to plan, the transfers should start and you will see stuff being moved in the screen window. You can either wait around and monitor its progress or detach from the screen to leave it running in the background. This will allow you to close the SSH connection (terminal) without interrupting the transfer. To do this in your screen:<br>
<br>
Press and hold <code>CTRL</code> and <code>a</code> then press <code>d</code> to detach from the screen. This leaves it running in the background.<br>
<br>
You should see a &quot;you have been detached&quot; or similar prompt from within the terminal.<br>
<br>
That is it. <br>
<br>
You can attach to the screen at any time to check on things by typing this in a terminal:<br>
<br>
<pre><code>screen -r transfer</code></pre><br>
Please see this Guide for <a href="https://www.feralhosting.com/faq/view?question=122">Completing a Data transfer</a> for getting your torrent programs back up and running.<br>
<br>
<h2>Notes:</h2><br>
<a href="http://linux.die.net/man/1/rsync">http:&#x2F;&#x2F;linux.die.net&#x2F;man&#x2F;1&#x2F;rsync</a><br>
<br>
<a href="http://ss64.com/bash/rsync.html">http:&#x2F;&#x2F;ss64.com&#x2F;bash&#x2F;rsync.html</a><br>
<br>
Here is the command broken down.<br>
<br>
<pre><code>-avhPS</code></pre><br>
<code>-a</code>, <code>--archive</code>&nbsp;  archive mode; equals <code>-rlptgoD</code> (no <code>-H</code>,<code>-A</code>,<code>-X</code>)<br>
<br>
<code>-r</code>, <code>--recursive</code> recurse into directories<br>
<code>-l</code>, <code>--links</code>&nbsp; &nbsp;  copy symlinks as symlinks<br>
<code>-p</code>, <code>--perms</code>&nbsp; &nbsp;  preserve permissions<br>
<code>-t</code>, <code>--times</code>&nbsp; &nbsp;  preserve modification times<br>
<code>-g</code>, <code>--group</code>&nbsp; &nbsp; preserve group<br>
<code>-o</code>, <code>--owner</code>&nbsp; &nbsp;  preserve owner (super-user only)<br>
<code>-D</code>, same as <code>--devices --specials</code><br>
<br>
<code>-v</code>, <code>--verbose</code>&nbsp;  increase verbosity<br>
<code>-h</code>, <code>--human-readableoutput</code> numbers in a human-readable format<br>
<code>-P</code>, same as <code>--partial --progress</code><br>
<code>-S</code>, <code>--sparse</code>&nbsp;  handle sparse files efficiently<br>
<br>
<strong>SSH specific commands:</strong><br>
<br>
<a href="http://linux.die.net/man/1/ssh">SSH man pages</a><br>
<br>
<code>-T</code>&nbsp; Disable pseudo-tty allocation.<br>
<code>-c arcfour </code> Use the <code>-c</code> flag to set a cipher from a list of supported ciphers. Arcfour improves speed.<br>
<code>-o Compression=no</code> Use the <code>-o</code> flag to provide an option. Here <code>Compression=no</code> is the option set to <code>no</code><br>
<br>
<strong>Optional arguments</strong><br>
<br>
<code>-n</code>, <code>--dry-run</code>&nbsp;  perform a trial run with no changes made<br>
<code>-c</code>, <code>--checksum</code>&nbsp; skip based on checksum, not mod-time &amp; size<br>
<code>-z</code>, <code>--compress</code>&nbsp; compress file data during the transfer<br>
<br>
<pre><code>-anczvhPS</code></pre><br>
<br>
