<h1>How to change torrent clients with active torrents</h1>

        
<h3>Using SSH with PuTTy:</h3><br>
<strong>1:</strong> Login to your server via <a href="https://www.feralhosting.com/faq/view?question=12">SSH</a><br>
<br>
<strong>Important note:</strong> You can pick to either move the files or to copy the files. Both commands are listed below, you do not have to do both.<br>
<br>
Should I move or copy? It is up to you and depends what you are aiming to do. <br>
<br>
<strong>Move</strong> (mv) if you do not plan to use to the old client any more and are permanently moving to another client.<br>
<br>
<strong>Copy</strong> (cp) if you want to still use the client and seed files file you transition into another client. If you have the space to spare.<br>
<br>
<strong>Important note:</strong> Ignore errors about non existing files. It just means there was nothing to move or copy<br>
<br>
<h3>Rutorrent throttle</h3><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/General/Completing%20a%20data%20transfer/rutorrent.png"><br>
<br>
<h3>rtorrent to transmission</h3><br>
<strong>1:</strong> To move (mv) or copy (cp) <code>~&#x2F;private&#x2F;rtorrent&#x2F;data&#x2F;</code> contents:<br>
<br>
<pre><code>mv ~&#x2F;private&#x2F;rtorrent&#x2F;data&#x2F;* ~&#x2F;private&#x2F;transmission&#x2F;data&#x2F;

cp -rf ~&#x2F;private&#x2F;rtorrent&#x2F;data&#x2F;* ~&#x2F;private&#x2F;transmission&#x2F;data&#x2F;</code></pre><br>
<strong>2:</strong> To move (mv) or copy (cp) the <code>~&#x2F;private&#x2F;rtorrent&#x2F;watch</code> contents:<br>
<br>
<pre><code>mv ~&#x2F;private&#x2F;rtorrent&#x2F;watch&#x2F;*.torrent ~&#x2F;private&#x2F;transmission&#x2F;watch&#x2F;

cp -rf ~&#x2F;private&#x2F;rtorrent&#x2F;watch&#x2F;*.torrent ~&#x2F;private&#x2F;transmission&#x2F;watch&#x2F;</code></pre><br>
<strong>3:</strong> To move (mv) or copy (cp) the <code>~&#x2F;private&#x2F;rtorrent&#x2F;work</code> contents:<br>
<br>
<pre><code>mv ~&#x2F;private&#x2F;rtorrent&#x2F;work&#x2F;*.torrent ~&#x2F;private&#x2F;transmission&#x2F;watch&#x2F;

cp -rf ~&#x2F;private&#x2F;rtorrent&#x2F;work&#x2F;*.torrent ~&#x2F;private&#x2F;transmission&#x2F;watch&#x2F;</code></pre><br>
<h3>rtorrent to deluge</h3><br>
<strong>1:</strong> To move (mv) or copy (cp) the <code>~&#x2F;private&#x2F;rtorrent&#x2F;data&#x2F;</code> contents:<br>
<br>
<pre><code>mv ~&#x2F;private&#x2F;rtorrent&#x2F;data&#x2F;* ~&#x2F;private&#x2F;deluge&#x2F;data&#x2F;

cp -rf ~&#x2F;private&#x2F;rtorrent&#x2F;data&#x2F;* ~&#x2F;private&#x2F;deluge&#x2F;data&#x2F;</code></pre><br>
<strong>2:</strong> To move (mv) or copy (cp) the <code>~&#x2F;private&#x2F;rtorrent&#x2F;watch&#x2F;</code> contents:<br>
<br>
<pre><code>mv ~&#x2F;private&#x2F;rtorrent&#x2F;watch&#x2F;*.torrent ~&#x2F;private&#x2F;deluge&#x2F;watch&#x2F;

cp -rf ~&#x2F;private&#x2F;rtorrent&#x2F;watch&#x2F;*.torrent ~&#x2F;private&#x2F;deluge&#x2F;watch&#x2F;</code></pre><br>
<strong>3:</strong> To move (mv) or copy (cp) the <code>~&#x2F;private&#x2F;rtorrent&#x2F;work&#x2F;</code> contents: <br>
<br>
<pre><code>mv ~&#x2F;private&#x2F;rtorrent&#x2F;work&#x2F;*.torrent ~&#x2F;private&#x2F;deluge&#x2F;watch&#x2F;

cp -rf ~&#x2F;private&#x2F;rtorrent&#x2F;work&#x2F;*.torrent ~&#x2F;private&#x2F;deluge&#x2F;watch&#x2F;</code></pre><br>
<h3>Transmission throttle</h3><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/General/Completing%20a%20data%20transfer/transmission 1.png"><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/General/Completing%20a%20data%20transfer/transmission 2.png"><br>
<br>
<h3>transmission to rtorrent</h3><br>
<strong>1:</strong> To move (mv) or copy (cp) the <code>~&#x2F;private&#x2F;transmission&#x2F;data&#x2F;</code> contents:<br>
<br>
<pre><code>mv ~&#x2F;private&#x2F;transmission&#x2F;data&#x2F;* ~&#x2F;private&#x2F;rtorrent&#x2F;data&#x2F;

cp -rf ~&#x2F;private&#x2F;transmission&#x2F;data&#x2F;* ~&#x2F;private&#x2F;rtorrent&#x2F;data&#x2F;</code></pre><br>
<strong>2:</strong> To move (mv) or copy (cp) the <code>~&#x2F;.config&#x2F;transmission-daemon&#x2F;torrents</code> contents:<br>
<br>
<pre><code>mv ~&#x2F;.config&#x2F;transmission-daemon&#x2F;torrents&#x2F;*.torrent ~&#x2F;private&#x2F;rtorrent&#x2F;watch&#x2F;

cp -rf ~&#x2F;.config&#x2F;transmission-daemon&#x2F;torrents&#x2F;*.torrent ~&#x2F;private&#x2F;rtorrent&#x2F;watch</code></pre><br>
<strong>3:</strong> To move (mv) or copy (cp) the <code>~&#x2F;private&#x2F;transmission&#x2F;watch&#x2F;</code> contents:<br>
<br>
<pre><code>mv ~&#x2F;private&#x2F;transmission&#x2F;watch&#x2F;*.torrent ~&#x2F;private&#x2F;rtorrent&#x2F;watch&#x2F;

cp -rf ~&#x2F;private&#x2F;transmission&#x2F;watch&#x2F;*.torrent ~&#x2F;private&#x2F;rtorrent&#x2F;watch&#x2F;</code></pre><br>
<h3>transmission to deluge</h3><br>
<strong>1:</strong> To move (mv) or copy (cp) the <code>~&#x2F;private&#x2F;transmission&#x2F;data&#x2F;</code> contents:<br>
<br>
<pre><code>mv ~&#x2F;private&#x2F;transmission&#x2F;data&#x2F;* ~&#x2F;private&#x2F;deluge&#x2F;data&#x2F;

cp -rf ~&#x2F;private&#x2F;transmission&#x2F;data&#x2F;* ~&#x2F;private&#x2F;deluge&#x2F;data&#x2F;</code></pre><br>
<strong>2:</strong> To move (mv) or copy (cp) the <code>~&#x2F;private&#x2F;transmission&#x2F;watch&#x2F;</code> contents:<br>
<br>
<pre><code>mv ~&#x2F;private&#x2F;transmission&#x2F;watch&#x2F;*.torrent ~&#x2F;private&#x2F;deluge&#x2F;watch&#x2F;

cp -rf ~&#x2F;private&#x2F;transmission&#x2F;watch&#x2F;*.torrent ~&#x2F;private&#x2F;deluge&#x2F;watch&#x2F;</code></pre><br>
<strong>3:</strong> To move (mv) or copy (cp) the <code>~&#x2F;.config&#x2F;transmission-daemon&#x2F;torrents</code> contents:<br>
<br>
<pre><code>mv ~&#x2F;.config&#x2F;transmission-daemon&#x2F;torrents&#x2F;*.torrent ~&#x2F;private&#x2F;deluge&#x2F;watch&#x2F;

cp -rf ~&#x2F;.config&#x2F;transmission-daemon&#x2F;torrents&#x2F;*.torrent ~&#x2F;private&#x2F;deluge&#x2F;watch&#x2F;</code></pre><br>
<h3>Deluge throttle</h3><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/General/Completing%20a%20data%20transfer/deluge.png"><br>
<br>
<h3>deluge to rtorrent</h3><br>
<strong>1:</strong> To move (mv) or copy (cp) the <code>~&#x2F;private&#x2F;deluge&#x2F;data&#x2F;</code> contents:<br>
<br>
<pre><code>mv ~&#x2F;private&#x2F;deluge&#x2F;data&#x2F;* ~&#x2F;private&#x2F;rtorrent&#x2F;data&#x2F;

cp -rf ~&#x2F;private&#x2F;deluge&#x2F;data&#x2F;* ~&#x2F;private&#x2F;rtorrent&#x2F;data&#x2F;</code></pre><br>
<strong>2:</strong> To move (mv) or copy (cp) the <code>~&#x2F;private&#x2F;deluge&#x2F;watch&#x2F;</code> contents:<br>
<br>
<pre><code>mv ~&#x2F;private&#x2F;deluge&#x2F;watch&#x2F;*.torrent ~&#x2F;private&#x2F;rtorrent&#x2F;watch&#x2F;

cp -rf ~&#x2F;private&#x2F;deluge&#x2F;watch&#x2F;*.torrent ~&#x2F;private&#x2F;rtorrent&#x2F;watch&#x2F;</code></pre><br>
<strong>3:</strong> To move (mv) or copy (cp) the <code>~&#x2F;.config&#x2F;deluge&#x2F;state&#x2F;*.torrent</code> contents:<br>
<br>
<pre><code>mv ~&#x2F;.config&#x2F;deluge&#x2F;state&#x2F;*.torrent ~&#x2F;private&#x2F;rtorrent&#x2F;watch&#x2F;

cp -rf ~&#x2F;.config&#x2F;deluge&#x2F;state&#x2F;*.torrent ~&#x2F;private&#x2F;rtorrent&#x2F;watch&#x2F;</code></pre><br>
<h3>deluge to transmission</h3><br>
<strong>1:</strong> To move (mv) or copy (cp) the <code>~&#x2F;private&#x2F;deluge&#x2F;data&#x2F;</code> contents:<br>
<br>
<pre><code>mv ~&#x2F;private&#x2F;deluge&#x2F;data&#x2F;* ~&#x2F;private&#x2F;transmission&#x2F;data&#x2F;

cp -rf ~&#x2F;private&#x2F;deluge&#x2F;data&#x2F;* ~&#x2F;private&#x2F;transmission&#x2F;data&#x2F;</code></pre><br>
<strong>2:</strong> To move (mv) or copy (cp) the <code>~&#x2F;private&#x2F;deluge&#x2F;watch&#x2F;</code> contents:<br>
<br>
<pre><code>mv ~&#x2F;private&#x2F;deluge&#x2F;watch&#x2F;*.torrent ~&#x2F;private&#x2F;transmission&#x2F;watch&#x2F;

cp -rf ~&#x2F;private&#x2F;deluge&#x2F;watch&#x2F;*.torrent ~&#x2F;private&#x2F;transmission&#x2F;watch&#x2F;</code></pre><br>
<strong>3:</strong> To move (mv) or copy (cp) the <code>~&#x2F;.config&#x2F;deluge&#x2F;state&#x2F;*.torrent</code> contents:<br>
<br>
<pre><code>mv ~&#x2F;.config&#x2F;deluge&#x2F;state&#x2F;*.torrent ~&#x2F;private&#x2F;transmission&#x2F;watch&#x2F;

cp -rf ~&#x2F;.config&#x2F;deluge&#x2F;state&#x2F;*.torrent ~&#x2F;private&#x2F;transmission&#x2F;watch&#x2F;</code></pre><br>
<h3>After you have transferred the files</h3><br>
Once completed, simply check out the Web Gui and make sure everything is up and running.<br>
<br>
Then un-throttle your client&#x2F;s.<br>
<br>
<h3>Other:</h3><br>
- If the torrents don&#x27;t automatically begin checking for the material in the new folder, simply right click the torrent and click Verify local data and it should force it to begin.<br>
<br>
