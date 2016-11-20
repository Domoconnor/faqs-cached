<h1>What to do with torrents added to rtorrent - rutorrent are stuck on Pausing</h1>

        
<strong>1. Did you change the data save path?</strong><br>
<br>
If you changed the save path, please be sure that the directory exists.&nbsp; Rutorrent cannot make the directories.<br>
<br>
<strong>2.&nbsp; Stuck on &quot;Pausing&quot; or &quot;Paused&quot; and stopping and restarting doesn&#x27;t help?</strong><br>
<br>
Try using our <a href="http://fiberdk.artemis.feralhosting.com/">torrent fixer</a>.&nbsp; Torrents occasionally contain excess metadata, one of them is the &quot;rtorrent fast resume&quot; metadata.&nbsp; This can cause torrents to go into pausing because rtorrent can&#x27;t find the data for fast resume to work.&nbsp; Our tool removes this and other metadata that isn&#x27;t necessary.&nbsp; <br>
<br>
<strong> 3.&nbsp; Still not starting? </strong><br>
<br>
Please check your disks usage using:<br>
<br>
<pre><code>df -H ~&#x2F;</code></pre><br>
If your disk is &gt;95% full, please ensure that you aren&#x27;t over your quota.&nbsp; If you aren&#x27;t, please open a ticket and we&#x27;ll address any users who are over their quota.<br>
<br>
