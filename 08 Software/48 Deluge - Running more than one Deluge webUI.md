<h1>Deluge - Running more than one Deluge webUI</h1>

        
Start off by following this FAQ on <a href="https://www.feralhosting.com/faq/view?question=197">running more than one instance of Deluge</a>.<br>
<br>
Shell into your slot and go into your new deluge directory and edit the web.conf file<br>
<br>
<pre><code>cd ~&#x2F;.config&#x2F;deluge2 &amp;&amp; nano web.conf</code></pre><br>
Near the top, around 5 lines down you will see &quot;port&quot; and then 5 numbers. This is the port that your current Deluge webUI is running on. Pick another random 5 digit number between <em>10000 - 50000</em> and put that in here. Make sure you remember what it was too as you will need it in a minute. Once you have done this, go further down the file until you see the configuration option &quot;base&quot;. This will look like &quot;&#x2F;username&#x2F;deluge&#x2F;&quot; change this to &quot;&#x2F;&quot;. Once you are done, hold <em>Ctrl+O</em>, then enter to save. Then <em>Ctrl+X</em> to exit. <br>
<br>
Next, we will start the new webUI. To do this, simply run the following:<br>
<br>
<pre><code>deluge-web -c ~&#x2F;.config&#x2F;deluge2 --fork</code></pre><br>
To ensure that the second webUI restarts when the server does, you will want to add it do the cron, so:<br>
<br>
<pre><code>crontab -e</code></pre><br>
Paste the following in exactly, at the bottom<br>
<br>
<pre><code>@reboot &#x2F;usr&#x2F;local&#x2F;bin&#x2F;deluge-web -c ${HOME}&#x2F;.config&#x2F;deluge2</code></pre><br>
You should now be able to access the secondary webUI on:<br>
<br>
<pre><code>username.servername.feralhosting.com:PORT_YOU_CHOSE_EARLIER</code></pre><br>
You can now add the deluge daemon connection using the information returned in <a href="https://www.feralhosting.com/faq/view?question=197">running more than one instance of Deluge</a> article under &quot;Retrieve important information&quot;<br>
<br>
