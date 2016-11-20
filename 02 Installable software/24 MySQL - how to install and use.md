<h1>MySQL - how to install and use</h1>

        
You will need to have Mysql already installed. You can do this from the <a href="https://www.feralhosting.com/manager/">[b]Install Software[&#x2F;b] link in your Manager</a><br>
<br>
Current Version used in the Feral Installer = <code>5.6.12</code><br>
<br>
Our installation service will compile version <code>5.6.12</code> and place it in your account giving you complete control over it; normally the installation directory is <br>
<br>
<pre><code>~&#x2F;private&#x2F;mysql&#x2F;</code></pre><br>
Which contains everything from error logs, binaries to the data directories.<br>
<br>
The binaries are stored in:<br>
<br>
<pre><code>~&#x2F;private&#x2F;mysql&#x2F;bin</code></pre><br>
You can call them directly from there prefixing this to any command:<br>
<br>
<pre><code>~&#x2F;private&#x2F;mysql&#x2F;bin</code></pre><br>
Or add it to your PATH using this command:<br>
<br>
<pre><code>[[ ! &quot;$(grep &#x27;~&#x2F;private&#x2F;mysql&#x2F;bin&#x27; ~&#x2F;.bashrc)&quot; ]] &amp;&amp; echo &#x27;export PATH=~&#x2F;private&#x2F;mysql&#x2F;bin:$PATH&#x27; &gt;&gt; ~&#x2F;.bashrc ; source ~&#x2F;.bashrc</code></pre><br>
<h3>Restarting Mysql</h3><br>
If for some reason MySQL crashes or goes down, you can restart it by logging in to <a href="https://www.feralhosting.com/faq/view?question=12">PuTTy</a> and executing the command:<br>
<br>
<pre><code>bash ~&#x2F;private&#x2F;mysql&#x2F;launch.sh</code></pre><br>
<h3>Editing the Configuration files</h3><br>
You can edit the configuration files to your needs but you are asked to remember that you are sharing the server resources with others. If your settings are too extreme and other users become affected Staff will intervene. So be cautious and mindful with these settings.<br>
<br>
<h3>Enable Networking</h3><br>
<strong>Important note:</strong> the default user <code>root</code> is <code>localhost</code> only. This means that this user cannot access the server over networking. It is recommended you leave this as it is and create new and limited users for your network connections where possible.<br>
<br>
Networking has been disabled by default, within the configuration which means only a socket connection is available.<br>
<br>
<pre><code>~&#x2F;private&#x2F;mysql&#x2F;my.conf</code></pre><br>
You will need to comment out<br>
<br>
<pre><code>skip-networking</code></pre><br>
In the <code>mysqld</code> section of the <code>my.conf</code> like this:<br>
<br>
<pre><code># skip-networking</code></pre><br>
Optional: This command will make the change to your <code>~&#x2F;private&#x2F;mysql&#x2F;my.conf</code> for you.<br>
<br>
<pre><code>sed -i &#x27;s&#x2F;^skip-networking&#x2F;# skip-networking&#x2F;g&#x27; ~&#x2F;private&#x2F;mysql&#x2F;my.conf</code></pre><br>
Take note of the port in the <code>mysqld</code> section of the <code>my.conf</code><br>
<br>
This command should show you, in SSH, the port from a default <code>my.conf</code><br>
<br>
<pre><code>sed -n &#x27;11p&#x27; ~&#x2F;private&#x2F;mysql&#x2F;my.conf</code></pre><br>
And then restart mysql for this to take effect.<br>
<br>
<a href="https://www.feralhosting.com/faq/view?question=158">Restarting - rtorrent - Deluge - Transmission - MySQL</a><br>
<br>
<h3>Using the Socket</h3><br>
The socket path will be displayed in your Slot Details page post installation:<br>
<br>
<pre><code>&#x2F;media&#x2F;DiskID&#x2F;username&#x2F;private&#x2F;mysql&#x2F;socket</code></pre><br>
<h3>Example using a socket with WordPress</h3><br>
<a href="https://www.feralhosting.com/faq/view?question=211">Wordpress basic set up</a><br>
<br>
Here is an example if the Worpress configuration file post installation:<br>
<br>
<pre><code>define(&#x27;DB_HOST&#x27;, &#x27;:&#x2F;media&#x2F;DiskID&#x2F;home&#x2F;username&#x2F;private&#x2F;mysql&#x2F;socket&#x27;);</code></pre><br>
<strong>Important note:</strong> If the web application uses PHP&#x27;s &quot;mysql&quot; driver (not mysqli and others) to connect to MySQL you can use the &quot;:&#x2F;media&#x2F;DiskID&#x2F;home&#x2F;username&#x2F;private&#x2F;mysql&#x2F;socket&quot; to instruct it to use the socket.<br>
<br>
In some cases this FAQ can be applied, though not all: <a href="https://www.feralhosting.com/faq/view?question=213">Mysql - Change php settings using htaccess</a><br>
<br>
<h3>Mysql Administration</h3><br>
We can set up <a href="http://www.phpmyadmin.net/">phpMyAdmin</a> (for database administration) if requested via a ticket in the support section.<br>
<br>
<strong>Set-up phpMyAdmin</strong> manually for easy and quick mysql administration using this FAQ: <a href="https://www.feralhosting.com/faq/view?question=230">phpmyadmin - MySQL Administration</a><br>
<br>
<strong>Set-up Adminer</strong> manually for easy and quick mysql administration using this FAQ: <a href="https://www.feralhosting.com/faq/view?question=116">Adminer - MySQL administration</a>.<br>
<br>
<h3>Backup your MYSQL databases via SSH (crontab friendly)</h3><br>
Connect using SSH and run this command to backup a single (or multiple if you read on) databases of your choosing to folder you have created via ssh.<br>
<br>
You must first edit this&#x2F;these commands to reflect some personal details.<br>
<br>
<code>DiskID:</code> Your disk ID from the full path.<br>
<br>
<code>USERNAME:</code> Your Feral Username<br>
 <br>
<code>PASSWORD:</code> NO SPACES between the <code>-p</code> and the <code>PASSWORD</code>. Use your root mysql password found via your software page after installing mysql.<br>
<br>
<code>YourDB1:</code> The name of the database you wish to backup.<br>
<br>
<code>mysqlbak:</code> The location where you wish the file to be backup up to.<br>
<br>
<code>YourDB1:</code> The name you wish the backed up file to have.<br>
<br>
To quickly break down this command:<br>
<br>
First we prefix the path to the binary , if it was not manually added to the PATH:<br>
<br>
<pre><code>~&#x2F;private&#x2F;mysql&#x2F;bin </code></pre><br>
<code>&amp;&amp;</code> Signifies for the command to continue with the next command if the previous worked.<br>
<br>
<pre><code>&amp;&amp;</code></pre><br>
Then we execute a backup command using the mysqldump binary and pass it some arguments and info. In this case the socket location, username and password for ROOT, Database to be backed up and then where we want the backup to be stored.<br>
<br>
<pre><code>.&#x2F;mysqldump --socket=&#x2F;media&#x2F;DiskID&#x2F;home&#x2F;USERNAME&#x2F;private&#x2F;mysql&#x2F;socket -u root -pPASSWORD YourDB1 &gt; ~&#x2F;mysqlbak&#x2F;YourDB1</code></pre><br>
<strong>Here is the full command.</strong><br>
<br>
<pre><code>~&#x2F;private&#x2F;mysql&#x2F;bin&#x2F;.&#x2F;mysqldump --socket=&#x2F;media&#x2F;DiskID&#x2F;home&#x2F;USERNAME&#x2F;private&#x2F;mysql&#x2F;socket -u root -pPASSWORD YourDB1 &gt; ~&#x2F;mysqlbak&#x2F;YourDB1</code></pre><br>
In this second version we are backing up 2 Databases.<br>
<br>
First I will break down the expanded version of the multiple backup command.<br>
<br>
<code>&amp;&amp;</code> Signifies for the command to continue with the next command if the previous worked. It can be used to string multiple commands (more than two) as shown below.<br>
<br>
<pre><code>&amp;&amp;</code></pre><br>
Then we add a clone of the first command minus the CD command. For example we are also backing up <code>YOURBD2</code> in this example so we append the previous command with.<br>
<br>
<pre><code>.&#x2F;mysqldump --socket=&#x2F;media&#x2F;DiskID&#x2F;home&#x2F;USERNAME&#x2F;private&#x2F;mysql&#x2F;socket -u root -pPASSWORD YourDB2 &gt; ~&#x2F;mysqlbak&#x2F;YourDB2</code></pre><br>
Notice the <code>&amp;&amp;</code> in-between new commands and the new database backup command <code>YourDB2</code> appended to the first.<br>
<br>
<strong>Here is the full command.</strong><br>
<br>
<pre><code>~&#x2F;private&#x2F;mysql&#x2F;bin&#x2F;.&#x2F;mysqldump --socket=&#x2F;media&#x2F;DiskID&#x2F;home&#x2F;USERNAME&#x2F;private&#x2F;mysql&#x2F;socket -u root -pPASSWORD YourDB1 &gt; ~&#x2F;mysqlbak&#x2F;YourDB1 &amp;&amp; .&#x2F;mysqldump --socket=&#x2F;media&#x2F;DiskID&#x2F;home&#x2F;USERNAME&#x2F;private&#x2F;mysql&#x2F;socket -u root -pPASSWORD YourDB2 &gt; ~&#x2F;mysqlbak&#x2F;YourDB2</code></pre><br>
You can add as many databases as you need by appending the new ones to the end of the command.<br>
<br>
