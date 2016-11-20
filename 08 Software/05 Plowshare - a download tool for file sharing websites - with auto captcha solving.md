<h1>Plowshare - a download tool for file sharing websites - with auto captcha solving</h1>

        
<br>
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
<h2>Plowshare</h2><br>
<a href="https://github.com/mcrapet/plowshare">Plowshare homepage</a><br>
<a href="https://github.com/mcrapet/plowshare/wiki/Modules">Plowshare Readme</a><br>
<br>
Plowshare is a UNIX&#x2F;Linux command line tool for downloading files from file sharing websites like rapidshare.com, hotfile.com, depositfiles.com, and so on, it currently has support for 49 sites.<br>
<br>
The real benefit for users is Plowshare&#x27;s ability to take a file of links and download them all, with automatic captcha solving, and you can start it running and then logout of your Feral slot leaving it to do all the hard work (maybe even leaving it running overnight to download lots).<br>
<br>
The automatic captcha solving is done by using one of several sites which allow you to either buy captchas or to earn them by solving other people&#x27;s captchas and so build up captcha credits for your own future use. In this guide I will explain how to setup Plowshare to use 9kw.eu which is the site that allows you to earn captchas by solving them as and when you want to earn credits. When Plowshare needs to solve a captcha it will send a request to 9kw.eu and as long as you have credits available the captcha will be solved. As well as 9kw.eu you can also use deathbycaptcha.com and antigate.com which both sell captcha solving cheaply, but only 9kw.eu has the facility to earn credits by solving other people&#x27;s captchas. Note: Cost, 9kw.eu sells 4000 captchas for EURO €5.00, deathbycaptcha.com sells 5000 captchas for USD $6.95, antigate.com is in the same ballpark.<br>
<br>
Plowshare is a command line tool and while not hard to install, setup, and run, it is not for Linux newbies. You really need to know how to edit files on your Feral slot, create and change directories, and such like. This is a step-by-step guide for installing and using Plowshare on your Feral slot and not a how-to-do the basics of Linux.<br>
<br>
<h2>Download and install Plowshare:</h2><br>
<pre><code>mkdir -p ~&#x2F;bin &amp;&amp; bash
git clone <a href="https://github.com/mcrapet/plowshare.git">https:&#x2F;&#x2F;github.com&#x2F;mcrapet&#x2F;plowshare.git</a> ~&#x2F;.plowshare-source &amp;&amp; cd ~&#x2F;.plowshare-source
make install PREFIX=$HOME &amp;&amp; cd &amp;&amp; rm -rf .plowshare-source</code></pre><br>
Now it should be successful installed. You can test by running this command.<br>
<br>
<pre><code>plowdown -h</code></pre><br>
You should see a page of usage and options. If instead you get &quot;command not found&quot;, it will be because the &#x27;bin&#x27; directory has not been added to your $PATH. Just log out of Feral and then log back in again and it should work. (Feral slots have a &#x27;.bashrc&#x27; file which automatically adds the &#x27;~&#x2F;bin&#x27; directory to your path if &#x27;bin&#x27; exists and &#x27;.bashrc&#x27; is run when you login.)<br>
<br>
At this point you can delete the temp install directory you created, i.e. &#x27;plowtemp&#x27;, as well as the source tarball (.tar.gz) file if you want, they won&#x27;t be needed again.<br>
<br>
<h2>Fix Potential IPv6 (Internet Protocol v6) Problem.</h2><br>
There is no support on Feral slots for IPv6 (Internet Protocol version 6) at the moment. Plowshare makes extensive use of a program called &#x27;curl&#x27; to access the web and you must create a &#x27;curl&#x27; init file to make sure &#x27;curl&#x27; always uses IPv4 IP addresses and not IPv6.<br>
 <br>
Create a file in your home directory called &#x27;.curlrc&#x27; and in it place just the short line below:<br>
<br>
<pre><code>--ipv4</code></pre><br>
You can achieve this by running the following command:<br>
<br>
<pre><code>echo &#x27;--ipv4&#x27; &gt;&gt; ~&#x2F;.curlrc</code></pre><br>
 <br>
<h2>Create an automated captcha Account.</h2><br>
You can use 9kw.eu, deathbycaptcha.com or antigate.com to buy captcha credits, but only 9kw.eu allows you to earn credits by solving other people&#x27;s captchas - this works by you going to the 9kw.eu &#x27;Captcha&#x27; page, it will give you a captcha to solve, when you do so it will give you some credits, then it will give you another captcha to solve and so on.<br>
<br>
Note: An alternative to automated captcha solving is manual captcha solving. Just use the &quot;--captchamethod=imgur&quot; option on the command line or &quot;captchamethod=imgur&quot; in your config file. Plowshare will provide you with an imgurlink hosting the captcha, and you will need to solve it yourself which means you will have to keep and eye on the window if downloading more than one file at a time.<br>
<br>
<h2>Create a Plowshare Config File.</h2><br>
<strong>Important note:</strong> You do not need to create a config file, everything can be done on the command line, but it is useful to use one.<br>
 <br>
Plowshare uses this file location for its config file: <code>~&#x2F;.config&#x2F;plowshare&#x2F;plowshare.conf</code><br>
 <br>
Go to your home folder and make the directories and file, e.g. like this:<br>
<br>
<pre><code>cd $HOME
mkdir .config
(Note: &#x27;.config&#x27; may already exist, it will do if you have Deluge installed on your slot.)
cd .config
mkdir plowshare
cd plowshare
touch plowshare.conf</code></pre><br>
Now you must edit the &#x27;plowshare.conf&#x27; file. Mine looks like this:<br>
<br>
<pre><code># Plowshare configuration file
#

[General]
# I have a rapidshare Premium account, so have entered my login details:
rapidshare&#x2F;a=UserName:UserPass

# Plowshare readme (linked at the top of this page) shows how to enter login details for other sites, e.g.
# mediafire&#x2F;a=&quot;UserName:Pass With Spaces Use Quotes&quot;
# freakshare&#x2F;b=UserName:UserPass
# Note: The &quot;&#x2F;a&quot; denotes a premium account, the &quot;&#x2F;b&quot; denotes a registered but free account.

[Plowdown]
# Timeout in seconds: 43200 = 12 hours <code> 60 mins </code> 60 secs
timeout=43200

# Num retries you want per file.
max-retries=20

# I created a dir to put the download the files in. If you leave this out the PWD will be used, that is whichever
# dir you start the program from. Make sure you use the FULL PATH and not the &#x27;~&#x2F;&#x27; home notation.
output-directory=&#x2F;media&#x2F;sdh1&#x2F;home&#x2F;username&#x2F;downloads&#x2F;

# Use online automated captcha solving.
captchamethod=online

# The key for 9kw.eu
9kweu=FITSEKDFVIXXXXXXXXX

# If using deathbycaptcha.com use this instead of &quot;9kweu&quot;:
# deathbycaptcha=UserName:UserPass

# If using antigate.com use your key:
# antigate=49b1b8740e4b51cf51838975de9e1c31

# Note: Only use one of: &quot;9kweu=&quot;, &quot;deathbycaptcha=&quot;, &quot;antigate=&quot; so if you set up
# multiple accounts then make sure only the one you want to use is in the config.</code></pre><br>
I have a rapidshare.com account, so my login details go in the <code>General</code> section. The other sites can have login details entered as well, see the notes in the example config file above and the readme linked below. If you don&#x27;t have any account just delete the <code>General</code> section.<br>
<br>
The <code>Plowdown</code> section can have all kinds of things set in them, I just have a few. If you are using 9kw.eu enter your key details in the way of my example, likewise antigate, if deathbycaptcha then enter your username and pass seperated by a &#x27;:&#x27; and if there are spaces in your user&#x2F;pass then add double quotes, e.g. deathbycaptcha=&quot;User Name:Pass Word&quot;.<br>
 <br>
Any option can be placed in the config file, please see the Plowshare Readme config file section, here:<br>
<a href="http://code.google.com/p/plowshare/wiki/Readme4&#x23;Configuration_file">http:&#x2F;&#x2F;code.google.com&#x2F;p&#x2F;plowshare&#x2F;wiki&#x2F;Readme4#Configuration_file</a><br>
<br>
<h2>Using Plowshare.</h2><br>
Plowshare can be used to download, upload, list, and delete files on the file sharing websites.<br>
<br>
See the Plowshare Readme usage examples section, here:<br>
<br>
<a href="http://code.google.com/p/plowshare/wiki/Readme4&#x23;Usage_examples">http:&#x2F;&#x2F;code.google.com&#x2F;p&#x2F;plowshare&#x2F;wiki&#x2F;Readme4#Usage_examples</a><br>
<br>
I would think you&#x27;ll mainly be downloading files using &#x27;plowdown&#x27;, here are a few examples of its basic usage, but you can get a lot more information in the readme (already linked above) or by entering &#x27;man plowdown&#x27; on the command line. If you want to use &#x27;plowup&#x27; for uploading files, &#x27;plowdel&#x27; for deleting them, or &#x27;plowlist&#x27; for listing the contents of a shared-folder link then read their man pages and the webpage readme.<br>
<br>
To download a single file it&#x27;s as easy as this:<br>
<br>
<pre><code>plowdown <a href="http://www.rapidshare.com/files/86545320/TestName.rar">http:&#x2F;&#x2F;www.rapidshare.com&#x2F;files&#x2F;86545320&#x2F;TestName.rar</a>
plowdown <a href="http://depositfiles.com/files/zqwghtyz">http:&#x2F;&#x2F;depositfiles.com&#x2F;files&#x2F;zqwghtyz</a></code></pre><br>
If a captcha needs to be solved, and you set it up correctly, then that will be done automatically for you.<br>
<br>
To download a file of links, just create a text file with each link on a single line, e.g.<br>
<br>
<pre><code># Links example file: links.txt
<a href="http://depositfiles.com/files/zqwghtyz">http:&#x2F;&#x2F;depositfiles.com&#x2F;files&#x2F;zqwghtyz</a>
<a href="http://depositfiles.com/files/qwwgmsjs">http:&#x2F;&#x2F;depositfiles.com&#x2F;files&#x2F;qwwgmsjs</a>
<a href="http://depositfiles.com/files/shashsnd">http:&#x2F;&#x2F;depositfiles.com&#x2F;files&#x2F;shashsnd</a>
<a href="http://depositfiles.com/files/whayetms">http:&#x2F;&#x2F;depositfiles.com&#x2F;files&#x2F;whayetms</a></code></pre><br>
Then run plowdown with the file name:<br>
<br>
<pre><code>plowdown links.txt</code></pre><br>
If you use the -m switch then each link will be &#x27;commented out&#x27; in the &#x27;links.txt&#x27; file as and when it has been successfully downloaded.<br>
<br>
<pre><code>plowdown -m links.txt</code></pre><br>
You can also use plowdown to check - but not download - links, so you can check that all parts of a multi-part archive exist before starting the download process. Again using a single link or a file of links.<br>
<br>
<pre><code>plowdown -c <a href="http://depositfiles.com/files/zqwghtyz">http:&#x2F;&#x2F;depositfiles.com&#x2F;files&#x2F;zqwghtyz</a>
plowdown -c links.txt</code></pre><br>
<strong>How to run plowdown even after you have logged off Feral:</strong><br>
<br>
A useful hint for Feral users is that if you use the &#x27;&amp;&#x27; control operator at the end of the command line, then the command will &#x27;return&#x27; immediately and continue to run as a background task. This means you can start plowdown and then logoff Feral while plowdown continues to run. If you stay logged in you will continue to get messages from plowdown in your terminal window (unless you used the -q, --quiet switch) but logging out of Feral will not kill the process.<br>
 <br>
Just enter the command, add a &#x27;&amp;&#x27; at the end of it, and afterwards logout of Feral as normal, e.g.<br>
<br>
<pre><code>plowdown -m links.txt &amp;</code></pre><br>
Note: A much better option than using the command followed by &#x27;&amp;&#x27; so that plowdown will run after you have logged out is to use the Linux &#x27;screen&#x27; command. You may have used screen with a torrent program on your Feral slot already. Just type &#x27;screen&#x27; to get a new screen, start plowdown, then hit &lt;CTRL&gt;A+D to &#x27;detach&#x27; the screen. You can then log out of your Feral slot, maybe leaving files to download overnight. Restore a screen by using &#x27;screen -ls&#x27; to list active screens, then &#x27;screen -r screen_id&#x27; to restore it. Once restored you can kill that screen using &lt;CTRL&gt;A+K to &#x27;kill&#x27; the screen if plowdown has finished or of course you can detach the screen again with &lt;CTRL&gt;A+D. Screen is very powerful and has many features, see the manual linked below.<br>
<br>
<a href="http://www.gnu.org/software/screen/manual/screen.html">Screen User&#x27;s Manual</a><br>
<br>
That is the end of this tutorial but there is lots more information on the Plowshare site.<br>
<br>
