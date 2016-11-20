<h1>aria2c</h1>

        
<br>
aria2 is a lightweight multi-protocol &amp; multi-source command-line download utility. It supports HTTP&#x2F;HTTPS, FTP, BitTorrent and Metalink. aria2 can be manipulated via built-in JSON-RPC and XML-RPC interfaces.<br>
<br>
<a href="http://aria2.sourceforge.net/manual/en/html/aria2c.html">aria2c command documentation</a><br>
<br>
<h2>Using the aria2c Windows Command line binary with the Web Gui</h2><br>
<strong>1:</strong> Getting the <a href="http://aria2.sourceforge.net/">aria2c</a> executable.<br>
<br>
<strong>Important note:</strong> This is required for use with the Web Gui. The Web Gui does not come with the binary.<br>
<br>
<a href="http://downloads.sourceforge.net/project/aria2/stable/aria2-1.18.10/aria2-1.18.10-win-32bit-build1.zip">aria2c 1.18.10 x86</a> or <a href="http://downloads.sourceforge.net/project/aria2/stable/aria2-1.18.10/aria2-1.18.10-win-64bit-build1.zip">aria2c 1.18.10 x64</a> - Windows command line executable. <br>
<br>
<strong>2:</strong> Getting <a href="https://github.com/ziahamza/webui-aria2/">Aria2c Web Gui</a> - A very simple Web application that you can download and run in any browser.<br>
<br>
<a href="https://github.com/ziahamza/webui-aria2/archive/master.zip">Aria2c Web Gui download</a><br>
<br>
<strong>3:</strong> Unpacking the files and set-up:<br>
<br>
<h2>aria2c.exe</h2><br>
<strong>Important note:</strong> This section is aimed at getting the aria2c process running as simply as possible for use with the Web Gui. In the Web Gui you can configure many of aria2c&#x27;s options and settings per session. Please see the custom set-up section for a more advanced set-up using a custom <code>.conf</code> file, if you want certain settings to persist like username or site specific settings.<br>
<br>
Extract the <code>aria2c.exe</code> the the root of your C drive.<br>
<br>
<pre><code>C:\aria2c.exe</code></pre><br>
<strong>Important note:</strong> The command below uses this location to start aria2c.<br>
<br>
<strong>Important note:</strong> A note on download paths: aria2c will download files to the location from which the <code>aria2c.exe</code> from executed by default. <br>
<br>
To deal with this you can:<br>
<br>
1: You can set a path in the Web Gui once <code>aria2c.exe</code>. This will stick for this session only (until aria2c.exe is restarted)<br>
<br>
2: Using the arguments <code>--dir=some&#x2F;path</code> or <code>-d some&#x2F;path</code> when starting <code>aria2c.exe</code>. When used like this:<br>
<br>
<pre><code>-d downloads</code></pre><br>
or <br>
<br>
<pre><code>--dir=downloads</code></pre><br>
aria2c will create a new folder relative (in the same place) to the <code>aria2c.exe</code> when you start a download and use this location to store downloads.<br>
<br>
<strong>Important note:</strong> I tried using dynamic Windows paths using <code>%UserProfile%</code> in the start up parameters. While this seems to work at first, on restart aria2c gets confused about this path refuses to work. You will need to use direct links to folders or paths relative to the <code>aria2c.exe</code> (paths relative to the <code>aria2c.exe</code>).<br>
<br>
Press and hold the <code>Windows Key</code> then press <code>R</code> to open the run prompt.<br>
<br>
If you copy and paste this command into the prompt it will load and run aria2c in the command prompt window.<br>
<br>
<pre><code>C:\aria2c.exe --enable-rpc=true --check-certificate=false -d downloads -x 16 -s 16 -j 10</code></pre><br>
For a full list of options and their defaults please refer to this page:<br>
<br>
<a href="http://aria2.sourceforge.net/manual/en/html/aria2c.html">aria2c command documentation</a><br>
<br>
<strong>Important note:</strong> If you close the command prompt window that opens you will terminate the <code>aria2c.exe</code> process. See the custom set-up below to avoid this.<br>
<br>
Now jump to the aria Web Gui section<br>
<br>
<h2>aria2c custom setup</h2><br>
<code>aria2c.exe</code> or the Web Gui do not remember your configuration settings if you restart <code>aria2c.exe</code> The <code>aria2c.bat</code> or <code>aria2.conf</code>&nbsp; files are easily edited to add or remove command line options that suit your needs. This means it will always start with the settings you want. Also to have the program run in the background (no command prompt window) making it set and forget you need to use this custom set-up:<br>
<br>
This set-up will allow you to easily download from password protected http&#x2F;s folders and ftp by using a custom <code>.conf</code>.<br>
<br>
<strong>What is this custom set-up then? </strong><br>
<br>
This is the aria2c v1.18.10 x64 or x86 exe, in a folder that includes a <code>aria2c.bat</code>, a <code>runme.vbs</code> file and a custom <code>aria2.conf</code> with some pre configured settings.<br>
<br>
The <code>aria2c.bat</code> file contains the command we use to run aria2c. In this case, executing it and loading our custom <code>aria2.conf</code>. You can tweak the <code>aria2c.bat</code> or the <code>aria2.conf</code> to decide start-up parameters<br>
<br>
The <code>aria2.conf</code> contains our unique settings in a way that is easily customisable.<br>
<br>
Apart from some Windows specific things like the <code>.bat</code> and <code>.vbs</code> file, the start-up command used and <code>.conf</code> settings should apply to any platform.<br>
<br>
This is the start-up command used in the custom set-up.<br>
<br>
<pre><code>aria2c.exe --conf-path=settings&#x2F;aria2.conf</code></pre><br>
You should be able to use the included <code>.conf</code> on Mac or Linux.<br>
<br>
<strong>Important note:</strong> Where a setting has not been included in the <code>aria2.conf</code> it is because the default setting is more than fine for almost all needs. For a full list of options and their defaults please refer to this page:<br>
<br>
<a href="http://aria2.sourceforge.net/manual/en/html/aria2c.html">aria2c command documentation</a><br>
<br>
The <code>runme.vbs</code> checks to see if aria is already running before executing the bat file to prevent duplicate running processes.<br>
<br>
<strong>1:</strong> Download the zip, extract the <code>aria2c</code> inside it to anywhere you like.<br>
<br>
<strong>2:</strong> Navigate to this extracted directory and double click on the <code>runme.vbs</code>.<br>
<br>
<strong>Important note:</strong> You can customise the <code>aria2c.exe</code> settings from with the Web Gui that will stick as long as the <code>aria2c.exe</code> does not restart. For permanent settings you will need to customise the <code>aria2c.bat</code>.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/aria2c/aria2ccustom.png"><br>
<br>
<a href="http://git.io/aNq7DA">Download the aria2c x64 custom set-up zip</a><br>
<br>
<a href="http://git.io/YBHVGA">Download the aria2c x86 custom set-up zip</a><br>
<br>
You can create multiple <code>.conf</code> files that have different settings as templates for various needs.<br>
<br>
This custom set-up has been tested and works with this FAQ including with _h5ai: <a href="https://www.feralhosting.com/faq/view?question=20">Putting your WWW folder to use</a><br>
<br>
You will need to edit the <code>aria2.conf</code> and add your credentials before you start the <code>aria2c.exe</code><br>
<br>
<pre><code># Credentials
# http&#x2F;s like your rutorrent login and pass
http-user=
http-passwd=
# You ftp details. Either from feral or from the proftpd FAQ
ftp-user=
ftp-passwd=</code></pre><br>
<h3>aria2c Web Gui</h3><br>
This can literally be run from anywhere you want.<br>
<br>
So extract the folder somewhere and then browse into it.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/aria2c/webgui.png"><br>
<br>
You should see this:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/aria2c/webguisuccess.png"><br>
<br>
If you see this, aria2c is not running.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/aria2c/webguifail.png"><br>
<br>
For each session you can configure settings via the Web Gui. <br>
<br>
<strong>Important note:</strong> These settings will last until you close or restart the <code>aria2c.exe</code> process.<br>
 <br>
<h3>uget a front end for aria2c Linux or Windows</h3><br>
<a href="http://ugetdm.com/">Uget download Manager</a> is a cross platform program download manager. It is also a useful front end for aria2c.<br>
<br>
<strong>Important note:</strong> This program may use an older version of aria2c x86 than the official stable release.<br>
<br>
1: Download <a href="http://sourceforge.net/projects/urlget/files/latest/download?source=files">uget</a> for Windows.<br>
<br>
2: Extract the contents of the archive to a folder.<br>
<br>
Inside this folder you will see this, navigate into the <code>bin</code> folder<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/aria2c/uget1.png"><br>
<br>
Find and run the <code>uget.exe</code><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/aria2c/uget2.png"><br>
<br>
This is what you will see:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/aria2c/uget3.png"><br>
<br>
Go to <code>Edit</code> and then click on <code>Settings...</code><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/aria2c/uget4.png"><br>
<br>
Click on the <code>Plug in</code> tab:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/aria2c/uget5.png"><br>
<br>
Activate the use of aria2c. Customise the commands if needed.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/aria2c/uget6.png"><br>
<br>
You are now ready to use aria2c with uget.<br>
<br>
