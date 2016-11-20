<h1>SoX - Basic Setup</h1>

        
SoX is a cross-platform (Windows, Linux, MacOS X, etc.) command line utility that can convert various formats of computer audio files in to other formats. It can also apply various effects to these sound files, and, as an added bonus, SoX can play and record audio files on most platforms. <br>
<br>
In SSH do the commands described in this FAQ. If you do not know how to SSH into your slot use this FAQ: <a href="https://www.feralhosting.com/faq/view?question=12">SSH Guide - The Basics</a><br>
<br>
Your FTP &#x2F; SFTP &#x2F; SSH login information can be found on the Slot Details page for the relevant slot. Use this link in your Account Manager to access the relevant slot:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/slot_detail_link.png"><br>
<br>
You login information for the relevant slot will be shown here:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/slot_detail_ssh.png"><br>
<br>
Install SoX<br>
--<br>
<br>
You can <a href="https://www.feralhosting.com/manager/tickets/new">open a ticket</a> ask for SoX to be installed:<br>
<br>
<pre><code>Please can you install the Application: APPLICATION NAME

<a href="https://packages.debian.org/sid/sox">https:&#x2F;&#x2F;packages.debian.org&#x2F;sid&#x2F;sox</a>

apt-get install sox

Reason: So i can use SoX to work with audio files

Thank you.</code></pre><br>
<h2>Install SoX manually and optionally Flac and lame</h2><br>
We need to ask for these to be installed.<br>
<br>
<pre><code>apt-get install libflac-dev libmp3lame-dev libvorbis-dev libmad0-dev</code></pre><br>
You check which dependencies are already installed using these commands:<br>
<br>
 <strong>Important notes:</strong> A result of <code>1</code> Means it is installed and <code>0</code> means it is not:<br>
<br>
<pre><code>dpkg-query -s libflac-dev 2&gt;&amp;1 | grep -c &#x27;ok installed&#x27;
dpkg-query -s libmp3lame-dev 2&gt;&amp;1 | grep -c &#x27;ok installed&#x27;
dpkg-query -s libvorbis-dev 2&gt;&amp;1 | grep -c &#x27;ok installed&#x27;
dpkg-query -s libmad0-dev 2&gt;&amp;1 | grep -c &#x27;ok installed&#x27;</code></pre><br>
Once you have your dependencies required then do this:<br>
<br>
<pre><code>wget -qO ~&#x2F;sox.tar.gz <a href="http://downloads.sourceforge.net/project/sox/sox/14.4.2/sox-14.4.2.tar.gz">http:&#x2F;&#x2F;downloads.sourceforge.net&#x2F;project&#x2F;sox&#x2F;sox&#x2F;14.4.2&#x2F;sox-14.4.2.tar.gz</a>
tar xf ~&#x2F;sox.tar.gz &amp;&amp; cd ~&#x2F;sox-14.4.2
.&#x2F;configure --prefix=$HOME
make &amp;&amp; make install
cd &amp;&amp; rm -rf sox{-14.4.2,.tar.gz}</code></pre><br>
Optional - Install Flac locally:<br>
<br>
<pre><code>wget -qO ~&#x2F;flac.tar.xz <a href="http://downloads.xiph.org/releases/flac/flac-1.3.1.tar.xz">http:&#x2F;&#x2F;downloads.xiph.org&#x2F;releases&#x2F;flac&#x2F;flac-1.3.1.tar.xz</a>
tar xf ~&#x2F;flac.tar.xz &amp;&amp; cd ~&#x2F;flac-1.3.1
.&#x2F;configure --prefix=$HOME
make &amp;&amp; make install
cd &amp;&amp; rm -rf flac{-1.3.1,.tar.xz}</code></pre><br>
Optional - Install Lame locally:<br>
<br>
<pre><code>wget -qO ~&#x2F;lame.tar.gz <a href="http://downloads.sourceforge.net/project/lame/lame/3.99/lame-3.99.5.tar.gz">http:&#x2F;&#x2F;downloads.sourceforge.net&#x2F;project&#x2F;lame&#x2F;lame&#x2F;3.99&#x2F;lame-3.99.5.tar.gz</a>
tar xf ~&#x2F;lame.tar.gz &amp;&amp; cd ~&#x2F;lame-3.99.5
.&#x2F;configure --prefix=$HOME
make &amp;&amp; make install
cd &amp;&amp; rm -rf lame{-3.99.5,.tar.gz}</code></pre><br>
<h2>SoX Documentation</h2><br>
<a href="http://sox.sourceforge.net/Docs/Documentation">http:&#x2F;&#x2F;sox.sourceforge.net&#x2F;Docs&#x2F;Documentation</a>
<br>