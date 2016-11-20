<h1>etherpad-lite</h1>

        
Etherpad is a highly customizable Open Source online editor providing collaborative editing in really real-time.<br>
<br>
<h2>etherpad-lite install</h2><br>
Prerequisites of using etherpad-lite<br>
<br>
1: You will need to have updated to <a href="https://www.feralhosting.com/faq/view?question=231">nginx</a><br>
<br>
2: You have installed <a href="https://www.feralhosting.com/faq/view?question=199">node.js</a><br>
<br>
Once you have done these two thing then you can install and use Ghost.<br>
<br>
<h2>Installation:</h2><br>
<pre><code>npm install sqlite3
git clone <a href="https://github.com/ether/etherpad-lite.git">https:&#x2F;&#x2F;github.com&#x2F;ether&#x2F;etherpad-lite.git</a></code></pre><br>
<pre><code>cp -f ~&#x2F;etherpad-lite&#x2F;settings.json.template ~&#x2F;etherpad-lite&#x2F;settings.json</code></pre><br>
Now edit this file:<br>
<br>
<pre><code>nano -w ~&#x2F;etherpad-lite&#x2F;settings.json</code></pre><br>
Find and make these changes:<br>
<br>
<strong>1:</strong><br>
<br>
<pre><code>&#x2F;&#x2F;IP and port which etherpad should bind at
&quot;ip&quot;: &quot;0.0.0.0&quot;,
&quot;port&quot; : 9001,</code></pre><br>
Change the port. Anything between <code>6000</code> to <code>50000</code><br>
<br>
<pre><code>&#x2F;&#x2F;IP and port which etherpad should bind at
&quot;ip&quot;: &quot;0.0.0.0&quot;,
&quot;port&quot; : 12874,</code></pre><br>
<strong>2:</strong><br>
<br>
<pre><code>&quot;sessionKey&quot; : &quot;&quot;,</code></pre><br>
Add a session key. Just generate some letters and numbers.<br>
<br>
<pre><code>&quot;sessionKey&quot; : &quot;NGTpvziaR5SZQ2jqd7Vf&quot;,</code></pre><br>
<strong>3:</strong><br>
<br>
<pre><code>&quot;dbType&quot; : &quot;dirty&quot;,
&#x2F;&#x2F;the database specific settings
&quot;dbSettings&quot; : {
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  &quot;filename&quot; : &quot;var&#x2F;dirty.db&quot;
&nbsp; &nbsp; &nbsp; &nbsp;  },</code></pre><br>
Change the database settings. I use sqlite3, but you can use redis:<br>
<br>
<pre><code>&quot;dbType&quot; : &quot;sqlite&quot;,
&#x2F;&#x2F;the database specific settings
&quot;dbSettings&quot; : {
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  &quot;filename&quot; : &quot;var&#x2F;sqlite.db&quot;
&nbsp; &nbsp; &nbsp; &nbsp;  },</code></pre><br>
<strong>4:</strong><br>
<br>
<pre><code>&nbsp; &#x2F;*
&nbsp; &quot;users&quot;: {
&quot;admin&quot;: {
&nbsp; &quot;password&quot;: &quot;changeme1&quot;,
&nbsp; &quot;is_admin&quot;: true
},
&quot;user&quot;: {
&nbsp; &quot;password&quot;: &quot;changeme1&quot;,
&nbsp; &quot;is_admin&quot;: false
}
&nbsp; },
&nbsp; *&#x2F;</code></pre><br>
Uncomment this section and change the passwords:<br>
<br>
<pre><code>&nbsp; &quot;users&quot;: {
&quot;admin&quot;: {
&nbsp; &quot;password&quot;: &quot;fwe5235f3&quot;,
&nbsp; &quot;is_admin&quot;: true
},
&quot;user&quot;: {
&nbsp; &quot;password&quot;: &quot;EGFSD215TF&quot;,
&nbsp; &quot;is_admin&quot;: false
}
&nbsp; },</code></pre><br>
Start etherpad<br>
<br>
<pre><code>screen -S etherpad ~&#x2F;etherpad-lite&#x2F;bin&#x2F;run.sh</code></pre><br>
If all goes well then press and hold <code>CTRL</code> and <code>a</code> then press <code>d</code> to detach from the screen. This leaves it running in the background.<br>
<br>
<h2>Update etherpad</h2><br>
<pre><code>screen -r etherpad</code></pre><br>
Then press and hold <code>CTRL</code> and then press <code>c</code> to quit.<br>
<br>
<pre><code>cd ~&#x2F;etherpad-lite
git pull origin
screen -dmS etherpad ~&#x2F;etherpad-lite&#x2F;bin&#x2F;run.sh
cd</code></pre><br>
<h3>Optional </h3><br>
<strong>Apache</strong><br>
<br>
To use https you create your own certs, then uncomment the relevant section in the <code>settings.json</code>. Then add the relative paths to your certs.<br>
<br>
<pre><code>mkdir -p ~&#x2F;etherpad-lite&#x2F;ssl
openssl req -new -x509 -nodes -days 365 -subj &#x27;&#x2F;C=GB&#x2F;ST=none&#x2F;L=none&#x2F;CN=none&#x27; -newkey rsa:2048 -keyout ~&#x2F;etherpad-lite&#x2F;ssl&#x2F;etherpad.key.pem -out ~&#x2F;etherpad-lite&#x2F;ssl&#x2F;etherpad.cert.pem</code></pre><br>
<br>
<pre><code>&nbsp; &#x2F;*&nbsp; 
&nbsp; &#x2F;&#x2F; Node native SSL support
&nbsp; &#x2F;&#x2F; this is disabled by default
&nbsp; &#x2F;&#x2F;
&nbsp; &#x2F;&#x2F; make sure to have the minimum and correct file access permissions set
&nbsp; &#x2F;&#x2F; so that the Etherpad server can access them

&nbsp; &quot;ssl&quot; : {
&nbsp; &nbsp; &nbsp; &nbsp; &quot;key&quot;&nbsp; : &quot;&#x2F;path-to-your&#x2F;epl-server.key&quot;,
&nbsp; &nbsp; &nbsp; &nbsp; &quot;cert&quot; : &quot;&#x2F;path-to-your&#x2F;epl-server.crt&quot;
&nbsp; &nbsp; &nbsp; },

&nbsp; *&#x2F;</code></pre><br>
Becomes:<br>
<br>
<pre><code>&nbsp; &#x2F;&#x2F; Node native SSL support
&nbsp; &#x2F;&#x2F; this is disabled by default
&nbsp; &#x2F;&#x2F;
&nbsp; &#x2F;&#x2F; make sure to have the minimum and correct file access permissions set
&nbsp; &#x2F;&#x2F; so that the Etherpad server can access them

&nbsp; &quot;ssl&quot; : {
&nbsp; &nbsp; &nbsp; &nbsp; &quot;key&quot;&nbsp; : &quot;ssl&#x2F;etherpad.key.pem&quot;,
&nbsp; &nbsp; &nbsp; &nbsp; &quot;cert&quot; : &quot;ssl&#x2F;etherpad.cert.pem&quot;
&nbsp; &nbsp; &nbsp; },</code></pre><br>
<strong>Nginx</strong><br>
<br>
In ngnix we can use proxypass to work with the existing and valid SSL URL format. These two lines must be edited in the template conf below:<br>
<br>
<pre><code>rewrite ^&#x2F;ether$ <a href="https://">https:&#x2F;&#x2F;</a>$http_x_host&#x2F;username&#x2F;ether&#x2F; permanent;
proxy_pass <a href="http://10.0.0.1:PORT/username/ether/&#x3B;">http:&#x2F;&#x2F;10.0.0.1:PORT&#x2F;username&#x2F;ether&#x2F;;</a></code></pre><br>
Change the <code>username</code> in two places and <code>PORT</code> in one, to match yours. Where <code>username</code> if your Feral username and the port is the same port configured in the <code>~&#x2F;etherpad-lite&#x2F;settings.json</code><br>
<br>
<pre><code>location &#x2F;ether {
proxy_set_header&nbsp; &nbsp; &nbsp; &nbsp; Host&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; $http_x_host;
proxy_set_header&nbsp; &nbsp; &nbsp; &nbsp; X-Real-IP&nbsp; &nbsp; &nbsp;  $remote_addr;
proxy_set_header&nbsp; &nbsp; &nbsp; &nbsp; X-Forwarded-For $proxy_add_x_forwarded_for;
rewrite ^&#x2F;ether$ <a href="https://">https:&#x2F;&#x2F;</a>$http_x_host&#x2F;username&#x2F;ether&#x2F; permanent;
rewrite &#x2F;ether&#x2F;(.*) &#x2F;$1 break;
proxy_pass <a href="http://10.0.0.1:PORT/username/ether/&#x3B;">http:&#x2F;&#x2F;10.0.0.1:PORT&#x2F;username&#x2F;ether&#x2F;;</a>
proxy_redirect &#x2F; &#x2F;ether&#x2F;;
proxy_redirect off;
proxy_buffering off;
}</code></pre><br>
Once you have saved this file use this command to reload nginx:<br>
<br>
<pre><code>&#x2F;usr&#x2F;sbin&#x2F;nginx -s reload -c ~&#x2F;.nginx&#x2F;nginx.conf</code></pre><br>
<strong>Admin</strong><br>
<br>
<pre><code><a href="https://server.feralhosting.com/username/ether/admin/plugins">https:&#x2F;&#x2F;server.feralhosting.com&#x2F;username&#x2F;ether&#x2F;admin&#x2F;plugins</a></code></pre>
<br>