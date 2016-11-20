<h1>Setting up a remote watch directory using CuteFTP and uTorrent</h1>

        
<pre><code>Mac Users that need a RSS download scheduler, check out <a href="http://codingcurious.com/automatic/">[b]Automatic[&#x2F;b]</a></code></pre><br>
<strong>Step 1:</strong><br>
<br>
Install uTorrent. Open preferences with <strong>ctrl + p</strong>. Under <strong>Directories</strong> set <strong>Store .torrents in</strong> to your desired torrent directory (remember this directory for later).<br>
<br>
Under <strong>UI Settings</strong> select <strong>Don&#x27;t Start Download Automatically</strong>.<br>
<br>
<strong>Optional:</strong><br>
<br>
Under <strong>Scheduler</strong> â€” <strong>Enable Scheduler</strong>. Click your mouse and run over all the boxes; repeat this until all boxes are white.<br>
<br>
Refer to <a href="http://www.utorrent.com/documentation/rss/">uTorrent documentation</a> for setting up RSS in uTorrent.<br>
<br>
<strong>Step 2:</strong><br>
<br>
Install CuteFTP Pro and Set up your FTP connection to your Feral box.<br>
<br>
Press <strong>ctrl + F9</strong> to open the <strong>Local Monitor</strong> dialog. Press <strong>Next</strong>.<br>
<br>
<strong>Monitor the following local path</strong> â€” the directory you set uTorrent to save .torrents in.<br>
<br>
<strong>Upload to the following remote path</strong><br>
<br>
<pre><code> &#x2F;home&#x2F;<strong>USERNAME</strong>&#x2F;private&#x2F;rtorrent&#x2F;watch</code></pre><br>
You can substitute above for transmission or any other client that uses watch folders. Click <strong>Next</strong> and leave everything else default.<br>
<br>
With everything set up, uTorrent will download a .torrent from RSS and CuteFTP will see the new .torrent and upload it to your watch directory on your Feral box.<br>
<br>
<strong>CuteFTP Mac Professional does not have a folder monitoring feature (yet), however <a href="http://www.yummysoftware.com/download">[b]Yummy FTP[&#x2F;b]</a> does.</strong><br>
<br>
<strong>Step 1:</strong><br>
<br>
Inside Yummy FTP, connect with your Feral FTP login details.<br>
<br>
<strong>Step 2:</strong><br>
<br>
Navigate to rtorrent&#x27;s or transmission&#x27;s folder, right click on the <strong>watch</strong> folder and click <strong>Save as FTP Watcher</strong><br>
<br>
<strong>Step 3:</strong><br>
<br>
On the Finder dialogue that opens, choose the folder where your torrents are saved automatically and click Save.<br>
<br>
<strong>Step 4:</strong><br>
<br>
Now open a new Finder, navigate to that same folder, look for the <strong>Watcher</strong> file and double click it to start monitoring that folder.<br>
<br>
<br>
---<br>
<strong>Thanks to user fiendskull9 for testing this setup.</strong>
<br>
