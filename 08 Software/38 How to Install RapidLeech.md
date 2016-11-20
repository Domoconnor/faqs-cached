<h1>How to Install RapidLeech</h1>

        
<br>
RapidLeech allows you to download files from file-hosting services such as Rapidshare.com etc. directly on to your Feral slot. You can then FTP them down to your home computer without any timers.<br>
<br>
Installation is exceptionally easy — run these two command in <a href="https://www.feralhosting.com/faq/view?question=12">SSH</a>:<br>
<br>
The URL is using Rapidleech <code>rl23_v43_SVN430.zip</code> from here <a href="https://drive.google.com/folderview?id=0B2TOwN5xkUeIQ3RxT3c1allQZkE&#x23;list">Rapid Share Source Code</a><br>
<br>
<pre><code>wget -qO ~&#x2F;rapid.zip <a href="http://git.io/3nr6fw">http:&#x2F;&#x2F;git.io&#x2F;3nr6fw</a>
unzip -qn ~&#x2F;rapid.zip -d ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;</code></pre><br>
Then visit your Feral URL in a web browser, for example:<br>
<br>
<pre><code><a href="http://username.server.feralhosting.com/rapidleech/">http:&#x2F;&#x2F;username.server.feralhosting.com&#x2F;rapidleech&#x2F;</a></code></pre><br>
<h3>Creating your config.php</h3><br>
Now, you can set whatever options you need or want then scroll to the bottom and click <code>Save Configuration</code> to create your first <code>config.php</code>.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Software/RapidLeech%20-%20How%20to%20Install/config.png"><br>
<br>
Now you can password protect your installation.<br>
<br>
You newly created config.php file is located at (relative path to the WWW root):<br>
<br>
<pre><code>&#x2F;rapidleech&#x2F;configs&#x2F;config.php</code></pre><br>
Rapidleech has no password authentication turned on by default, so it is necessary to follow <a href="http://wiki.rapidleech.com/FAQ&#x23;How_to_setup_password_on_rapidleech.3F">this Rapidleech Wiki article</a> to enable it. This is a required step.<br>
<br>
<strong>New Password Protection Method:</strong><br>
<br>
<strong>1:</strong> Make sure you have created and saved your <code>config.php</code> and shown in the previous step.<br>
<br>
<strong>2:</strong> Edit you config.php using nano in SSH using this command:<br>
<br>
<pre><code>nano -w ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;rapidleech&#x2F;configs&#x2F;config.php</code></pre><br>
Find the line:<br>
<br>
<pre><code>&#x27;login&#x27; =&gt; false,</code></pre><br>
then replace it with:<br>
<br>
<pre><code>&#x27;login&#x27; =&gt; true,</code></pre><br>
<strong>3:</strong> In the next line, you will see :<br>
<br>
<pre><code>&#x27;users&#x27; =&gt; 
&nbsp; array (
&nbsp; &nbsp; &#x27;test&#x27; =&gt; &#x27;test&#x27;,
&nbsp; ),</code></pre><br>
<strong>4:</strong> change: <code>test</code> to your user name and then the second <code>test</code> to your password<br>
<br>
<pre><code>&#x27;feral&#x27; =&gt; &#x27;password&#x27;,</code></pre><br>
Where feral is your username and password is your password.<br>
<br>
<strong>5:</strong> Now, it should look like this :<br>
<br>
<pre><code>&#x27;users&#x27; =&gt; 
&nbsp; array (
&nbsp; &nbsp; &#x27;feral&#x27; =&gt; &#x27;password&#x27;,
&nbsp; ),</code></pre><br>
Where <code>feral</code> is your username and <code>password</code> is your password.<br>
<br>
<strong>6:</strong> Save this file and your password protection will be active.<br>
<br>
Please read through the <a href="http://wiki.rapidleech.com/FAQ">Rapidleech Wiki</a> for more answers about how to use Rapidleech.<br>
<br>
