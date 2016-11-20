<h1>SSH tunnelled browser on your Android phone</h1>

        
Android users probably know that setting up SSH tunnels on non-rooted Android phones is a pain in the ass and more trouble than it is worth. I&#x27;ve found a relatively simple method that allows you to secure your browsing. A few notes before we start:<br>
<br>
a) You cannot setup an all-encompassing SSH tunnel without rooting your phone. This guide explains how to configure a browser (Firefox) to use your SSH session opened with a free app (ConnectBot) without incurring the risk of rooting. This will only protect your browsing.<br>
<br>
b) If you already have a rooted phone, there are easier ways of getting this done. Google it up.<br>
<br>
Here are the steps.<br>
<br>
1: Install Firefox <br>
<br>
<pre><code><a href="https://play.google.com/store/apps/details?id=org.mozilla.firefox">https:&#x2F;&#x2F;play.google.com&#x2F;store&#x2F;apps&#x2F;details?id=org.mozilla.firefox</a></code></pre><br>
2: Install ConnectBot <br>
<br>
<a href="http://michaelchelen.net/articles/android-connectbot-ssh-key-auth-howto.html">Set up Connect Bot private&#x2F;public keys</a><br>
<br>
<pre><code><a href="https://play.google.com/store/apps/details?id=org.connectbot">https:&#x2F;&#x2F;play.google.com&#x2F;store&#x2F;apps&#x2F;details?id=org.connectbot</a></code></pre><br>
3: Login into your server through ConnectBot. Press your menu button and access Port Forwards. Setup a port forward with a destination of 127.0.0.1 (localhost doesn&#x27;t seem to work) and with a higher port than normal, as you are running without root, and most ports are restricted. A good number is 9000-10000.<br>
<br>
4: Open Firefox, and type <em>about:config</em> into the destination bar. Access and modify the following properties:<br>
<br>
<pre><code>network.proxy.socks = 127.0.0.1
network.proxy.socks_port = &lt;whatever port you chose&gt;
network.proxy.type = 1
network.proxy.socks_remote_dns = â€œtrueâ€  (press toggle to change the value)</code></pre><br>
5: Restart Firefox, and open any IP identifying website (<a href="http://www.whatismyip.com/">http:&#x2F;&#x2F;www.whatismyip.com&#x2F;</a> for instance). If all is correct, you should see your server IP instead of whatever your phone is using. Congrats.<br>
<br>
