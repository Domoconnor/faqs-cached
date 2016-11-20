<h1>Uninstalling software</h1>

        
So you&#x27;ve tried several torrent clients and now you feel you&#x27;d like to stop using some of them. If you are concerned about system resources, do not worry: if you do not actively use a client, it consumes almost no resources, even if it remains running. Simply clear out any data in the client and leave it be.<br>
<br>
Though sometimes you really may not want your client to run any longer, for instance, you switched to another for good. If you kill the process, it will just restart again as this is by design. We want your programs to run all the time for you. <br>
<br>
To make a client stop loading automatically after being killed, simply <a href="https://www.feralhosting.com/faq/view?question=12">SSH</a> into your slot, and create a special file in the client&#x27;s folder. Then kill its process. Please check the FAQ for each client on how to kill it.<br>
<br>
For <a href="https://www.feralhosting.com/faq/view?question=2">rtorrent</a>, please execute this command: <br>
<br>
<pre><code>touch ~&#x2F;private&#x2F;rtorrent&#x2F;.prevent-restart</code></pre><br>
For <a href="https://www.feralhosting.com/faq/view?question=4">transmission</a>: <br>
<br>
<pre><code>touch ~&#x2F;private&#x2F;transmission&#x2F;.prevent-restart</code></pre><br>
For <a href="https://www.feralhosting.com/faq/view?question=62">deluge</a>: <br>
<br>
<pre><code>touch ~&#x2F;private&#x2F;deluge&#x2F;.prevent-restart</code></pre><br>
For <a href="https://www.feralhosting.com/faq/view?question=9">MySQL</a>: <br>
<br>
<pre><code>touch ~&#x2F;private&#x2F;mysql&#x2F;.prevent-restart</code></pre><br>
With the <code>.prevent-restart</code> file in place, the client will not be started automatically. If you change your mind in the future, just remove the file from the corresponding folder. Remember, it is a .dot file or hidden, so it may seem like it&#x27;s not there in your FTP or SFTP client; make sure you tell it to display hidden files and folders. In the shell, use the <code>ls -a</code> command to see it listed and <code>rm</code> command to remove it. After removing the special file, the client will be automatically restarted for you. <br>
<br>
But wait! You say that the very sight of the program&#x27;s folder offends you? Just remove the folder for the client from the <code>~&#x2F;private</code> directory, and don&#x27;t forget the webui from the <code>public_html</code> directory and the program is gone. All that will remain is the login information on your <a href="https://www.feralhosting.com/manager/">Slot Detail</a> page for the relevant slot as we can&#x27;t do much about that part, without going into a lengthy explanation. You can always change your mind later and issue a re-install from the <a href="https://www.feralhosting.com/manager/">[b]Install Software[&#x2F;b] link in your manager</a>.<br>
<br>
