<h1>Remote Torrent Adder - Adding torrents to your slot from Chrome</h1>

        
<br>
<strong>1:</strong> Start by installing the extension from here:<br>
<br>
<a href="https://chrome.google.com/webstore/detail/oabphaconndgibllomdcjbfdghcmenci">Remote torrent adder</a><br>
<br>
<strong>2:</strong> Open the settings for the extension.<br>
<br>
<strong>3:</strong> Fill in the data in the form under the WebUI tab accordingly:<br>
<br>
<h2>Rutorrent</h2><br>
<strong>Client:</strong> ruTorrent WebUI from the drop down menu<br>
<br>
<strong>Host:</strong> <code>server.feralhosting.com</code> For example: <code>aphrodite.feralhosting.com</code><br>
<br>
<strong>Port:</strong> leave blank<br>
<br>
<strong>SSL</strong> Checked if you are using SSL<br>
<br>
<strong>Username:</strong> Your <code>Feral Username</code><br>
<br>
<strong>Password:</strong> Your <code>rutorrent Web Gui Password</code> (as shown on your Slot Details page for rutorrent)<br>
<br>
<strong>Important note:</strong> on your username and password: If you have changed your default rutorrent Web Gui config using the <a href="https://www.feralhosting.com/faq/view?question=22">Password Protect Your WWW Page(s)</a> guide you will need to use the <strong>Username</strong> and <strong>Password</strong> you created there.<br>
<br>
<strong>Relative Path SSL:</strong> <code>&#x2F;username&#x2F;rutorrent&#x2F;</code><br>
<br>
<strong>Label:</strong> [Nothing required]<br>
<br>
<strong>Directory:</strong> This is the directory where your torrent <strong>data</strong> will be stored, you will need the full path to this folder.<br>
To get this you have to SSH into your box, then navigate to your:<br>
<br>
Paste the following command into the terminal: <br>
<br>
<pre><code>ls -d $HOME&#x2F;private&#x2F;rtorrent&#x2F;data</code></pre><br>
The output should look something like this:<br>
<br>
<pre><code>&#x2F;media&#x2F;DiskID&#x2F;home&#x2F;username&#x2F;private&#x2F;rtorrent&#x2F;data&#x2F;</code></pre><br>
If you press a torrent link now it should load the .torrent directly into rtorrent<br>
on your slot.<br>
<br>
You will get an error like this:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Remote%20Torrent%20Adder%20-%20Adding%20torrents%20to%20your%20slot%20from%20Chrome/error.png"><br>
<br>
But it stills works.<br>
<br>
<strong>Important note:</strong><br>
<br>
If you update to nginx run this command:<br>
<br>
<pre><code>mkdir -p ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;rutorrent&#x2F;share&#x2F;torrents</code></pre><br>
<h2>Still having issues?</h2><br>
If you are having issues you can try these server settings instead:<br>
<br>
<strong>Important note:</strong> If you force redirection to https this URL format <strong>will not work</strong> unless you accept the cert in Chrome first every session. Follow these steps.<br>
<br>
1: You will need to visit the <code><a href="https://username.server.feralhosting.com">https:&#x2F;&#x2F;username.server.feralhosting.com</a></code> URL in a Chrome and accept the cert for this session.<br>
<br>
2: You will need to check <code>SSL</code> in the remote torrent adder options since https is being forced.<br>
<br>
These settings will work if https redirection is not forced, or you have visited the https URL for this session<br>
<br>
<strong>Host:</strong> <code>username.server.feralhosting.com</code> For example: <code>peterpan.aphrodite.feralhosting.com</code><br>
<br>
<strong>Port:</strong> leave blank<br>
<br>
<strong>Relative Path:</strong> <code>&#x2F;rutorrent&#x2F;</code><br>
<br>
<strong>SSL:</strong> Checked if https is being forced, otherwise leave unchecked.<br>
<br>
<h2>Client: Deluge</h2><br>
<strong>Host:</strong> server.feralhosting.com<br>
<br>
<strong>Port:</strong> leave blank<br>
<br>
<strong>Username:</strong> Your Feral username<br>
<br>
<strong>Password:</strong> You Deluge Web Gui password as listed on your Slot Details page.<br>
<br>
<strong>Relative path:</strong><br>
<br>
<pre><code>&#x2F;username&#x2F;deluge</code></pre><br>
<h2>Notes</h2><br>
You can also let the option of downloading on your torrent only be available by right-clicking<br>
the torrent link by deselecting the &quot;clicks on links&quot; in the &quot;link catching&quot; tab.<br>
(I&#x27;d recommend doing this so you don&#x27;t download all kinds of rubbish onto your slot)<br>
<br>
You will also override downloading this on your box by holding down Alt+Ctrl+Shift<br>
while clicking the link.<br>
<br>
