<h1>ruTorrent Plugin - Screenshots</h1>

        
You&#x27;ll need to execute some commands via SSH (secure shell). If you&#x27;ve never used SSH commands the idea of using a terminal window may seem daunting. There is a guide on simply getting connected to your slot through SSH <a href="https://www.feralhosting.com/faq/view?question=12">here</a>. Commands are kept as simple as possible and in most cases will simply need to be copied and pasted into the terminal window (then executed by pressing the <code>Enter</code> key).<br>
<br>
<h2>Installing ffmpeg</h2>The plugin uses ffmpeg to generate screenshots and due to the removal of this software from Debian stable you&#x27;ll need to install it to your slot instead. This is easily done by executing the following commands:<br>
<br>
<pre><code>mkdir -p ~&#x2F;bin &amp;&amp; bash
wget -qO ~&#x2F;ffmpeg.tar.gz <a href="http://johnvansickle.com/ffmpeg/releases/ffmpeg-release-64bit-static.tar.xz">http:&#x2F;&#x2F;johnvansickle.com&#x2F;ffmpeg&#x2F;releases&#x2F;ffmpeg-release-64bit-static.tar.xz</a>
tar xf ~&#x2F;ffmpeg.tar.gz 
rm -rf ffmpeg-*-64bit-static&#x2F;{manpages,presets,readme.txt}
cp ~&#x2F;ffmpeg-*-64bit-static&#x2F;* ~&#x2F;bin
chmod 700 ~&#x2F;bin&#x2F;{ffmpeg,ffprobe,ffmpeg-10bit,qt-faststart}
rm -rf ffmpeg{.tar.gz,-*-64bit-static}
</code></pre><br>
<br>
<h2>Installing Screenshots</h2>If you&#x27;re using 3.6 of ruTorrent (which is the default version installed here at Feral) you won&#x27;t be able to use the general plugin install method described on <a href="https://www.feralhosting.com/faq/view?question=282">this page</a>. Instead, execute these commands:<br>
<br>
<pre><code>rm -rf ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;rutorrent&#x2F;plugins&#x2F;screenshots
wget -q <a href="https://bintray.com/artifact/download/novik65/generic/plugins/screenshots-3.6.tar.gz">https:&#x2F;&#x2F;bintray.com&#x2F;artifact&#x2F;download&#x2F;novik65&#x2F;generic&#x2F;plugins&#x2F;screenshots-3.6.tar.gz</a>
tar xf screenshots-3.6.tar.gz -C ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;rutorrent&#x2F;plugins&#x2F;
rm screenshots-3.6.tar.gz
</code></pre><br>
The first command removes any existing instance of screenshots in case you previously installed an incorrect version. Naturally if you are using the 3.7 version of ruTorrent then you can install Screenshots by following the general plugin install method.<br>
<br>
<br>
<h2>Configuring screenshots</h2>To make sure your version of ffmpeg is used we need to amend the screenshot plugin&#x27;s config file. This can be done simply by executing this command:<br>
<br>
<pre><code>cd &amp;&amp; sed -i &quot;s|ffmpeg&#x27;] = &#x27;&#x27;|ffmpeg&#x27;] = &#x27;$(pwd)&#x2F;bin&#x2F;ffmpeg&#x27;|g&quot; ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;rutorrent&#x2F;plugins&#x2F;screenshots&#x2F;conf.php</code></pre><br>
As with all plugins, you&#x27;ll need to refresh ruTorrent if it&#x27;s open in a browser to get any changes recognised.<br>
<br>
<br>
<h2>Troubleshooting</h2><em>When I load ruTorrent I get an error &quot;screenshots: Plugin will not work. rTorrent user can&#x27;t access external program (ffmpeg)&quot;</em><br>
Make sure you&#x27;ve configured screenshots to point to the instance of ffmpeg running on your slot. If in doubt, follow this guide from top to bottom again and refresh ruTorrent.<br>
<br>
<em>When I generate screenshots I get no pictures, just a list of numbers</em><br>
That happens when using the 3.7 version of screenshots with the 3.6 version of ruTorrent. Please install the 3.6 version using the instructions above.<br>
<br>
