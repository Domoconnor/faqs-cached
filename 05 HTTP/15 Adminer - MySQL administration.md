<h1>Adminer - MySQL administration</h1>

        
<strong>Step 1:</strong> First, go to the <a href="https://www.feralhosting.com/manager/">Account Manager</a> and then use the <a href="https://www.feralhosting.com/manager/">[b]Install Software[&#x2F;b] link in your Manager</a> for that slot:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/installmysql.png"><br>
<br>
<strong>Step 2:</strong> Install MySQL via the Software Page (selecting the radio button to the left of MySQL):<br>
<br>
<strong>Important note:</strong> Take note of your <code>Socket</code> path and your <code>Password</code> once the installation is completed. You do not need them until Step 2. Your username should be <code>root</code>.<br>
<br>
<strong>Important note:</strong> MySQL can take up to 15 minutes to install as it is compiled upon request of installation so please be patient:<br>
<br>
<strong>Important note:</strong> If you have your own domain you can use this <a href="https://www.feralhosting.com/faq/view?question=52">VHost FAQ</a> to host it here.<br>
<br>
This is a relevant (optional) FAQ: <a href="https://www.feralhosting.com/faq/view?question=213">PHP - modify settings</a> for configuration of some PHP settings before you start.<br>
<br>
This next stage of the guide needs to be done in an SSH client such as PuTTy.How to <a href="https://www.feralhosting.com/faq/view?question=12">SSH</a> to your slot.<br>
<br>
<strong>Step 3:</strong> Now to install Adminer to configure your MySQL using these SSH commands:<br>
<br>
<pre><code>mkdir -p ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;adminer &amp;&amp; cd $_
wget -qO index.php <a href="https://www.adminer.org/static/download/4.2.5/adminer-4.2.5-mysql.php">https:&#x2F;&#x2F;www.adminer.org&#x2F;static&#x2F;download&#x2F;4.2.5&#x2F;adminer-4.2.5-mysql.php</a></code></pre><br>
<strong>Step 4:</strong><br>
<br>
<br>
<strong>1:</strong> Now go to your slot HTTP URL which MUST be in this format, where <code>username</code> if your Feral username and <code>server</code> if the name of the server that the relevant slot is hosted on.<br>
<br>
<pre><code><a href="http://username.server.feralhosting.com/adminer">http:&#x2F;&#x2F;username.server.feralhosting.com&#x2F;adminer</a></code></pre><br>
You can use https if you accept the Feral certificate, which is a mismatch to the URL format but perfectly fine for the purpose.<br>
<br>
<pre><code><a href="https://username.server.feralhosting.com/adminer">https:&#x2F;&#x2F;username.server.feralhosting.com&#x2F;adminer</a></code></pre><br>
<strong>Important note:</strong> The URL format <code>server.feralhosting.com&#x2F;username&#x2F;</code> will not work for Adminer.<br>
<br>
<strong>2:</strong> You will need the <code>Socket</code> path, <code>username</code> and <code>password</code> you obtained after installing the MySQL server from the very first step as shown on the Slot Details page for the relevant slot.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/mysqlsocket.png"><br>
<br>
<strong>Important note:</strong> Put the socket path in the <code>hostname&#x2F;server</code> field prefixed with a <a href="http://en.wikipedia.org/wiki/Colon_%28punctuation%29">colon :</a>, for example:<br>
<br>
<pre><code>:&#x2F;media&#x2F;DiskID&#x2F;home&#x2F;username&#x2F;private&#x2F;mysql&#x2F;socket</code></pre><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Adminer%20-%20MySQL%20administration/0.0.png"><br>
<br>
<strong>3:</strong> Put in <code>root</code> for the <code>username</code><br>
<br>
<strong>4:</strong> Put in the <code>password</code> obtained from the software install page.<br>
<br>
<h3>A very simple overview of creating a New Database and User.</h3><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Adminer%20-%20MySQL%20administration/0.png"><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Adminer%20-%20MySQL%20administration/1.png"><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Adminer%20-%20MySQL%20administration/2.png"><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Adminer%20-%20MySQL%20administration/3.png"><br>
<br>
You can edit the user in the next step as well.<br>
<br>
<strong>Important note:</strong> This user is going to be restricted <code>localhost</code> connections only by default. Meaning if you do not use a socket they will not be able to connect to the database.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Adminer%20-%20MySQL%20administration/4.local.png"><br>
<br>
If you require that your user has network access (networking has been enabled) to the Database you would do this instead:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Adminer%20-%20MySQL%20administration/4.any.png"><br>
<br>
Where the Server files has had <code>localhost</code> has been changed to <code>%</code> allowing outside connections to the Database.<br>
<br>
<strong>Important note:</strong> These are safe to use privileges that will work with most (pretty much all) web applications.<br>
<br>
In this image you can see that we are editing the privileges for the database <code>example</code> that we just created:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Adminer%20-%20MySQL%20administration/adminerpriv.png"><br>
<br>
Once saved, you are ready to use this new Database and user with your web applications.<br>
<br>
