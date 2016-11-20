<h1>Backing up rutorrent RSS feeds and filters</h1>

        
<br>
You might want to back up your rutorrent RSS feeds and filters in case they get lost or accidentally deleted. While there is no foolproof method of doing this and it may not work between different versions as there is no official &quot;export&quot; button, it is the best way of doing so for rutorrent.<br>
<br>
1) To backup browse to the following directory from your home folder:<br>
<br>
<pre><code>~&#x2F;www&#x2F;username.server.feralhosting.com&#x2F;public_html&#x2F;rutorrent&#x2F;share&#x2F;users&#x2F;username&#x2F;settings&#x2F;rss</code></pre><br>
Replacing <strong>username</strong> with your user and <strong>server</strong> with your Feral server name.<br>
<br>
2) Download the entire contents of this folder including the cache folder.<br>
<br>
3) Save it somewhere safe.<br>
<br>
4) It is now backed up so if you need to restore it just put your saved version back into the same directory.<br>
<br>
<h3>Using SSH</h3><br>
This command will backup all profile folders for rutorrent users to a folder in your private directory. So this will include user based settings and torrent file as well as RSS.<br>
<br>
<pre><code>rsync -avhPS ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;rutorrent&#x2F;share&#x2F;users&#x2F; ~&#x2F;rssbackup</code></pre><br>
You can edit this command however you wish. This is the command broken down into its 3 main parts for easier reading.<br>
<br>
<pre><code>rsync -avhPS</code></pre><br>
The rysnc command itself with options. you can mostly ignore this part.<br>
<br>
<pre><code>~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;rutorrent&#x2F;share&#x2F;users&#x2F;</code></pre><br>
The location of the directory you wish rsync to backup<br>
<br>
<pre><code>~&#x2F;rssbackup&#x2F;</code></pre><br>
the location you wish rysnc to backup the files to (separated by a single space from the previous command)<br>
<br>
