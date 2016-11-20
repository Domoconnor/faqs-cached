<h1>Setting up Public Key Authentication - Linux</h1>

        
<br>
This guide is for <strong>GNU Linux users</strong> who wish to use Public&#x2F;Private Key Authentication to quickly access their shell with Feral Hosting. It is primarily for Ubuntu Linux, but most commands apply to most other distributions.<br>
<br>
<h2>Generate your own public and private key pair</h2><br>
Issue this command. It will ask you specify where you want to store the keys, just hit the [Enter] key to use the default. Specifying a password is not mandatory, but in the interests of security it&#x27;s really necessary. Most modern Linux distributions will allow you to automate the logging of this key so you won&#x27;t have to type it in at boot.<br>
<br>
<pre><code>ssh-keygen</code></pre><br>
<img src="https://raw.githubusercontent.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Linux%20Command-Line%20-%20Advanced/Setting%20Up%20Public%20Key%20Authentication%20-%20Linux/1.png"><br>
<br>
<h2>Send Public key to server and add to authorized_keys</h2><br>
<strong>1:</strong> Securely send public key to remote server<br>
<br>
<pre><code>scp ~&#x2F;.ssh&#x2F;id_rsa.pub username@server.feralhosting.com:~&#x2F;</code></pre><br>
<strong>2:</strong> Login to remote server<br>
<br>
<pre><code>ssh username@server.feralhosting.com</code></pre><br>
<strong>3:</strong> Add the key you sent to the <code>authorized_keys</code> list of the server (Note: If you get the message <code>No such file or directory</code>, it means that your SSH directory doesn&#x27;t exist.&nbsp; Type <code>mkdir ~&#x2F;.ssh</code> and then retry the following command.)<br>
<br>
<pre><code>cat id_rsa.pub &gt;&gt; ~&#x2F;.ssh&#x2F;authorized_keys</code></pre><br>
<strong>4:</strong> Remove public key file<br>
<br>
<pre><code>rm id_rsa.pub</code></pre><br>
<h2>Test that it works</h2><br>
Log out of a SSH session you already have and try logging into the server with <br>
<br>
<pre><code>ssh username@server.feralhosting.com</code></pre><br>
You should now be automatically logged in using Public Key Authentication.<br>
