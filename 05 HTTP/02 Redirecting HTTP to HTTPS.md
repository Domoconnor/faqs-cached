<h1>Redirecting HTTP to HTTPS</h1>

        
<br>
In SSH do the commands described in this FAQ. If you do not know how to SSH into your slot use this FAQ: <a href="https://www.feralhosting.com/faq/view?question=12">SSH basics - Putty</a><br>
<br>
<h3>Dual URL format force HTTPS</h3><br>
This guide will help you force HTTPS usage on your default domains, independent of one another, at the same time.<br>
<br>
First, please navigate to your <code>public_html</code> folder (replacing username and server with the relevant details) via FTP or SFTP:<br>
<br>
<pre><code>~&#x2F;www&#x2F;username.server.feralhosting.com&#x2F;public_html&#x2F;</code></pre><br>
Second, create a file called <strong>.htaccess</strong> and place the following inside it:<br>
<br>
You <strong>DO NOT</strong> need to edit this code before it will work for you<br>
<br>
To edit in SSH do:<br>
<br>
<pre><code>nano -w ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;.htaccess</code></pre><br>
Then copy an paste this code below:<br>
<br>
<pre><code>RewriteEngine on
#
RewriteCond %{HTTP:X-Forwarded-Proto} !https
RewriteCond %{HTTP:x-HOST} ^.+\..+\.feralhosting\.com$ [NC]
RewriteRule ^.*$ <a href="https://%">https:&#x2F;&#x2F;%</a>{HTTP:X-Host}%{REQUEST_URI} [R,L]
#
RewriteCond %{HTTP:X-Forwarded-Proto} !https
RewriteCond %{HTTP:x-HOST} ^.+\.feralhosting\.com$ [NC]
RewriteRule ^.*$ <a href="https://%">https:&#x2F;&#x2F;%</a>{HTTP:X-Host}&#x2F;%{ENV:USER}%{REQUEST_URI} [R,L]</code></pre><br>
The press and hold <code>CTRL</code> then press <code>x</code> to save. Press <code>y</code> to confirm.<br>
<br>
Run this <code>chmod</code> command in SSH no matter how you created the file:<br>
<br>
<pre><code>chmod 644 ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;.htaccess</code></pre><br>
If you are still unsure here is an example you can paste into your <code>.htaccess</code> on pastebin. <br>
<br>
Once saved it should happen almost immediately. Though you might have to clear your history&#x2F;cache and&#x2F;or restart the browser to see the change in some cases.<br>
<br>
This will work for both URL formats at the same time:<br>
<br>
<code><a href="http://username.server.feralhosting.com">http:&#x2F;&#x2F;username.server.feralhosting.com</a></code> to <code><a href="https://username.server.feralhosting.com">https:&#x2F;&#x2F;username.server.feralhosting.com</a></code><br>
<br>
and<br>
<br>
<code><a href="http://server.feralhosting.com/username">http:&#x2F;&#x2F;server.feralhosting.com&#x2F;username</a></code> to <code><a href="https://server.feralhosting.com/username">https:&#x2F;&#x2F;server.feralhosting.com&#x2F;username</a></code><br>
<br>
<h3>Force all HTTP to <code><a href="https://server.feralhosting.com">https:&#x2F;&#x2F;server.feralhosting.com</a></code> only</h3><br>
If you would like to force all traffic to only:<br>
<br>
<pre><code>server.feralhosting.com&#x2F;username</code></pre><br>
<strong>Be Warned:</strong> this will effectively lock you out of the <code>username.server.feralhosting.com</code> URL format, breaking or locking you out of many Web-apps and usages of your <code>www</code>.<br>
<br>
Then use this code instead.<br>
<br>
<pre><code>RewriteEngine on
#
RewriteCond %{HTTP:X-Forwarded-Proto} !https
#
RewriteCond %{HTTP:x-HOST} ^(.+\.)?(.+)\.feralhosting\.com$ [NC]
RewriteRule ^.*$ <a href="https://%">https:&#x2F;&#x2F;%</a>{ENV:APACHE_HOSTNAME}&#x2F;%{ENV:USER}%{REQUEST_URI} [R,L] 
RewriteCond %{HTTP:x-HOST} ^(.+\.)(.+)\.feralhosting\.com$ [NC]
RewriteRule ^.*$ <a href="https://%">https:&#x2F;&#x2F;%</a>{ENV:APACHE_HOSTNAME}&#x2F;%{ENV:USER}%{REQUEST_URI} [R,L] </code></pre><br>
There are two rules we need to force <code><a href="https://server.feralhosting.com">https:&#x2F;&#x2F;server.feralhosting.com</a></code><br>
<br>
<code><a href="http://server.feralhosting.com/username/">http:&#x2F;&#x2F;server.feralhosting.com&#x2F;username&#x2F;</a></code> to <code><a href="https://server.feralhosting.com/username">https:&#x2F;&#x2F;server.feralhosting.com&#x2F;username</a></code><br>
<br>
<code><a href="http://username.server.feralhosting.com/">http:&#x2F;&#x2F;username.server.feralhosting.com&#x2F;</a></code> to <code><a href="https://server.feralhosting.com/username">https:&#x2F;&#x2F;server.feralhosting.com&#x2F;username</a></code><br>
<br>
<h3>Fix password protected folders</h3><br>
Now after applying the above steps, you&#x27;ll be asked twice for your credentials when accessing an authentication-requiring folder like ruTorrent via HTTP.<br>
<br>
You can fix this easily by enclosing the authentication by a <code>&lt;FilesMatch &quot;.&quot;&gt;</code> block.<br>
<br>
For example, this is how your .htaccess file in your ruTorrent folder should look like:<br>
<br>
<pre><code>&lt;FilesMatch &quot;.&quot;&gt;
AuthType Basic
AuthName &quot;username&quot;
AuthUserFile &quot;path to .htpasswd&quot;
Require valid-user
&lt;&#x2F;FilesMatch&gt;</code></pre><br>
That&#x27;s it. This will also improve security, as the credentials won&#x27;t be sent in plaintext via HTTP.<br>
<br>
<h3>nginx</h3><br>
This will force HTTPS usage on your default domains, independent of one another, at the same time.<br>
<br>
Execute this command in SSH to have the required files automatically created and nginx restarted.<br>
<br>
<pre><code>wget -qO ~&#x2F;nginxhttps.sh <a href="http://git.io/A34SpA">http:&#x2F;&#x2F;git.io&#x2F;A34SpA</a> &amp;&amp; bash ~&#x2F;nginxhttps.sh</code></pre><br>
<br>
