<h1>Plex Requests - Basic Setup</h1>

        
Plex Requests is a new and simple way for users to request new contents for Plex, and automated download requests linking it with <a href="https://www.feralhosting.com/faq/view?question=218">Couchpotato</a>, <a href="https://www.feralhosting.com/faq/view?question=281">Sickrage</a> or <a href="https://www.feralhosting.com/faq/view?question=303">Sonarr</a>. For more informations, please check <a href="http://plexrequests.8bits.ca/">official site</a><br>
<br>
# Installing Meteor<br>
<br>
First, we&#x27;ve to install Meteor with this command :<br>
<br>
<pre><code>curl <a href="https://gist.githubusercontent.com/feralhosting/ed3321cdebf8a59d47a5/raw/979f8b1d042c9ed20d2db0f9705b8a6df4133bdf/meteor.sh">https:&#x2F;&#x2F;gist.githubusercontent.com&#x2F;feralhosting&#x2F;ed3321cdebf8a59d47a5&#x2F;raw&#x2F;979f8b1d042c9ed20d2db0f9705b8a6df4133bdf&#x2F;meteor.sh</a> | sh </code></pre><br>
after we&#x27;ve to check if Meteor is correctly installed, so check it with this command :<br>
<br>
<pre><code>meteor --version </code></pre><br>
and if it has installed correctly you will see this :<br>
<br>
<img src="http://i.imgur.com/y1NZVYF.png"><br>
<br>
Note: If meteor cannot be found, try disconnecting and reconnecting to the host.<br>
<br>
<h2>Installing Plex Requests</h2><br>
<br>
After you&#x27;ve installed Meteor correctly, you can install Plex Requests, so first we clone git repo with this command:<br>
<pre><code>git clone <a href="https://github.com/lokenx/plexrequests-meteor.git">https:&#x2F;&#x2F;github.com&#x2F;lokenx&#x2F;plexrequests-meteor.git</a> ~&#x2F;.plexrequests
cd ~&#x2F;.plexrequests</code></pre><br>
After these two commands, we open a new screen and start Plex Requests with this command :<br>
<pre><code>screen -S plexrequests meteor --port portnumber</code></pre><br>
portnumber should be above 30000 and unique to your setup.<br>
if every is gone well you&#x27;ll see this on your terminal:<br>
<img src="http://i.imgur.com/5K5WVOG.png"><br>
<br>
and now you can press CTRL + A + D on your keyboard to detach screen. And Plex Requests is installed and running on this address : <br>
<br>
<pre><code><a href="http://username.server.feralhosting.com:portnumber">http:&#x2F;&#x2F;username.server.feralhosting.com:portnumber</a></code></pre>
<br>