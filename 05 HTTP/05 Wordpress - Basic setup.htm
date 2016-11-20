<h1>Wordpress - Basic setup</h1>

        
<br>
You will need to have MySQL already installed. You can do this from the <code>Install Software</code> link in your <a href="https://www.feralhosting.com/manager/">Account Manager</a> for the relevant slot.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/installmysql.png"><br>
<br>
<strong>Important note:</strong> MySQL can take up to 15 minutes to install as it is compiled upon request of installation so please be patient.<br>
<br>
<strong>Important note:</strong> If you have your own domain you can use this <a href="https://www.feralhosting.com/faq/view?question=52">VHost FAQ</a> to host it here.<br>
<br>
This is a relevant FAQ: <a href="https://www.feralhosting.com/faq/view?question=213">PHP - modify settings</a><br>
<br>
<strong>Step 1:</strong> In order to use Wordpress you will need to have MySQL user and database set up for it to connect with to MySQL with, so follow this FAQ: <a href="https://www.feralhosting.com/faq/view?question=116">Adminer - MySQL administration</a><br>
<br>
<strong>Step 2:</strong> Then in SSH do these commands. Use this FAQ if you do not know how to SSH into your slot: <a href="https://www.feralhosting.com/faq/view?question=12">SSH basics - Putty</a><br>
<br>
<h2>Bash script easy download and extract to default WWW</h2><br>
This bash script will download and extract Wordpress into the <code>&#x2F;wordpress</code> subdirectory for you to your <em>default</em> Feral WWW directory.<br>
<br>
<pre><code>wget -qO ~&#x2F;install.wordpress <a href="http://git.io/2JBQlg">http:&#x2F;&#x2F;git.io&#x2F;2JBQlg</a> &amp;&amp; bash ~&#x2F;install.wordpress</code></pre><br>
<h2>Install to the WWW subdirectory &#x2F;wordpress manually:</h2><br>
 <strong>Important note:</strong> Nginx users using the default feral URLs must add this configuration file and then reload nginx for permalinks and similar to function properly. If you are using a custom vHost, the vHost FAQ already covers this in the provided template.<br>
<br>
Use these commands if you installed wordpress to the default subdirectory of <code>&#x2F;wordpress</code><br>
<br>
<pre><code>wget -qO ~&#x2F;.nginx&#x2F;conf.d&#x2F;000-default-server.d&#x2F;wordpress.conf <a href="http://git.io/vO6NA">http:&#x2F;&#x2F;git.io&#x2F;vO6NA</a>
&#x2F;usr&#x2F;sbin&#x2F;nginx -s reload -c ~&#x2F;.nginx&#x2F;nginx.conf</code></pre><br>
Use these commands if you installed wordpress to the default root directory of www.<br>
<br>
<pre><code>wget -qO ~&#x2F;.nginx&#x2F;conf.d&#x2F;000-default-server.d&#x2F;wordpress.conf&nbsp; <a href="http://git.io/vO6Nj">http:&#x2F;&#x2F;git.io&#x2F;vO6Nj</a>
&#x2F;usr&#x2F;sbin&#x2F;nginx -s reload -c ~&#x2F;.nginx&#x2F;nginx.conf</code></pre><br>
If you installed to a custom location you should download one of the above and then you will need to modify the location inside the conf file to reflect your custom location. Then reload nginx.<br>
<br>
Do this command in SSH:<br>
<br>
<pre><code>wget -qO ~&#x2F;latest.tar.gz <a href="http://wordpress.org/latest.tar.gz">http:&#x2F;&#x2F;wordpress.org&#x2F;latest.tar.gz</a></code></pre><br>
Now you must decide where to install Worpdress.<br>
<br>
<h2>Option 1: Install to the default WWW subdirectory &#x2F;wordpress manually:</h2><br>
Do this command to install Wordpress into the subdirectory <code>&#x2F;wordpress</code> inside the default Feral WWW directory:<br>
<br>
<pre><code>tar xf ~&#x2F;latest.tar.gz -C ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;</code></pre><br>
<h2>Option 2: Install to the WWW root directory manually:</h2><br>
Do this command to install Wordpress into the root of the default Feral WWW directory:<br>
<br>
<pre><code>tar xf ~&#x2F;latest.tar.gz&nbsp; --strip-components=1&nbsp; -C ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;</code></pre><br>
<h2>Custom domain option 1: Install to the Custom domain WWW subdirectory &#x2F;wordpress:</h2><br>
This requires you have followed this FAQ - <a href="https://www.feralhosting.com/faq/view?question=52">Host a virtual host on your Feral slot</a><br>
<br>
Use this command format, where <code>example.co.uk</code> is replaced by your domain name.<br>
<br>
<pre><code>tar xf ~&#x2F;latest.tar.gz -C ~&#x2F;www&#x2F;example.co.uk&#x2F;public_html&#x2F;</code></pre><br>
<h2>Custom domain option 2: Install to the Custom domain WWW root directory:</h2><br>
Use this command to install it to the root of your WWW instead.<br>
<br>
<pre><code>tar xf ~&#x2F;latest.tar.gz&nbsp; --strip-components=1 -C ~&#x2F;www&#x2F;example.co.uk&#x2F;public_html&#x2F;</code></pre><br>
Optionally: remove the tar archive:<br>
<br>
<pre><code>cd &amp;&amp; rm -f latest.tar.gz</code></pre><br>
Now Visit your <code>public_html&#x2F;wordpress</code> directory in a Web Browser and complete the installation:<br>
<br>
<h2>Mysql connection with a socket:</h2><br>
<strong>Important note:</strong> This is the default connection option.<br>
<br>
When you install MySQL you are provided with a <code>socket</code> to connect to the database server. You can find this on the Slot details page for the relevant slot.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/mysqlsocket.png"><br>
<br>
This images shows the hows the fields would be filled out when using a socket.<br>
<br>
<strong>Important note:</strong> Put the socket path in the <code>hostname&#x2F;server</code> field prefixed with a <a href="http://en.wikipedia.org/wiki/Colon_%28punctuation%29">colon :</a> for example:<br>
<br>
<pre><code>:&#x2F;media&#x2F;DiskID&#x2F;home&#x2F;username&#x2F;private&#x2F;mysql&#x2F;socket</code></pre><br>
<strong>Important note:</strong> If you set the <code>mysql.default_sockect</code> and <code>mysqli.default_sockect</code> in this FAQ: <a href="https://www.feralhosting.com/faq/view?question=213">PHP - modify settings</a> you only need to enter <code>localhost</code> as the host to use the socket.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Worpress/socket.png"><br>
<br>
<h2>Mysql connection with networking enabled:</h2><br>
Please see this <a href="https://www.feralhosting.com/faq/view?question=9">FAQ</a> for enabling networking.<br>
<br>
This images shows the hows the fields would be filled out when using networking.<br>
<br>
Where:<br>
<br>
<strong>IP</strong> = Your servers hostname such as <code>server.feralhosting.com</code> or the <a href="https://www.feralhosting.com/faq/view?question=74">IP of your slot</a>.<br>
<br>
<strong>PORT</strong> = Is the port shown when you followed this <a href="https://www.feralhosting.com/faq/view?question=9">FAQ</a> to enable networking in MySQL.<br>
<br>
<strong>Important note:</strong> If you set the <code>mysql.default_port</code> and <code>mysqli.default_port</code> in this FAQ: <a href="https://www.feralhosting.com/faq/view?question=213">PHP - modify settings</a> you only need to enter the hostname or IP without the PORT for a network connection.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Worpress/networking.png"><br>
<br>
