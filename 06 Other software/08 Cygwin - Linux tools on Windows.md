<h1>Cygwin - Linux tools on Windows</h1>

        
<br>
<h3>Installing cygwin on Windows</h3><br>
First you will need to download and run the Cygwin setup file: <a href="http://cygwin.com/setup-x86.exe">Cygwin setup-x86.exe</a><br>
<br>
There is a <em>x64</em> version but it does not have all the programs we need. Also it installs alongside, in a separate location, from the <em>x86</em> files if you want to install it.<br>
<br>
<h3>Step 1: Run the setup-x86.exe</h3><br>
Upon running the setup exe you will be presented with this screen. You will have to navigate through these screens as shown in the images.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Cygwin%20-%20Linux%20tools%20on%20Windows/1.png"><br>
<br>
Leave it as is and then click next:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Cygwin%20-%20Linux%20tools%20on%20Windows/2.png"><br>
<br>
It is recommended to leave the installation directory as the default and for all users. Then click next.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Cygwin%20-%20Linux%20tools%20on%20Windows/3.png"><br>
<br>
This is where Cygwin will download the temp files&#x2F;packages of the core files and the programs your select. Then click next:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Cygwin%20-%20Linux%20tools%20on%20Windows/4.png"><br>
<br>
Leave as <em>Direct Connection</em> unless you have special requirements for connecting to the internet. Then click next:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Cygwin%20-%20Linux%20tools%20on%20Windows/5.png"><br>
<br>
Here you can select a mirror for the files and files list. I always just use the first one. Then click next:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Cygwin%20-%20Linux%20tools%20on%20Windows/6.png"><br>
<br>
Cygwin will now download the file lists.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Cygwin%20-%20Linux%20tools%20on%20Windows/7.png"><br>
<br>
If this is the first time you have installed Cygwin you will see this Alert. It is not an error, simply a warning. Click OK to continue.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Cygwin%20-%20Linux%20tools%20on%20Windows/alert.png"><br>
<br>
<h3>Step 2: Select out packages</h3><br>
This is what you will see once you have completed Step 1. This screen can seem quite overwhelming at first, but it is quite simple once you know how to navigate it.<br>
<br>
<strong>Important note:</strong> By default Cygwin will only install the basic and critical files it needs to run. <br>
<br>
We want to install these programs so we will have to find and select them for installation:<br>
<br>
<pre><code>cygrunsrv
lftp
rsync
cron
openssh
openssl
nano</code></pre><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Cygwin%20-%20Linux%20tools%20on%20Windows/apps.1.png"><br>
<br>
This is the first program we want to install, called:<br>
<br>
<pre><code>cygrunsrv</code></pre><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Cygwin%20-%20Linux%20tools%20on%20Windows/apps.cygrunsrv.png"><br>
<br>
Now search for:<br>
<br>
<pre><code>lftp</code></pre><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Cygwin%20-%20Linux%20tools%20on%20Windows/apps.lftp.png"><br>
<br>
Now search for:<br>
<br>
<pre><code>rsync</code></pre><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Cygwin%20-%20Linux%20tools%20on%20Windows/apps.rsync.png"><br>
<br>
Now search for:<br>
<br>
<pre><code>cron</code></pre><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Cygwin%20-%20Linux%20tools%20on%20Windows/apps.cron.png"><br>
<br>
Now search for:<br>
<br>
<pre><code>openssh</code></pre><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Cygwin%20-%20Linux%20tools%20on%20Windows/apps.openssh.png"><br>
<br>
Now search for:<br>
<br>
<pre><code>openssl</code></pre><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Cygwin%20-%20Linux%20tools%20on%20Windows/apps.openssl.png"><br>
<br>
Now search for:<br>
<br>
<pre><code>nano</code></pre><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Cygwin%20-%20Linux%20tools%20on%20Windows/apps.nano.png"><br>
<br>
<strong>Important note:</strong> For now just install these tools. You can easily add new programs later be re running the Cygwin setup.<br>
<br>
Once you have selected all the programs above for installation click on <em>Next</em> to start the installation process.<br>
<br>
<h3>Step 3: Installing the programs</h3><br>
You will see this screen about installing the required dependencies for any programs you have selected.<br>
<br>
<strong>Important note:</strong> You need to make sure <em>Select required packages (RECOMMENDED)</em> is checked.<br>
<br>
Then click on <em>Next</em><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Cygwin%20-%20Linux%20tools%20on%20Windows/finish.1.png"><br>
<br>
It will now download an install the programs. This can take some time so be patient.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Cygwin%20-%20Linux%20tools%20on%20Windows/finish.2.png"><br>
<br>
Check both options here so it is easier to start the Cygwin terminal.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Cygwin%20-%20Linux%20tools%20on%20Windows/finish.3.png"><br>
<br>
You have now successfully installed Cygwin.<br>
<br>
<strong>Important note:</strong> Re run the <em>setup-x86.exe</em> at any time to add new programs or remove them<br>
<br>
<h3>Cygwin first run</h3><br>
On your Desktop look for the Cygwin icon:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Cygwin%20-%20Linux%20tools%20on%20Windows/shortcut.png"><br>
<br>
Double click the short cut to start the Cygwin terminal. You will something like this on your first time running the Cygwin terminal:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Cygwin%20-%20Linux%20tools%20on%20Windows/firstrun.png"><br>
<br>
From now on when you run the Cygwin terminal it will simply look like this:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Cygwin%20-%20Linux%20tools%20on%20Windows/secondrun.png"><br>
<br>
And that is it. You have now successfully run Cygwin for the first time and are ready to start using the programs you installed. You can use these installed programs just how they are described in the FAQs here, except for where things like Path names and other variables are relative to you and your PC.<br>
<br>
<h3>Notes:</h3><br>
I like to use nano in bash as the default editor (for things like crontab).<br>
<br>
You can do this per session:<br>
<br>
<pre><code>export &quot;EDITOR=nano&quot;</code></pre><br>
Or make it permanent by adding it to your <em>.bashrc</em> file.<br>
<br>
Your <em>.bashrc</em> is located here in a default installation, where <em>username</em> if your Windows username:<br>
<br>
<pre><code>C:&#x2F;cygwin&#x2F;home&#x2F;username&#x2F;.bashrc</code></pre><br>
<pre><code>echo &quot;export EDITOR=nano&quot; &gt;&gt; ~&#x2F;.bashrc</code></pre><br>
<pre><code>source ~&#x2F;.bashrc</code></pre><br>
<br>
