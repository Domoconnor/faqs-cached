<h1>How to run FLASK webpages on your slot</h1>

        
What is flask? <a href="http://flask.pocoo.org/">http:&#x2F;&#x2F;flask.pocoo.org&#x2F;</a><br>
<br>
This tutorial will help you to upgrade from Apache to Nginx. Install uWSGI and make a flask test app.<br>
<br>
<strong>Step 1:</strong> Upgrade to nginx: <a href="https://www.feralhosting.com/faq/view?question=231">https:&#x2F;&#x2F;www.feralhosting.com&#x2F;faq&#x2F;view?question=231</a><br>
<br>
<strong>Step 2:</strong> Run the following commands to install Pip, Flask and uWSGI:<br>
<br>
<pre><code>easy_install --user pip
~&#x2F;.local&#x2F;bin&#x2F;pip install --user flask uwsgi</code></pre><br>
<strong>Step 3:</strong> Create file and put the following code into it.<br>
<br>
Create this file: <code>~&#x2F;.nginx&#x2F;conf.d&#x2F;000-default-server.d&#x2F;<strong>uwsgi</strong>.conf</code><br>
<br>
<pre><code>echo -n &#x27;&#x27; &gt; ~&#x2F;.nginx&#x2F;conf.d&#x2F;000-default-server.d&#x2F;<strong>uwsgi</strong>.conf</code></pre><br>
Put the following code into the file:<br>
<br>
<pre><code>location = &#x2F;<strong>foo</strong> { rewrite ^ &#x2F;<strong>foo</strong>&#x2F;; }
location &#x2F;<strong>foo</strong> { try_files $uri @theapp; }
location @theapp {
&nbsp;  include &#x2F;etc&#x2F;nginx&#x2F;uwsgi_params;
&nbsp;  uwsgi_param SCRIPT_NAME &#x2F;<strong>foo</strong>;
&nbsp;  uwsgi_modifier1 30;
&nbsp;  uwsgi_pass unix:&#x2F;media&#x2F;<strong>&lt;your diskname&gt;</strong>&#x2F;home&#x2F;<strong>&lt;your username&gt;</strong>&#x2F;<strong>foo</strong>.sock;
}</code></pre><br>
Remember to put in your username and change from <code>foo</code> to your projectname<br>
<br>
Restart the nginx server:<br>
<br>
<pre><code>&#x2F;usr&#x2F;sbin&#x2F;nginx -s reload -c ~&#x2F;.nginx&#x2F;nginx.conf</code></pre><br>
<strong>Step 4:</strong> Make uWSGI start automatically each time the server boots.<br>
<br>
Run the following code in the terminal:<br>
<br>
<pre><code>crontab -e</code></pre><br>
This will open up or create your Crontab config file. Now add this line:<br>
<br>
<pre><code>@reboot uwsgi --socket &#x2F;media&#x2F;<strong>&lt;your diskname&gt;</strong>&#x2F;home&#x2F;<strong>&lt;your username&gt;</strong>&#x2F;<strong>foo</strong>.sock --wsgi-file &#x2F;media&#x2F;<strong>&lt;your diskname&gt;</strong>&#x2F;home&#x2F;<strong>&lt;your username&gt;</strong>&#x2F;<strong>foo</strong>&#x2F;<strong>main.py</strong> --master --processes 4 --threads 0 --enable-threads --callable app --daemonize2 &#x2F;media&#x2F;<strong>&lt;your diskname&gt;</strong>&#x2F;home&#x2F;<strong>&lt;your username&gt;</strong>&#x2F;.nginx&#x2F;uwscgi.log</code></pre><br>
Then run the following code to start it instantly:<br>
<br>
<pre><code>uwsgi --socket &#x2F;media&#x2F;<strong>&lt;your diskname&gt;</strong>&#x2F;home&#x2F;<strong>&lt;your username&gt;</strong>&#x2F;<strong>foo</strong>.sock --wsgi-file &#x2F;media&#x2F;<strong>&lt;your diskname&gt;</strong>&#x2F;home&#x2F;<strong>&lt;your username&gt;</strong>&#x2F;<strong>foo</strong>&#x2F;<strong>main.py</strong> --master --processes 4 --threads 0 --enable-threads --callable app --daemonize2 &#x2F;media&#x2F;<strong>&lt;your diskname&gt;</strong>&#x2F;home&#x2F;<strong>&lt;your username&gt;</strong>&#x2F;.nginx&#x2F;uwscgi.log</code></pre><br>
<strong>Step 5:</strong> Make the flask project testfile.<br>
<br>
Create this file (mentioned in step4): <code>&#x2F;media&#x2F;<strong>&lt;your diskname&gt;</strong>&#x2F;home&#x2F;<strong>&lt;your username&gt;</strong>&#x2F;<strong>foo</strong>&#x2F;<strong>main.py</strong></code> then put in the following flask code (python):<br>
<br>
<pre><code>#!&#x2F;usr&#x2F;bin&#x2F;env python2
from flask import Flask
app = Flask(__name__)

@app.route(&quot;&#x2F;&quot;)
def hello():
&nbsp; return &quot;Hello World!&quot;

if __name__ == &quot;__main__&quot;:
&nbsp; app.run()</code></pre><br>
<strong>Step 5:</strong> Open your favorite browser and go to <code><a href="http://">http:&#x2F;&#x2F;</a><strong>&lt;your username&gt;</strong>.gaia.feralhosting.com&#x2F;<strong>foo&#x2F;</strong></code><br>
<br>
<strong>IRC help:</strong><br>
<br>
Questions regarding your slot: #Feral @ irc.what-network.net<br>
Questions regarding Flask: #Pocoo @ Freenode<br>
Questions regarding uWSGI: #uWSGI @ Freenode<br>
Questions regarding nginx: #nginx @ Freenode<br>
<br>
