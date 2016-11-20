<h1>PHP - modify settings</h1>

        
<br>
<h2>Apache and Nginx php settings using local php.ini</h2><br>
In SSH do the commands described in this FAQ. If you do not know how to SSH into your slot use this FAQ: <a href="https://www.feralhosting.com/faq/view?question=12">SSH basics - Putty</a><br>
<br>
<h3>Bash Script</h3><br>
This bash script will do these things for you.<br>
<br>
<strong>1:</strong> Install the Apache php.ini and configure the default mysql, mysqli and pdo sockets.<br>
<strong>2:</strong> Install the nginx php.ini and configure the default mysql, mysqli and pdo sockets.<br>
<strong>3:</strong> Reload Apache with immediate effect.<br>
<strong>4:</strong> Reload nginx and php-fpm with immediate effect.<br>
<br>
<pre><code>wget -qO ~&#x2F;phpsettings <a href="http://git.io/hGdl">http:&#x2F;&#x2F;git.io&#x2F;hGdl</a> &amp;&amp; bash ~&#x2F;phpsettings</code></pre><br>
Once you have used the script you can now edit and save your php.ini at:<br>
<br>
Apache = <code>~&#x2F;.apache2&#x2F;php.ini</code><br>
<br>
<pre><code>nano ~&#x2F;.apache2&#x2F;php.ini</code></pre><br>
nginx = <code>~&#x2F;.nginx&#x2F;php&#x2F;php.ini</code><br>
<br>
<pre><code>nano ~&#x2F;.nginx&#x2F;php&#x2F;php.ini</code></pre><br>
 <strong>Important note:</strong> The default mysql, mysqli and pdo socket settings are already set to your local socket path by the script.<br>
<br>
When you have finished editing the <code>php.ini</code> you can use the script to reload Apache or Nginx.<br>
<br>
<h2>Apache using htaccess</h2><br>
In your <code>.htaccess</code> files you can add these lines and change the paths or numbers to match yours:<br>
<br>
<strong>Important note:</strong> <code>.htaccess</code> files work recursively from their current location. If you want some settings to apply to the entire server put these settings in a <code>.htaccess</code> in your server root. If you only need them to apply to certain directories, place the settings in a <code>.htaccess</code> within those directories.<br>
<br>
This is an example of the <code>.htaccess</code> in your server root.<br>
<br>
Where <code>username</code> is your Feral username and <code>server</code> is the name of the server your slot is hosted on.<br>
<br>
<pre><code>~&#x2F;www&#x2F;username.server.feralhosting.com&#x2F;public_html&#x2F;.htaccess</code></pre><br>
<strong>Default Socket setting</strong><br>
<br>
<pre><code>php_value mysql.default_socket &quot;&#x2F;media&#x2F;DiskID&#x2F;home&#x2F;username&#x2F;private&#x2F;mysql&#x2F;socket&quot;
php_value mysqli.default_socket &quot;&#x2F;media&#x2F;DiskID&#x2F;home&#x2F;username&#x2F;private&#x2F;mysql&#x2F;socket&quot;</code></pre><br>
Will make it so <code>localhost</code> uses these socket paths.<br>
<br>
If networking has been enabled in your <code>~&#x2F;private&#x2F;mysql&#x2F;my.conf</code> you can also set these:<br>
<br>
<strong>Default port settings</strong><br>
<br>
<pre><code>php_value mysql.default_port 23456
php_value mysqli.default_port 23456</code></pre><br>
This will define the default port.<br>
<br>
<strong>Modifying other settings:</strong><br>
<br>
The basic concept is this:<br>
<br>
<pre><code>php_value some_setting value&#x2F;path</code></pre><br>
For example:<br>
<br>
<pre><code>php_value max_execution_time 100</code></pre><br>
This will change the default value from 30 to 100<br>
<br>
<strong>Max file upload size</strong><br>
<br>
<pre><code>php_value upload_max_filesize 100M
php_value post_max_size 100M
php_value max_input_time 300
php_value max_execution_time 300
php_value memory_limit = 100M</code></pre><br>
Will allow larger file uploads, up to <code>100M</code>.<br>
<br>
