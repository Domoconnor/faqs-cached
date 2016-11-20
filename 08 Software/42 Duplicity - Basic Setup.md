<h1>Duplicity -  Basic Setup</h1>

        
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
<h2>What is Duplicity?</h2><br>
<a href="http://duplicity.nongnu.org/">duplicity</a>: Encrypted bandwidth-efficient backup using the rsync algorithm<br>
<br>
Duplicity backs directories by producing encrypted tar-format volumes and uploading them to a remote or local file server. Because duplicity uses librsync, the incremental archives are space efficient and only record the parts of files that have changed since the last backup. Because duplicity uses GnuPG to encrypt and&#x2F;or sign these archives, they will be safe from spying and&#x2F;or modification by the server.<br>
<br>
<h2>Installation</h2><br>
In SSH do the commands described in this FAQ. If you do not know how to SSH into your slot use this FAQ: <a href="https://www.feralhosting.com/faq/view?question=12">SSH basics - Putty</a><br>
<br>
1: Do these preparation steps:<br>
<br>
<pre><code>mkdir -p ~&#x2F;bin &amp;&amp; bash
[ ! &quot;$(grep &#x27;~&#x2F;.local&#x2F;bin&#x27; ~&#x2F;.bashrc)&quot; ] &amp;&amp; echo &#x27;export PATH=~&#x2F;.local&#x2F;bin:$PATH&#x27; &gt;&gt; ~&#x2F;.bashrc ; source ~&#x2F;.bashrc</code></pre><br>
2: Install librsync<br>
<br>
<pre><code>wget -qO ~&#x2F;librsync.tar.gz <a href="http://downloads.sourceforge.net/project/librsync/librsync/0.9.7/librsync-0.9.7.tar.gz">http:&#x2F;&#x2F;downloads.sourceforge.net&#x2F;project&#x2F;librsync&#x2F;librsync&#x2F;0.9.7&#x2F;librsync-0.9.7.tar.gz</a>
tar xf ~&#x2F;librsync.tar.gz &amp;&amp; cd ~&#x2F;librsync-0.9.7
.&#x2F;configure --prefix=$HOME --with-pic &amp;&amp; make &amp;&amp; make install
cd &amp;&amp; rm -rf librsync{-0.9.7,.tar.gz}</code></pre><br>
3: Install Duplicity<br>
<br>
<pre><code>wget -qO ~&#x2F;duplicity.tar.gz <a href="https://launchpad.net/duplicity/0.6-series/0.6.24/&#x2B;download/duplicity-0.6.24.tar.gz">https:&#x2F;&#x2F;launchpad.net&#x2F;duplicity&#x2F;0.6-series&#x2F;0.6.24&#x2F;+download&#x2F;duplicity-0.6.24.tar.gz</a>
tar xf ~&#x2F;duplicity.tar.gz &amp;&amp; cd ~&#x2F;duplicity-0.6.24
python setup.py install --prefix=$HOME&#x2F;.local --librsync-dir=$HOME
cd &amp;&amp; rm -rf duplicity{-0.6.24,.tar.gz}</code></pre><br>
Check it was installed correctly.<br>
<br>
<pre><code>duplicity --version
duplicity --help</code></pre><br>
<br>
