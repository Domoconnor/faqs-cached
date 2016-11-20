<h1>ImageMagick - Basic Setup</h1>

        
In SSH do the commands described in this FAQ. If you do not know how to SSH into your slot use this FAQ: <a href="https://www.feralhosting.com/faq/view?question=12">SSH basics - Putty</a><br>
<br>
Your FTP &#x2F; SFTP &#x2F; SSH login information can be found on the Slot Details page for the relevant slot. Use this link in your Account Manager to access the relevant slot:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/slot_detail_link.png"><br>
<br>
You login information for the relevant slot will be shown here:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/slot_detail_ssh.png"><br>
<br>
<h2>Manual installation:</h2><br>
Use these first two commands to create to do some pre requisite tasks:<br>
<br>
<pre><code>mkdir -p ~&#x2F;bin &amp;&amp; bash</code></pre><br>
Install the program using these commands:<br>
<br>
<pre><code>wget -qO ~&#x2F;ImageMagick.tar.gz <a href="http://www.imagemagick.org/download/ImageMagick.tar.gz">http:&#x2F;&#x2F;www.imagemagick.org&#x2F;download&#x2F;ImageMagick.tar.gz</a>
tar xf ~&#x2F;ImageMagick.tar.gz &amp;&amp; cd ~&#x2F;ImageMagick-*
.&#x2F;configure --prefix=$HOME
make &amp;&amp; make install
cd &amp;&amp; rm -rf ImageMagick{.tar.gz,-*}</code></pre><br>
<br>
