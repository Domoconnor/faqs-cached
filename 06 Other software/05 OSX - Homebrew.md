<h1>OSX - Homebrew</h1>

        
<br>
<h2>Installing <a href="http://brew.sh/">homebrew</a> on OS X Mavericks</h2><br>
This is quite a simple thing to do and once you have done it you will be able to install some useful apps for use with your slot.<br>
<br>
The first thing you need to do is open your terminal:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/macterminal1.png"><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/macterminal2.png"><br>
<br>
If you haven&#x27;t already created a dock icon for &quot;Terminal&quot;, open your Macintosh HD and go to the Applications folder, then Utilities from within that. Terminal is in the Utilities folder. Just drag it on to the Dock, and it&#x27;ll make a permanent Dock icon.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/terminalicon.png"><br>
<br>
<h2>Installing homebrew</h2><br>
In your terminal you need yo paste this command and then press enter:<br>
<br>
<pre><code>ruby -e &quot;$(curl -fsSL <a href="https://raw.githubusercontent.com/Homebrew/install/master/install">https:&#x2F;&#x2F;raw.githubusercontent.com&#x2F;Homebrew&#x2F;install&#x2F;master&#x2F;install</a>)&quot;</code></pre><br>
This will begin the homebrew installation procedure:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/OSX%20-%20Homebrew/homebrew1.png"><br>
<br>
You will need to follow the prompts from the script. Here you will need to press <code>enter</code> to continue.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/OSX%20-%20Homebrew/homebrew2.png"><br>
<br>
Enter your user&#x27;s password to allow the software to be installed. It should be your login password for this device.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/OSX%20-%20Homebrew/homebrew3.png"><br>
<br>
You may see this notice if you have not done this or something similar before. You will need to accept the installation. Click &quot;Install&quot; to continue:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/OSX%20-%20Homebrew/homebrew4.png"><br>
<br>
After you click &quot;Install&quot; you will see the software will be downloaded and installed:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/OSX%20-%20Homebrew/homebrew5.png"><br>
<br>
Click &quot;Done&quot; when it has finished to continue with the homebrew installation:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/OSX%20-%20Homebrew/homebrew6.png"><br>
<br>
Now you should be able to continue with the homebrew installation script to actually install homebrew itself.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/OSX%20-%20Homebrew/homebrew7.png"><br>
<br>
You will the terminal showing info similar to this while the installation is in progress. Just wait for it to finish.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/OSX%20-%20Homebrew/homebrew8.png"><br>
<br>
Once it has finish you will see something similar to this in your terminal.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/OSX%20-%20Homebrew/homebrew9.png"><br>
<br>
The closing section of the installer told us that we should run this command<br>
<br>
<pre><code>brew doctor</code></pre><br>
Do this now:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/OSX%20-%20Homebrew/homebrew10.png"><br>
<br>
You have now successfully installed homebrew and are now ready to install some apps.<br>
<br>
<h2>Installing homebrew apps.</h2><br>
The first thing to do is update the formulae:<br>
<br>
<pre><code>brew update</code></pre><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/OSX%20-%20Homebrew/homebrewupdate1.png"><br>
<br>
Once everything is updated it will look like this:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/OSX%20-%20Homebrew/homebrewupdate2.png"><br>
<br>
<a href="https://github.com/mxcl/homebrew/tree/master/Library/Formula">A list of available programs</a><br>
<br>
The basic idea of it is that you will run this command in your terminal window<br>
<br>
<pre><code>brew install someapp</code></pre><br>
<strong>lftp:</strong><br>
<br>
<pre><code>brew install lftp</code></pre><br>
Use the above command in your terminal window to install <code>lftp</code>:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/OSX%20-%20Homebrew/homebrewlftp1.png"><br>
<br>
The process will begin and it can take some times. Be patient and wait for it to finish:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/OSX%20-%20Homebrew/homebrewlftp2.png"><br>
<br>
Once it has finished you will have the prompt returned and be able to use <code>lftp</code>:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/OSX%20-%20Homebrew/homebrewlftp3.png"><br>
<br>
Here is an example of using <code>lftp</code> to show the version installed:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/OSX%20-%20Homebrew/homebrewlftp4.png"><br>
<br>
<strong>aria2:</strong><br>
<br>
<pre><code>brew install aria2</code></pre><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/OSX%20-%20Homebrew/homebrewaria21.png"><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/OSX%20-%20Homebrew/homebrewaria22.png"><br>
<br>
Once it has successfully installed you can called it using the command:<br>
<br>
<pre><code>aria2c</code></pre><br>
For example:<br>
<br>
<pre><code>aria2c --version</code></pre><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/OSX%20-%20Homebrew/homebrewaria23.png"><br>
<br>
Check out this FAQ for using <code>aria2c</code> - <a href="https://www.feralhosting.com/faq/view?question=236">aria2c</a><br>
<br>
