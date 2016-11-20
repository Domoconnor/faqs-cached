<h1>Installing Different Versions of rTorrent and ruTorrent</h1>

        
When you install rTorrent and ruTorrent from the Install Software link you&#x27;re given the latest version that Feral provides. This is currently 0.9.6 in the case of rTorrent and 3.6 for ruTorrent.<br>
<br>
Some trackers will restrict use of certain versions of rTorrent so it&#x27;s handy to have some options. It&#x27;s possible to install and use different versions of both rTorrent and ruTorrent if need be using the instructions in each section below. Whilst your choice of rTorrent is restricted to what is held at Feral it should be possible to install any new version of ruTorrent that&#x27;s released without waiting for staff.<br>
<br>
You&#x27;ll need to execute some commands via SSH (secure shell). If you&#x27;ve never used SSH commands the idea of using a terminal window may seem daunting. There is a guide on simply getting connected to your slot through SSH <a href="https://www.feralhosting.com/faq/view?question=12">here</a>. Commands are kept as simple as possible and in most cases will simply need to be copied and pasted into the terminal window (then executed by pressing the <code>Enter</code> key).<br>
<br>
<br>
<h2>Selecting an rTorrent Version</h2> The list below contains the versions of rTorrent and libtorrent that are available (the number after the _w is the libtorrent version number). The versions followed by a * were released in tandem and so should be preferred. Please note that versions ending in an odd number were classed as development releases so may have stability issues.<br>
<br>
<pre><code>0.9.6_w0.13.6 *
0.9.4_w0.13.4 *
0.9.3_w0.13.3 *
0.9.2_w0.13.2 *
0.9.1_w0.13.1 *
0.9.0_w0.13.0 *
0.8.9_w0.12.9 *
0.8.8_w0.12.9
0.8.8_w0.12.8 *
0.8.7_w0.12.7
0.8.6_w0.12.6 *
0.8.6_w0.12.5
0.8.5_w0.12.6
0.8.5_w0.12.5 *
0.8.4_w0.12.6
0.8.4_w0.12.5
0.8.4_w0.12.4 *
0.8.3_w0.12.6
0.8.3_w0.12.5
0.8.3_w0.12.4
0.8.3_w0.12.3 *
0.8.2_w0.12.6
0.8.2_w0.12.5
0.8.2_w0.12.4
0.8.2_w0.12.3
0.8.2_w0.12.2 *
0.8.1_w0.12.6
0.8.1_w0.12.5
0.8.1_w0.12.4
0.8.1_w0.12.3
0.8.1_w0.12.2
0.8.1_w0.12.1 *
0.8.1_w0.12.0
</code></pre><br>
Older versions of rTorrent might not worky very well with newer versions of ruTorrent so if you wish to use ruTorrent you may find yourself limited in the options you have.<br>
<br>
Install the version and restart rTorrent to activate it as follows:<br>
<br>
<pre><code>echo -n &#x27;<em>version</em>&#x27; &gt; ~&#x2F;private&#x2F;rtorrent&#x2F;.version
pkill -fu &quot;$(whoami)&quot; &#x27;SCREEN -S rtorrent&#x27;
screen -S rtorrent rtorrent
</code></pre><br>
In the first code above replace <em>version</em> with a version number in the previous list.<br>
<br>
You can verify the correct version is running with this command (you should see a process running which contains your chosen version number):<br>
<br>
<pre><code>ps x | grep opt&#x2F;rtorrent | grep -v grep</code></pre><br>
<br>
<h2>Installing a Different Version of ruTorrent</h2> The current version of ruTorrent installed is not the latest so if you wish to take advantage of any new features in the later version you&#x27;ll need to install it manually. Before doing that, please take note of the following:<br>
	<br>
&nbsp; &nbsp; -&nbsp; &nbsp; The instructions assume you want the latest version of ruTorrent. If you want to install an earlier version for some reason you&#x27;ll need to edit the first command to grab an earlier version (or upload it separately via FTP);<br>
		<br>
&nbsp; &nbsp; -&nbsp; &nbsp; The final command will result in your previous ruTorrent instance being removed and replaced. If you want it back you&#x27;d need to reinstall, either using the Install Software link on your manager page or manuall (if the previous version is not installed by the Install Software link);<br>
	<br>
&nbsp; &nbsp; -&nbsp; &nbsp; Custom plugins you previously installed are not copied - this is because you should update them to match the version of ruTorrent you&#x27;re using.<br>
	<br>
To install the latest version please execute the following via SSH:<br>
<br>
<pre><code>cd ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;
git clone <a href="https://github.com/Novik/ruTorrent.git">https:&#x2F;&#x2F;github.com&#x2F;Novik&#x2F;ruTorrent.git</a>
cp -r rutorrent&#x2F;conf&#x2F;* ruTorrent&#x2F;conf&#x2F;
cp rutorrent&#x2F;.ht* ruTorrent&#x2F;
rm -rf rutorrent&#x2F; &amp;&amp; mv ruTorrent&#x2F; rutorrent&#x2F;
</code></pre><br>
<br>
<h2>Troubleshooting</h2><em>When I restart rTorrent I get a message &quot;screen is terminating&quot;</em><br>
Try starting up rTorrent without screen (just type rtorrent and press <code>enter</code>). If you see a message like the following, please double-check you&#x27;ve selected a correct version:<br>
<br>
<pre><code>&#x2F;usr&#x2F;local&#x2F;bin&#x2F;rtorrent: line 24: &#x2F;opt&#x2F;rtorrent&#x2F;version_entered&#x2F;bin&#x2F;rtorrent: No such file or directory</code></pre><br>
<br>

</html>
