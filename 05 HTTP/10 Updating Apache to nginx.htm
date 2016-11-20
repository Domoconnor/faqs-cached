<h1>Updating Apache to nginx</h1>

        
A web server is software that sends web pages to your browser over the HTTP protocol. Apache is the name of the current web server we&#x27;re using, however we&#x27;re looking to move to <code>nginx</code> as it&#x27;s easier to configure, uses less memory and is faster. Updating to <code>nginx</code> is essential if you want to run a lot of concurrent HTTP connections.<br>
<br>
To switch to <code>nginx</code> create the folder called <br>
<br>
<pre><code>.nginx</code></pre><br>
in the base of your home folder with an <a href="https://www.feralhosting.com/faq/view?question=187">FTP &#x2F; SFTP client</a>. <br>
<br>
Or <a href="https://www.feralhosting.com/faq/view?question=12">using SSH</a> run this command:<br>
<br>
<pre><code>mkdir -p ~&#x2F;.nginx</code></pre><br>
After <strong>waiting 5 minutes</strong> Apache will shut down and <code>nginx</code> will have been auto-configured to be very similar to Apache. It will attempt to:<br>
<br>
- Configure PHP<br>
- Serve domains from <code>~&#x2F;www&#x2F;*&#x2F;public_html</code><br>
- Password protect rutorrent<br>
- Set up an rtorrent SCGI rpc mount point at <code>&#x2F;$username&#x2F;RPC</code> (necessary for Transdroid)<br>
- Deny access to areas of rutorrent which do not need web access<br>
- Deny access to all files beginning with <code>.ht</code><br>
- Deny access to any folder with a <code>.htaccess</code> file at the time of auto-configuration<br>
<br>
<strong>Important note:</strong> The SCGI rpc password will be the same as the rutorrent password, for your Feral username, at the time the update was initiated. See this FAQ for changing these passwords if you have forgotten them - <a href="https://www.feralhosting.com/faq/view?question=22">Password protect your WWW folder</a><br>
<br>
Additional domain top-level configuration and domains can be updated by dropping (or editing) files in the directory: <br>
<br>
<pre><code>~&#x2F;.nginx&#x2F;conf.d</code></pre><br>
You should not need to do this if you just want to <a href="https://www.feralhosting.com/faq/view?question=52">add a domain</a>. <br>
<br>
Configuration for the default domain can be updated by adding (or editing) files in the folder <br>
<br>
<pre><code>~&#x2F;.nginx&#x2F;conf.d&#x2F;000-default-server.d</code></pre><br>
<strong>Important note:</strong> You will need to restart <code>nginx</code> to apply configuration changes you make, once nginx has been loaded, for them to take effect.<br>
<br>
If you run any custom configuration in Apache (found in the <code>.htaccess</code> files or the <code>~&#x2F;.apache2&#x2F;conf.d&#x2F;</code> directory) then you should carefully review and apply this configuration to <code>nginx</code>. <br>
<br>
<strong>Important note:</strong> As a precaution any folder containing a <code>.htaccess</code> file will be denied access at the time of auto-configuration.<br>
<br>
To review the configuration will need to consult the <a href="http://httpd.apache.org/docs/2.2/index.html">Apache 2.2 documentation</a> and corresponding <a href="http://wiki.nginx.org/Main">nginx command</a><br>
<br>
There exist tools to assist with the conversion if you <a href="https://www.google.com/&#x23;q=nginx&#x2B;htaccess&#x2B;converter">Google &quot;nginx htaccess converter&quot;</a>. The paths with a <code>.htaccess</code> are denied by the default server configuration in the files <br>
<br>
<pre><code>*-deny-htaccess.conf</code></pre><br>
Which can be removed once you&#x27;ve reviewed the set up.<br>
<br>
<strong>Reload your nginx.conf</strong><br>
<br>
To reload the nginx conf file use this command for changes to take effect use this command:<br>
<br>
<pre><code>&#x2F;usr&#x2F;sbin&#x2F;nginx -s reload -c ~&#x2F;.nginx&#x2F;nginx.conf</code></pre><br>
You will see this:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Updating%20Apache%20to%20nginx/nginx.png"><br>
<br>
This is normal, your changes have been applied. You may need clear your browser cache for some changes to take effect.<br>
<br>
<strong>Kill the nginx process</strong><br>
<br>
<code>nginx</code> can be killed and then automatically restarted by running the <a href="https://www.feralhosting.com/faq/view?question=12">SSH command</a> <br>
<br>
<pre><code>killall -9 -u $(whoami) nginx php5-fpm</code></pre><br>
and then waiting up to 5 minutes for it to be restarted.<br>
<br>
If nothing prevents nginx starting, like a bad .conf file, then running this command should show you the running processes.<br>
<br>
<pre><code>ps x | grep nginx | grep -v grep</code></pre><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Updating%20Apache%20to%20nginx/started.png"><br>
<br>
<br>
<strong>Notes:</strong><br>
<br>
In regards to this particular action:<br>
<br>
- Deny access to any folder with a <code>.htaccess</code> file at the time of auto-configuration<br>
<br>
What will happen is that a numbered <code>deny.conf</code> will be created in the the <code>~&#x2F;.nginx&#x2F;conf.d&#x2F;000-default-server.d</code> directory. This can break certain apps and will happen during the upgrade from Apache to nginx. An example of this is <code>_h5ai</code> if it was present during before upgrading to nginx.<br>
<br>
If you&#x27;ve setup couchpotato or sickrage&#x2F;sickbeard using our scripts, and found that the sites no longer work after updating Apache to nginx, please re-run the setup scripts for the programs.&nbsp; They allow you to choose to reinstall the nginx proxy bypass (Option #2).&nbsp; This will restore the sites without having to manually convert the .conf files from Apache to nginx.<br>
<br>
apache2nginx<br>
<br>
