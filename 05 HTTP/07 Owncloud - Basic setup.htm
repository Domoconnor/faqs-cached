<h1>Owncloud - Basic setup</h1>

        
<br>
<strong>Important note:</strong> For using Owncloud With nginx please complete the nginx section of this guide first.<br>
<br>
<h2>Owncloud Manual installation</h2><br>
In <a href="https://www.feralhosting.com/faq/view?question=12">SSH</a> run this command. It will download the <code>setup.php</code> to the root of your <code>WWW</code><br>
<br>
<pre><code>wget -P ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F; <a href="https://download.owncloud.com/download/community/setup-owncloud.php">https:&#x2F;&#x2F;download.owncloud.com&#x2F;download&#x2F;community&#x2F;setup-owncloud.php</a></code></pre><br>
Now visit the URL in this format, in your browser, it will look something like this:<br>
<br>
 <strong>Important note:</strong> If you use or force https you may need to unblock the remote content of the installer in Firefox.<br>
<br>
<img src="https://raw.githubusercontent.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Owncloud%20-%20Basic%20setup/https.png"><br>
<br>
<pre><code><a href="http://username.server.feralhosting.com/setup-owncloud.php">http:&#x2F;&#x2F;username.server.feralhosting.com&#x2F;setup-owncloud.php</a></code></pre><br>
You should be able to just click on this file from your apache&#x2F;nginx&#x2F;h5ai index.<br>
<br>
<strong>1:</strong> Just click next<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Owncloud%20-%20Basic%20setup/web-install-1.png"><br>
<br>
<strong>2:</strong> Leave the installation directory as <code>owncloud</code>. This will create and install it to a the <code>&#x2F;owncloud</code> directory in your server root.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Owncloud%20-%20Basic%20setup/web-install-2.png"><br>
<br>
<strong>3:</strong> Click next when done to visit the final stage of the setup.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Owncloud%20-%20Basic%20setup/web-install-3.png"><br>
<br>
The easiest way to install Owncloud is to use the sqlite database option (default). <br>
<br>
Once you have visited the URL in a browser you will see this:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Owncloud%20-%20Basic%20setup/1.png"><br>
<br>
<h2>nginx</h2><br>
 <strong>Important note:</strong> This configuration depends on the user installing owncloud to the default location which is the subdirectory <code>&#x2F;owncloud</code> inside the <code>public_html</code> folder.<br>
<br>
<strong>Owncloud custom conf:</strong><br>
<br>
Now download a preconfigured conf file to use in conjunction with this edit:<br>
<br>
<pre><code>wget -qO ~&#x2F;.nginx&#x2F;conf.d&#x2F;000-default-server.d&#x2F;owncloud.conf <a href="http://git.io/nVy4Cg">http:&#x2F;&#x2F;git.io&#x2F;nVy4Cg</a></code></pre><br>
Now run this command in SSH:<br>
<br>
 <strong>Important note:</strong> You need to run this command at least once to properly configure the <code>owncloud.conf</code><br>
<br>
<pre><code>sed -ri &quot;s|fastcgi_pass(.*);|fastcgi_pass&nbsp; &nbsp; unix:$HOME&#x2F;.nginx&#x2F;php&#x2F;socket;|g&quot; ~&#x2F;.nginx&#x2F;conf.d&#x2F;000-default-server.d&#x2F;owncloud.conf</code></pre><br>
Now reload nginx:<br>
<br>
<pre><code>&#x2F;usr&#x2F;sbin&#x2F;nginx -s reload -c ~&#x2F;.nginx&#x2F;nginx.conf</code></pre><br>
Owncloud should now work as intended with nginx.<br>
<br>