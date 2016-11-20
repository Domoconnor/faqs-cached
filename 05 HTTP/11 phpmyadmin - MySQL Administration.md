<h1>phpmyadmin - MySQL Administration</h1>

        
<br>
You will need to have Mysql already installed. You can do this from the <a href="https://www.feralhosting.com/manager/">[b]Install Software[&#x2F;b] link in your Manager</a><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/installmysql.png"><br>
<br>
This is a relevant FAQ: <a href="https://www.feralhosting.com/faq/view?question=213">Mysql - Change php settings using htaccess</a><br>
<br>
In SSH do these commands. Use this FAQ if you do not know how to SSH into your slot: <a href="https://www.feralhosting.com/faq/view?question=12">SSH basics - Putty</a><br>
<br>
<h2>phpmyadmin basic setup</h2><br>
Download the phpMyAdmin package:<br>
<br>
<pre><code>wget -qO ~&#x2F;phpMyAdmin.zip <a href="https://files.phpmyadmin.net/phpMyAdmin/4.5.0.2/phpMyAdmin-4.5.0.2-all-languages.zip">https:&#x2F;&#x2F;files.phpmyadmin.net&#x2F;phpMyAdmin&#x2F;4.5.0.2&#x2F;phpMyAdmin-4.5.0.2-all-languages.zip</a>
unzip -qo ~&#x2F;phpMyAdmin.zip
cp -rf ~&#x2F;phpMyAdmin-*-all-languages&#x2F;. ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;phpmyadmin
mkdir -p ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;phpmyadmin&#x2F;config
cd &amp;&amp; rm -rf phpMyAdmin{-*-languages,.zip}</code></pre><br>
<h2>https URL redirect fix:</h2><br>
<strong>Important note:</strong> These commands only apply to a fresh installation. For example updating Apache to nginx will break the fix.<br>
<br>
Please run the command below that matches your Web server. The Default is Apache. It will only be nginx if you manually updated Apache to nginx.<br>
<br>
<strong>Default: Apache</strong><br>
<br>
<pre><code>sed -i &#x27;s&#x2F;443)&#x2F;80)&#x2F;g&#x27; ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;phpmyadmin&#x2F;libraries&#x2F;Config.class.php</code></pre><br>
<strong>nginx</strong><br>
<br>
<pre><code>sed -i &#x27;s&#x2F; 80)&#x2F; 8080)&#x2F;g;s&#x2F;443&#x2F;8080&#x2F;g&#x27; ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;phpmyadmin&#x2F;libraries&#x2F;Config.class.php</code></pre><br>
<h2>Completing the Setup</h2><br>
The rest of this FAQ must be completed in a Browser.<br>
<br>
Visit this page in a browser, replacing Your username with your Feral username and server with your slot servername<br>
<br>
<pre><code><a href="http://username.server.feralhosting.com/phpmyadmin/setup/">http:&#x2F;&#x2F;username.server.feralhosting.com&#x2F;phpmyadmin&#x2F;setup&#x2F;</a></code></pre><br>
Now you will see this page.<br>
<br>
Click on <code>New Server</code> to create our first custom server configuration file.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/phpmyadmin%20-%20MySQL%20Administration/1.png"><br>
<br>
You do not need to do much here. Fill in what the image shows. Click on <code>Save</code> when you are done:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/phpmyadmin%20-%20MySQL%20Administration/2.png"><br>
<br>
You will need to select your server from the drop down if it is not already selected and then click save.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/phpmyadmin%20-%20MySQL%20Administration/3.png"><br>
<br>
You should see this dialogue once you have saved:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/phpmyadmin%20-%20MySQL%20Administration/4.png"><br>
<br>
Once you have saved the configuration you need to run these two command in SSH to finalise the installation:<br>
<br>
<pre><code>cd ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;
cp -f phpmyadmin&#x2F;config&#x2F;config.inc.php ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;phpmyadmin&#x2F;config.inc.php
cd &amp;&amp; rm -rf www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;phpmyadmin&#x2F;config</code></pre><br>
Now you can return to the main page and login at:<br>
<br>
<pre><code>&#x2F;phpmyadmin</code></pre><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/phpmyadmin%20-%20MySQL%20Administration/5.png"><br>
<br>
<h2>https URL redirect issue</h2><br>
<strong>Important note:</strong> If you force https and you did not run the fix commands above the you will most likely see this error after you log in.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/phpmyadmin%20-%20MySQL%20Administration/6.png"><br>
<br>
If you don&#x27;t want to use the command you need to press back in your browser or using your mouse button (if available) when you see the error.<br>
<br>
What is happening is that the application tries to redirect on the wrong port and gets confused.<br>
<br>
<pre><code><a href="https://somesite.com:80/...">https:&#x2F;&#x2F;somesite.com:80&#x2F;...</a></code></pre><br>
For nginx:<br>
<br>
<pre><code><a href="https://somesite.com:8080/...">https:&#x2F;&#x2F;somesite.com:8080&#x2F;...</a></code></pre><br>
If you manually edit out the port it works fine to<br>
<br>
<pre><code><a href="https://somesite.com/...">https:&#x2F;&#x2F;somesite.com&#x2F;...</a></code></pre><br>
<br>
