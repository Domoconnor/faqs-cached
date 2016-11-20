<h1>AeroFS - How to install</h1>

        
<br>
In SSH do the commands described in this FAQ. If you do not know how to SSH into your slot use this FAQ: <a href="https://www.feralhosting.com/faq/view?question=12">SSH basics - Putty</a><br>
<br>
Your FTP &#x2F; SFTP &#x2F; SSH login information can be found on the Slot Details page for the relevant slot.<br>
<br>
Use this link in your Account Manager to access the relevant slot:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/slot_detail_link.png"><br>
<br>
You login information for the relevant slot will be shown here:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/slot_detail_ssh.png"><br>
<br>
<h2>Aerofs introduction</h2><br>
Aerofs is essentially a peer to peer secure dropbox style app. You only share directly with your attached devices.<br>
<br>
&quot;AeroFS encrypts your data end-to-end, and only shares your files with those who you invite. Files are never stored in the public cloud.&quot;<br>
<br>
<h2>Install AeroFS:</h2><br>
Please go to <a href="https://aerofs.com/">https:&#x2F;&#x2F;aerofs.com&#x2F;</a> and create an account.<br>
<br>
<pre><code>wget -qO ~&#x2F;aerofs.tgz <a href="https://dsy5cjk52fz4a.cloudfront.net/aerofs-installer-0.8.91.tgz">https:&#x2F;&#x2F;dsy5cjk52fz4a.cloudfront.net&#x2F;aerofs-installer-0.8.91.tgz</a>
tar xf ~&#x2F;aerofs.tgz</code></pre><br>
<h2>Running Aerofs</h2><br>
At first run we need set up the app and it work better in a screen, so type this command:<br>
<br>
<pre><code>screen -S aerofs ~&#x2F;aerofs&#x2F;aerofs-cli</code></pre><br>
<h3>Aerofs Teamserver example (Optional - Just for demonstration):</h3><br>
 <strong>Important note:</strong> The teamserver installation is pretty much exactly the same. Centralised files storage vs peer to peer clients.<br>
<br>
<pre><code>wget -qO ~&#x2F;aerofsts.tgz <a href="https://dsy5cjk52fz4a.cloudfront.net/aerofsts-installer-0.8.91.tgz">https:&#x2F;&#x2F;dsy5cjk52fz4a.cloudfront.net&#x2F;aerofsts-installer-0.8.91.tgz</a>
tar xf ~&#x2F;aerofsts.tgz
screen -S aerofs ~&#x2F;aerofs&#x2F;aerofsts-cli</code></pre><br>
<h2>Configuring Aerofs</h2><br>
This will start the set-up process.<br>
<br>
- Enter the email you registered with when prompted.<br>
<br>
- Enter you password for this account when prompted.<br>
<br>
- Enter the path you want for you Aerofs folder when prompted. This path will <code>~&#x2F;Aerofs</code> by default if you just press enter.<br>
<br>
When the set-up is complete press this keyboard sequence to detach from the screen:<br>
<br>
Press and hold <code>CTRL</code> and <code>A</code> then press&nbsp; <code>D</code><br>
<br>
Once you have setup up Aerofs you can start it easily using this command:<br>
<br>
<pre><code>screen -dmS aerofs ~&#x2F;aerofs&#x2F;aerofs-cli &amp;</code></pre><br>
To use the process interactively use this command:<br>
<br>
<pre><code>~&#x2F;aerofs&#x2F;aerofs-sh</code></pre><br>
Here is the result:<br>
<br>
<pre><code>AeroFS&gt;</code></pre><br>
Type <code>help</code> to see the help page<br>
<br>
<pre><code>AeroFS&gt; help</code></pre><br>
<br>

