<h1>Squid Proxy - Anonymous Forward Proxy Setup</h1>

        
<h2>Squid Proxy - Anonymous Forward Proxy Set-up</h2><br>
Use this article to download and configure Squid as an anonymous web proxy with <code>basic_digest</code> authentication.<br>
<br>
<strong>1:</strong>&nbsp; Create an Auth file that we will use to authenticate the proxy users.<br>
<br>
<strong>Important note:</strong> Using the <code>-c</code> flag will overwrite any existing files with the same name in the specified location. To update use the second command without the <code>-c</code> flag.<br>
<br>
You can change the <code>MyRealm</code> and <code>username</code> arguments to meet your needs:<br>
<br>
<pre><code>htdigest -c ~&#x2F;.squidauth MyRealm username</code></pre><br>
If the file does exists then use this command instead to update or add users:<br>
<br>
<pre><code>htdigest ~&#x2F;.squidauth MyRealm username</code></pre><br>
So for example:<br>
<br>
<pre><code>htdigest -c ~&#x2F;.squidauth NoOrcs bilbobaggins</code></pre><br>
<strong>2:</strong> Install and compile Squid.<br>
<br>
<pre><code>wget -qO ~&#x2F;squid.tar.gz <a href="http://www.squid-cache.org/Versions/v4/squid-4.0.1.tar.gz">http:&#x2F;&#x2F;www.squid-cache.org&#x2F;Versions&#x2F;v4&#x2F;squid-4.0.1.tar.gz</a>
tar xf ~&#x2F;squid.tar.gz &amp;&amp; cd squid-*
.&#x2F;configure --prefix=$HOME
make &amp;&amp; make install &amp;&amp; cd &amp;&amp; rm -rf squid{-*,.tar.gz}</code></pre><br>
<strong>3:</strong> Get the preconfigured conf file that we will have to modify a little.<br>
<br>
<pre><code>wget -qO ~&#x2F;etc&#x2F;squid.conf <a href="http://git.io/yavZuw">http:&#x2F;&#x2F;git.io&#x2F;yavZuw</a></code></pre><br>
<strong>Recommended:</strong> Make some required changes to the conf file with these commands.<br>
<br>
<pre><code>sed -i &quot;s|&#x2F;media&#x2F;DiskID&#x2F;username|$HOME|g&quot; ~&#x2F;etc&#x2F;squid.conf
sed -i &quot;s|http_port 3128|http_port $(shuf -i 10001-32001 -n 1)|g&quot; ~&#x2F;etc&#x2F;squid.conf</code></pre><br>
<strong>4:</strong> Personalise the conf<br>
<br>
Run this command in SSH:<br>
<br>
<pre><code>nano ~&#x2F;etc&#x2F;squid.conf</code></pre><br>
Modify this section only:<br>
<br>
<strong>1:</strong> line <code>61</code> - Change <code>MyRealm</code> to the what was set with the <code>htdigest</code> command in Step 1.<br>
<strong>2:</strong> lines <code>66</code> and <code>67</code> need <code>username</code> to be changed to match the user you created in Step 1 in the <code>~&#x2F;.squidauth</code> file.<br>
<strong>3:</strong> Full paths should already match your slots if you ran the <code>sed</code> command. Otherwise edit them to match your slots full path.<br>
<strong>4:</strong> The port should have been randomised for you&nbsp; if you ran the <code>sed</code> commands so just take not of it. Otherwise change the port to something between <code>10001</code> and <code>32001</code><br>
<br>
<strong>Important note:</strong>&nbsp; The helpers required for authentication are located in <code>~&#x2F;libexec</code>. For example <code>basic_ncsa_auth</code><br>
<br>
<pre><code># And finally deny all other access to this proxy
# Basic Auth Start
# auth_param basic program &#x2F;media&#x2F;DiskID&#x2F;username&#x2F;libexec&#x2F;basic_ncsa_auth &#x2F;media&#x2F;DiskID&#x2F;username&#x2F;.squidbasic
# Basic Auth End
# Digest Auth Start
auth_param digest program &#x2F;media&#x2F;DiskID&#x2F;username&#x2F;libexec&#x2F;digest_file_auth -c &#x2F;media&#x2F;DiskID&#x2F;username&#x2F;.squidauth
auth_param digest children 10
auth_param digest realm MyRealm
# Digest Auth End
acl username proxy_auth REQUIRED
http_access allow username
http_access deny all

# Squid normally listens to port 3128
http_port 3128

# Uncomment and adjust the following to add a disk cache directory.
#cache_dir ufs &#x2F;media&#x2F;DiskID&#x2F;username&#x2F;var&#x2F;cache&#x2F;squid 100 16 256

# Leave coredumps in the first cache dir
coredump_dir &#x2F;media&#x2F;DiskID&#x2F;username&#x2F;var&#x2F;cache&#x2F;squid</code></pre><br>
Then press and hold <code>CTRL</code> and then press <code>x</code> to save. Press <code>y</code> to confirm.<br>
<br>
<h2>Starting Squid:</h2><br>
Start Squid using this command (where USERNAME is replaced by your username):<br>
<br>
<pre><code>~&#x2F;sbin&#x2F;.&#x2F;squid -n USERNAME</code></pre><br>
<h2>Checking it is running:</h2><br>
Use this command to see related if Squid and related processes are running:<br>
<br>
<pre><code>ps x | grep squid | grep -v grep</code></pre><br>
<h2>Connecting to your proxy</h2><br>
You connect to your proxy via the proxy settings of your application.<br>
<br>
<strong>host:</strong> <code>server.feralhosting.com</code><br>
<br>
<strong>Port:</strong> What ever port you set on the conf file. This command will show it to you in SSH:<br>
<br>
<pre><code>cat ~&#x2F;etc&#x2F;squid.conf | grep http_port</code></pre><br>
<strong>Proxy options:</strong> Use this proxy for all connections (if available).<br>
<br>
<a href="https://addons.mozilla.org/en-US/firefox/addon/foxyproxy-standard/">Firefox Foxy Proxy</a><br>
<br>
<a href="https://chrome.google.com/webstore/detail/proxy-switchysharp/dpplabbmogkhghncfbfdeeokoefdjegm">Chrome Proxy SwitchySharp</a><br>
<br>
<h2>Basic Auth instead of Digest:</h2><br>
Here is the format for using digest Auth instead of basic.<br>
<br>
<strong>1:</strong> Create the password file:<br>
<br>
<pre><code>htpasswd -cm ~&#x2F;.squidbasic username</code></pre><br>
If the file already exists then just use:<br>
<br>
<pre><code>htpasswd -m ~&#x2F;.squidbasic username</code></pre><br>
<strong>2:</strong> Now uncomment this in these <code>~&#x2F;etc&#x2F;squid.conf</code>&nbsp; then comment out or remove the Digest Section<br>
<br>
<pre><code># auth_param basic program &#x2F;media&#x2F;DiskID&#x2F;username&#x2F;libexec&#x2F;basic_ncsa_auth &#x2F;media&#x2F;DiskID&#x2F;username&#x2F;.squidbasic</code></pre><br>
<strong>3:</strong> Then restart the Squid server.<br>
<br>