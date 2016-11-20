<h1>phpBB3 - basic setup</h1>

        
<br>
You will need to have MySQL already installed. You can do this from your <a href="https://www.feralhosting.com/manager/">Manager</a><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/install_mysql.png"><br>
<br>
In SSH do these commands. Use this FAQ if you do not know how to SSH into your slot: <a href="https://www.feralhosting.com/faq/view?question=12">SSH basics - Putty</a><br>
<br>
<h3>Download and extract</h3><br>
Download the phpBB3 package:<br>
<br>
<pre><code>wget -qO ~&#x2F;phpbb3.zip <a href="https://www.phpbb.com/files/release/phpBB-3.1.3.zip">https:&#x2F;&#x2F;www.phpbb.com&#x2F;files&#x2F;release&#x2F;phpBB-3.1.3.zip</a></code></pre><br>
Then extract the file archive:<br>
<br>
<pre><code>unzip -qo ~&#x2F;phpbb3.zip -d ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html</code></pre><br>
Optional: Clean up by removing the phpBB3 zip<br>
<br>
<pre><code>rm -f ~&#x2F;phpbb3.zip</code></pre><br>
<h3>Preparation</h3><br>
<strong>Step 1:</strong> Make a limited access user and a new database to use with phpBB3 - <a href="https://www.feralhosting.com/faq/view?question=116">Adminer - MySQL administration</a><br>
<br>
<strong>Step 2:</strong> The continue with the installation in this FAQ..<br>
<br>
<h3>Installation</h3><br>
phpBB3 is now ready to install via a web browser.<br>
<br>
It is highly recommended you follow this FAQ and create a new database with a limited user instead of using root as mentioned in preparation Step 1 above - <a href="https://www.feralhosting.com/faq/view?question=116">How to install MySQL and MySQL Adminer for easy MySQL administration</a><br>
<br>
Next Visit the web based installer, which by default is at:<br>
<br>
 <strong>Important note:</strong> nginx users should use this full URL since the redirect to the installation causes issues. If you get redirected to a URL with <code>:8080</code> then remove the <code>:8080</code> from the address bar and press enter or use the full URL format below.<br>
<br>
<pre><code><a href="http://username.server.feralhosting.com/phpBB3/install/index.php">http:&#x2F;&#x2F;username.server.feralhosting.com&#x2F;phpBB3&#x2F;install&#x2F;index.php</a></code></pre><br>
Progress with the installer.<br>
<br>
<strong>Important note:</strong> Feral does not include email support via php mail. You will have to configure phpBB3 to use an external smtp service, like Google Apps.<br>
<br>
<h3>Database settings</h3><br>
Database type: <code>mysql</code><br>
<br>
Your socket path will be displayed on the Slot details page for the relevant slot.<br>
<br>
<strong>Database hostname:</strong> <code>:&#x2F;media&#x2F;DiskID&#x2F;username&#x2F;private&#x2F;mysql&#x2F;socket</code><br>
<br>
<strong>Database name:</strong> The name of the non root user you created in Adminer.<br>
<br>
<strong>Database name:</strong> The database you created in Adminer.<br>
<br>
Leave all other fields blank or with their defaults.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/phpBB3 - basic setup/dbsettings-socket.png"><br>
<br>
<h3>URL Settings</h3><br>
While phpBB3 can use both URL formats, it will default to <code>username.server.feralhosting.com</code> as the primary URL format (noticeable with login redirects and similar). <br>
<br>
Fortunately we can change this without having to hack phpbb3.<br>
<br>
When you arrive at Server URL Settings page of the installer, follow the pointers in the image to make the server.feralhosting.com&#x2F;username URL format the default and primary one.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/phpBB3 - basic setup/urlsettings.png"><br>
<br>
<h2>Removing the installation folder</h2><br>
Once the set-up is complete you can use this command to remove the installation directory.<br>
<br>
<pre><code>rm -rf ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;phpBB3&#x2F;install</code></pre><br>
<br>
