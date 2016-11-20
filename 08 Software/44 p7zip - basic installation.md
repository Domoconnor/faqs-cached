<h1>p7zip - basic installation</h1>

        
<br>
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
You can ask for this to be installed on your slot by opening a ticket.<br>
<br>
<h2>Download and unpack pz7ip</h2><br>
Download the binaries and extract them using these commands:<br>
<br>
<pre><code>wget -qO ~&#x2F;p7zip.tar.bz2 <a href="http://sourceforge.net/projects/p7zip/files/p7zip/9.38.1/p7zip_9.38.1_src_all.tar.bz2">http:&#x2F;&#x2F;sourceforge.net&#x2F;projects&#x2F;p7zip&#x2F;files&#x2F;p7zip&#x2F;9.38.1&#x2F;p7zip_9.38.1_src_all.tar.bz2</a>
tar xf ~&#x2F;p7zip.tar.bz2 &amp;&amp; cd ~&#x2F;p7zip_9.38.1
make &amp;&amp; make install DEST_HOME=$HOME
cd &amp;&amp; rm -f ~&#x2F;p7zip.tar.bz2</code></pre><br>
<h2>Using p7zip</h2><br>
Now you can use the binary by using this command:<br>
<br>
<pre><code>~&#x2F;bin&#x2F;7za</code></pre><br>
For example how to extract an iso:<br>
<br>
<pre><code>~&#x2F;bin&#x2F;7za x ~&#x2F;Your.iso -oWhere&#x2F;You&#x2F;Want&#x2F;It&#x2F;Extracted&#x2F;To</code></pre><br>
<code>-o</code> cannot use <code>~</code> in the path or have a space after it. It must be relative from you are in the shell.<br>
<br>
