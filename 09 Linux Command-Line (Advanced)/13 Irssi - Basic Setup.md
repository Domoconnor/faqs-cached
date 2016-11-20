<h1>Irssi - Basic Setup</h1>

        
<br>
Here is the basic set-up to get connected to the Feral IRC channel using Irssi from your Feral slot. It will get you connected using SSL to the Feral IRC channel using irssi.<br>
<br>
Doe these commands in <a href="https://www.feralhosting.com/faq/view?question=12">SSH</a>:<br>
<br>
<strong>1:</strong> Create a required folder and get a custom theme<br>
<br>
<pre><code>mkdir -p ~&#x2F;.irssi&#x2F;scripts&#x2F;autorun
wget -qO ~&#x2F;.irssi&#x2F;xchat.theme <a href="http://irssi.org/themefiles/xchat.theme">http:&#x2F;&#x2F;irssi.org&#x2F;themefiles&#x2F;xchat.theme</a></code></pre><br>
<strong>2:</strong> Get a nick colour script:<br>
<br>
<pre><code>wget -qO ~&#x2F;.irssi&#x2F;scripts&#x2F;autorun&#x2F;xchatnickcolor.pl <a href="http://dave.waxman.org/irssi/xchatnickcolor.pl">http:&#x2F;&#x2F;dave.waxman.org&#x2F;irssi&#x2F;xchatnickcolor.pl</a></code></pre><br>
<strong>3:</strong> Create a screen and open irssi in it using this command:<br>
<br>
<pre><code>screen -S irssi irssi</code></pre><br>
Once it has loaded copy or type these commands to configure your username. Where <code>username</code> is your Feral username (it can be something else):<br>
<br>
<pre><code>&#x2F;set NICK username
&#x2F;set user_name username
&#x2F;set real_name username
&#x2F;HILIGHT username</code></pre><br>
<strong>4:</strong> Optionally, make some more configuration changes:<br>
<br>
<pre><code>&#x2F;set autolog ON
&#x2F;set recode_autodetect_utf8 ON
&#x2F;set recode_fallback utf-8
&#x2F;set recode_out_default_charset utf-8
&#x2F;set term_charset utf-8
&#x2F;set theme xchat</code></pre><br>
<strong>5:</strong> Configure your server and channel settings:<br>
<br>
<strong>Important note:</strong> Remove <code>-auto</code> to stop it automatically connecting on start-up:<br>
<br>
<pre><code>&#x2F;network ADD What-Network
&#x2F;server ADD -ssl -auto -network What-Network irc.what-network.net 6697
&#x2F;channel ADD -auto #feral What-Network</code></pre><br>
<strong>Important Note</strong> If you have already registered your Nick on IRC you can do this now instead of in step 7:<br>
<br>
<pre><code>&#x2F;network ADD -autosendcmd &quot;&#x2F;msg nickserv IDENTIFY YourPassGoesHere;wait 2000&quot; What-Network
&#x2F;server ADD -ssl -auto -network What-Network irc.what-network.net 6697
&#x2F;channel ADD -auto #feral What-Network</code></pre><br>
You can add more commands if required. They are separated by a <code>;</code> like this:<br>
<br>
For example, this version works for me to ghost my username on connect to make sure I always connect as the same user.<br>
<br>
<pre><code>&#x2F;network ADD -autosendcmd &quot;&#x2F;msg NickServ GHOST username YourPassGoesHere;wait 2000;&#x2F;nick username;wait 2000;&#x2F;msg NickServ IDENTIFY YourPassGoesHere;wait 2000&quot; What-Network</code></pre><br>
<strong>6:</strong> Save your configuration changes<br>
<br>
<pre><code>&#x2F;save</code></pre><br>
<strong>7:</strong> Now while you are still inside this screen you can use this command to connect<br>
<br>
<pre><code>&#x2F;connect What-Network</code></pre><br>
If you Nick is not already registered you can do so now like this:<br>
<br>
<pre><code>&#x2F;msg NickServ REGISTER YourPassGoesHere YouEmail@GoesHere</code></pre><br>
Where <code>YourPassGoesHere</code> is the password you wish to use and <code>YouEmail@GoesHere</code> is an email address you use to register with.<br>
<br>
Then update your configuration file to automatically do this when you connect next time using this command:<br>
<br>
<pre><code>&#x2F;network ADD -autosendcmd &quot;&#x2F;msg nickserv IDENTIFY YourPassGoesHere;wait 2000&quot; What-Network</code></pre><br>
Then save the updated configuration:<br>
<br>
<pre><code>&#x2F;save</code></pre><br>
<strong>8:</strong> Changing windows<br>
<br>
You can change windows using these commands:<br>
<br>
<pre><code>&#x2F;window 1
&#x2F;window 2
&#x2F;window 3
&#x2F;window 4</code></pre><br>
Or use the <code>ESC</code> key and a number, for example: Press and hold <code>ESC</code> then press <code>3</code>. If you are already on this window it will just print the number.<br>
<br>
Detach from the screen using this keyboard sequence:<br>
<br>
The press and hold <code>CTRL</code> and <code>a</code> then press <code>d</code> to detach from the screen. This leaves it running in the background.<br>
<br>
Use this command to re attach to the screen:<br>
<br>
<pre><code>screen -r irssi</code></pre><br>
And that is basically it. You are automatically connecting to the What-Network, Feral channel with a username<br>
<br>
