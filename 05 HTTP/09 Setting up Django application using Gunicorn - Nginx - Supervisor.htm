<h1>Setting up Django application using Gunicorn - Nginx - Supervisor</h1>

        
There have been several very good detailed tutorials written on the how to set up a Django application(s) using Gunicorn as the application server, Nginx as the proxy server&#x2F;static content web server, and Supervisor to monitor and manage it. <br>
<br>
So I&#x27;ll not spend much time rehashing what those tutorials tell you, but sharing the details of what it took to get it up and running here:<br>
<br>
Most of the tutorials refer to PostgreSQL setups, but <a href="https://www.feralhosting.com/faq/view?question=9">MySQL</a> is already available with your account and supported by Django, and there is sqlite which is included in the base python installation. I chose the later as my database already existed in sqlite.<br>
<br>
The biggest challenge was on the nginx side. All the tutorials reference to setting up a &quot;server&quot;&#x2F;virtual host and making changes within <em>&#x2F;etc&#x2F;nginx&#x2F;sites-available</em> and <em>&#x2F;etc&#x2F;nginx&#x2F;sites-enabled</em>. Those are not accessible for change within a slot. Therefore leverageing <em>location {}</em> was the only option that would work (3+ days of trial and error to find it).<br>
<br>
I created two files in:<br>
<br>
<pre><code>~&#x2F;.nginx&#x2F;conf.d&#x2F;000-default-server.d</code></pre><br>
<h3>static-app.conf</h3><br>
Create a file called:<br>
<br>
<pre><code>~&#x2F;.nginx&#x2F;conf.d&#x2F;000-default-server.d&#x2F;static-app.conf</code></pre><br>
And populate it with this. Edit in your info:<br>
<br>
<pre><code>location &#x2F;static&#x2F; {
alias &#x2F;media&#x2F;DiskID&#x2F;home&#x2F;username&#x2F;www&#x2F;$host&#x2F;public_html&#x2F;webapps&#x2F;static&#x2F;;
}</code></pre><br>
<h3>&lt;app-name&gt;-app.conf</h3><br>
Create a file called, where <em>YourApp</em> is the name of the application:<br>
<br>
<pre><code>~&#x2F;.nginx&#x2F;conf.d&#x2F;000-default-server.d&#x2F;YourApp-app.conf</code></pre><br>
And populate it with this. Edit in your info:<br>
<br>
<pre><code>location &#x2F;&lt;app-name&gt;&#x2F; {

# an HTTP header important enough to have its own Wikipedia entry:
#&nbsp;  <a href="http://en.wikipedia.org/wiki/X-Forwarded-For">http:&#x2F;&#x2F;en.wikipedia.org&#x2F;wiki&#x2F;X-Forwarded-For</a>
proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;

# pass the Host: header from the client right along so redirects
# can be set properly within the Rack application
proxy_set_header Host $http_host;

# we don&#x27;t want nginx trying to do something clever with
# redirects, we set the Host: header above already.
proxy_redirect off;

proxy_pass <a href="http://">http:&#x2F;&#x2F;</a>&lt;internal-ip-address:port&gt;;

}</code></pre><br>
That second file was the key; When you go to your browser and type in:<br>
<br>
<pre><code><a href="http://username.server.feralhosting.com/app-name/">http:&#x2F;&#x2F;username.server.feralhosting.com&#x2F;app-name&#x2F;</a></code></pre><br>
It will proxy&#x2F;redirect the request (including all the parts of the URI from <em>&#x2F;&lt;app-name&gt;&#x2F;....</em> to end). <br>
<br>
The address of <em><a href="http://Internal-IP-address:port">http:&#x2F;&#x2F;Internal-IP-address:port</a></em> is the same bind&#x2F;address that was set-up within Gunicorn.<br>
<br>
To get internal IP address, I was able to use the following command:<br>
<br>
<pre><code>&#x2F;sbin&#x2F;ifconfig |grep -B1 &quot;inet addr&quot; |awk &#x27;{ if ( $1 == &quot;inet&quot; ) { print $2 } else if ( $2 == &quot;Link&quot; ) { printf &quot;%s:&quot; ,$1 } }&#x27; |awk -F: &#x27;{ print $1 &quot;: &quot; $3 }&#x27;</code></pre><br>
The address next to users: is the IP address you want to leverage. <strong>(I&#x27;m assuming it does stay static)</strong><br>
<br>
The purpose of that is to avoid using a public facing IP address like the one associated with &lt;slot&gt;.feralhosting.com which could cause you to expose the application directly to the outside world which can be a security problem for you.<br>
<br>
The last piece of the puzzles that is different from all other set-ups is within the Django area. If you leverage the admin capability of Django, you will need to update the default set-up for <em>urls.py</em> related to admin.<br>
<br>
<pre><code># Uncomment the next line to enable the admin:
# url(r&#x27;^admin&#x2F;&#x27;, include(admin.site.urls)),
url(r&#x27;^&lt;app-name&gt;&#x2F;admin&#x2F;&#x27;, include(admin.site.urls)),</code></pre><br>
This way Django will be expecting a URL starting with <em>app-name&#x2F;admin&#x2F;</em> instead of <em>admin&#x2F;</em>. This will help you with regards to supporting multiple applications and using the different Admin pages for each application separately. <br>
<br>
Everything else basically came from the tutorial provided below, and there are others on the web that provide slight variations of it. But the above items should help with getting things set-up on your slot. <br>
<br>
My next step is to work on creating a script that will handle automating alot of these steps to make sure it gets done correctly each time without forgetting a step. I&#x27;ll share a link to that once completed in case others would like to leverage it.<br>
<br>
Good luck!!!<br>
<br>
<h3>References</h3><br>
<a href="https://www.djangoproject.com/">Django</a><br>
<a href="http://gunicorn.org/">Gunicorn</a><br>
<a href="http://nginx.org/">Nginx</a><br>
<a href="http://supervisord.org/">Supervisor</a><br>
<a href="http://www.virtualenv.org/en/latest/">Virtualenv</a><br>
<a href="http://michal.karzynski.pl/blog/2013/06/09/django-nginx-gunicorn-virtualenv-supervisor/">Setup Tutorial Reference</a><br>
<br>
