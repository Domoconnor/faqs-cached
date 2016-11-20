<h1>Upload a Downloaded Torrent to Another Tracker</h1>

        
<br>
This guide is for people who download data from one tracker and wish to upload it to another tracker, all on their Feral box.<br>
<br>
<strong>Step 1:</strong> Locate your data:<br>
<br>
Delugestores it&#x27;s data in the following folder:<br>
<br>
<pre><code>~&#x2F;private&#x2F;deluge&#x2F;data</code></pre><br>
rTorrent stores it&#x27;s data in the following folder:<br>
<br>
<pre><code>~&#x2F;private&#x2F;rtorrent&#x2F;data</code></pre><br>
Transmission stores it&#x27;s data in the following folder:<br>
<br>
<pre><code>~&#x2F;private&#x2F;tranmission&#x2F;data</code></pre><br>
<strong>Step 2: </strong> When you log in with putty, switch to that folder, by typing:<br>
<br>
For Deluge:<br>
<br>
<pre><code>cd ~&#x2F;private&#x2F;deluge&#x2F;data</code></pre><br>
For rtorrent:<br>
<br>
<pre><code>cd ~&#x2F;private&#x2F;rtorrent&#x2F;data</code></pre><br>
For Transmission:<br>
<br>
<pre><code>cd ~&#x2F;private&#x2F;transmission&#x2F;data</code></pre><br>
<strong>Step 3: </strong> You can view the contents of that folder with the command:<br>
<br>
<pre><code>ls</code></pre><br>
<strong>Step 4: </strong> Once your data is finished downloading, you can then create a new .torrent file using this command:<br>
<br>
<pre><code>mktorrent -l 21 -p -v -a <a href="http://tracker.url">http:&#x2F;&#x2F;tracker.url</a> -o filename.torrent&nbsp; &quot;folder_name&#x2F;&quot;</code></pre><br>
Example:<br>
<br>
(this command is all one line, no matter if it wraps in putty or on here)<br>
<br>
<pre><code>mktorrent -l 21 -p -v -a <a href="http://tracker.what.cd:34000/your_secret_code/announce">http:&#x2F;&#x2F;tracker.what.cd:34000&#x2F;your_secret_code&#x2F;announce</a> -o VA-SomeDanceAlbum.torrent &quot;VA - Some Dance Album&#x2F;&quot;</code></pre><br>
Please substitute things with your corresponding file and folder names. If the folder contains spaces and&#x2F;or special characters like parentheses, use quotes around the name, just like in the example above. You can of course choose any name you want for the .torrent file. I know that What.cd doesn&#x27;t like spaces in the .torrent file name, so I omitted spaces in the example above.<br>
<br>
The command will run and display a summary on in putty when it&#x27;s done. The .torrent file will be in the same folder where you created it, in this case the data folder:<br>
<code>~&#x2F;private&#x2F;rtorrent&#x2F;data</code> or <code>~&#x2F;private&#x2F;transmission&#x2F;data</code><br>
<br>
You can now download the .torrent file with filezilla to your PC, and then upload it to the tracker website. When the tracker generates a new .torrent file, download it to your PC, and load it via the Rutorrent web gui. Or you can upload it to the server with filezilla, and drop it in the watch folder:<br>
<code>~&#x2F;private&#x2F;rtorrent&#x2F;watch</code> or <code>~&#x2F;private&#x2F;tranmission&#x2F;watch</code><br>
<br>
It will automatically load in rtorrent or Transmission, do a hash check, and start seeding to the new tracker.<br>
<br>
