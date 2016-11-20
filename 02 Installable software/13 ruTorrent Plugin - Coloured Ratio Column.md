<h1>ruTorrent Plugin - Coloured Ratio Column</h1>

        
This plugin adds colour to your ruTorrent UI&#x27;s ratio column, changing from red to green (though orange and yellow) as your ratio increases.<br>
<br>
You&#x27;ll need to execute some commands via SSH (secure shell). If you&#x27;ve never used SSH commands the idea of using a terminal window may seem daunting. There is a guide on simply getting connected to your slot through SSH <a href="https://www.feralhosting.com/faq/view?question=12">here</a>. Commands are kept as simple as possible and in most cases will simply need to be copied and pasted into the terminal window (then executed by pressing the <code>Enter</code> key).<br>
<br>
<h2>Installing the Plugin</h2>Whilst logged in via SSH simply execute these commands:<br>
<br>
<pre><code>wget -qO ~&#x2F;ratio.zip <a href="http://git.io/71cumA">http:&#x2F;&#x2F;git.io&#x2F;71cumA</a>
unzip -qo ~&#x2F;ratio.zip -d ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;rutorrent&#x2F;plugins&#x2F;
rm -f ratio.zip
</code></pre><br>
Then simply open ruTorrent (or refresh the page if it was already open) to see the changes.<br>
<br>
