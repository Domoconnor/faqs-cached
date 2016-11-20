<h1>WeeChat - an IRC Client - Basic Setup</h1>

        
<br>
This FAQ is for downloading and installing <a href="http://www.weechat.org/">WeeChat</a> on your slot.<br>
<br>
WeeChat is a fast, light and extensible chat client. It runs on many platforms like Linux, Unix, BSD, GNU Hurd, Mac OS X and Windows (cygwin). <br>
<br>
Please run this command in SSH first:<br>
<br>
<pre><code>mkdir -p ~&#x2F;bin &amp;&amp; bash</code></pre><br>
<h2>1: Build WeeChat and install it</h2><br>
Please use this script.<br>
<br>
<strong>Important note:</strong> If you get errors about missing dependencies please see the dependencies section at the end of this FAQ.<br>
<br>
<pre><code>wget -qO ~&#x2F;install.weechat <a href="http://git.io/vffAV">http:&#x2F;&#x2F;git.io&#x2F;vffAV</a> &amp;&amp; bash ~&#x2F;install.weechat</code></pre><br>
<h2>2: Start WeeChat</h2><br>
We have added the location to the <code>PATH</code> in step 1, so we can use this command:<br>
<br>
<pre><code>screen -dmS weechat weechat</code></pre><br>
Now attach to the screen:<br>
<br>
<pre><code>screen -r weechat</code></pre><br>
The full path to execute WeeChat is:<br>
<br>
<pre><code>~&#x2F;bin&#x2F;weechat</code></pre><br>
<h2>3: Configure WeeChat</h2><br>
These are some required settings. You enter them in WeeChat after you have started it.<br>
<br>
<pre><code>&#x2F;server add What-Network irc.what-network.net&#x2F;6697 -ssl</code></pre><br>
Replace&nbsp; <code>&quot;username,username_1,username_2&quot;</code> and the two&nbsp; instances of <code>&quot;username&quot;</code> with a username of your&nbsp; choice.<br>
<br>
<pre><code>&#x2F;set irc.server.What-Network.nicks &quot;username,username_1,username_2&quot;
&#x2F;set irc.server.What-Network.username &quot;username&quot;
&#x2F;set irc.server.What-Network.realname &quot;username&quot;</code></pre><br>
Some final settings:<br>
<br>
<pre><code>&#x2F;set irc.server.What-Network.ssl on
&#x2F;set irc.server.What-Network.ssl_verify off
&#x2F;set irc.server.What-Network.ssl_dhkey_size 1024
&#x2F;save</code></pre><br>
Add other networks as desired.<br>
<br>
<h2>4: Connecting to predefined IRC networks</h2><br>
Use this command to connect to the Feral Hosting IRC channel,&nbsp; <code>#feral</code> on the <code>What-Network</code>&nbsp; IRC network that we defined in the previous step.<br>
<br>
<pre><code>&#x2F;connect What-Network</code></pre><br>
<h2>5: Join a channel</h2><br>
<pre><code>&#x2F;j #feral</code></pre><br>
To detach from the screen, press and hold <code>CRTL</code> and <code>a</code> then press <code>d</code>.<br>
<br>
<h2>Further reading</h2><br>
Here you can get information on further configuration, such as auto join and more.<br>
<br>
<a href="http://www.weechat.org/files/doc/weechat_faq.en.html">WeeChat FAQ</a><br>
<br>
<a href="http://www.weechat.org/files/doc/stable/weechat_quickstart.en.html">WeeChat Quick Start Guide</a><br>
<br>
<a href="http://www.weechat.org/files/doc/stable/weechat_user.en.html">WeeChat Quick Start Guide</a><br>
<br>
<br>
<h2>Dependencies:</h2><br>
<a href="http://www.weechat.org/files/doc/stable/weechat_user.en.html&#x23;dependencies">http:&#x2F;&#x2F;www.weechat.org&#x2F;files&#x2F;doc&#x2F;stable&#x2F;weechat_user.en.html#dependencies</a><br>
<br>
You may need to ask for certain dependencies to be installed. If you experience this through the scripts failing to configure&nbsp; weechat and exiting then please ask for that dependency using this format.<br>
<br>
<pre><code>Please can you install some dependencies for Weechat

<a href="http://www.weechat.org/files/doc/stable/weechat_user.en.html&#x23;dependencies">http:&#x2F;&#x2F;www.weechat.org&#x2F;files&#x2F;doc&#x2F;stable&#x2F;weechat_user.en.html#dependencies</a>

apt-get install libgnutls28-dev libncursesw5-dev libgcrypt20-dev

Thank you.</code></pre><br>
<br>
