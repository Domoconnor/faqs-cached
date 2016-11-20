<h1>Mosh - Basic Setup</h1>

        
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
Use this command to create the <code>~&#x2F;bin</code> directory and reload your shell for this change to take effect.<br>
<br>
<pre><code>mkdir -p ~&#x2F;bin &amp;&amp; bash</code></pre><br>
<h2>Installation Step 1: Install Protobuf (required dependency)</h2><br>
This is a required dependency that is not included with your slot.<br>
<br>
<pre><code>wget -qO ~&#x2F;protobuf-2.5.0.tar.gz <a href="http://protobuf.googlecode.com/files/protobuf-2.5.0.tar.gz">http:&#x2F;&#x2F;protobuf.googlecode.com&#x2F;files&#x2F;protobuf-2.5.0.tar.gz</a>
tar xf ~&#x2F;protobuf-2.5.0.tar.gz &amp;&amp; cd ~&#x2F;protobuf-2.5.0
.&#x2F;configure --prefix=$HOME &amp;&amp; make &amp;&amp; make install
cd &amp;&amp; rm -rf&nbsp; protobuf{-2.5.0.tar.gz,-2.5.0}</code></pre><br>
<h2>Installation Step 2: Install Mosh</h2><br>
Now download and install <code>mosh</code>:<br>
<br>
<pre><code>wget -qO ~&#x2F;mosh-1.2.4.tar.gz <a href="http://mosh.mit.edu/mosh-1.2.4.tar.gz">http:&#x2F;&#x2F;mosh.mit.edu&#x2F;mosh-1.2.4.tar.gz</a>
tar xf ~&#x2F;mosh-1.2.4.tar.gz &amp;&amp; cd ~&#x2F;mosh-1.2.4
.&#x2F;configure --prefix=$HOME PKG_CONFIG_PATH=$HOME&#x2F;lib&#x2F;pkgconfig LDFLAGS=&quot;--static&quot; 
make
make install
cd &amp;&amp; rm -rf&nbsp; mosh{-1.2.4.tar.gz,-1.2.4}</code></pre><br>
If you get a <code>curses.h</code> error&nbsp; when using <code>make</code> please use open a ticket and ask for this dependency to be installed:<br>
<br>
<pre><code>libncurses5 libncurses5-dev</code></pre><br>
Then run <code>make</code> again and continue from there.<br>
<br>
Connect to your slot using this command.<br>
<br>
For <em>older</em> versions of <code>mosh</code> only:<br>
<br>
<pre><code>mosh username@server.feralhosting.com --server=&quot;LANG=$LANG ~&#x2F;bin&#x2F;mosh-server&quot;</code></pre><br>
For <code>mosh</code> versions 1.2.4 + you only need this command:<br>
<br>
<pre><code>mosh username@server.feralhosting.com --server=~&#x2F;bin&#x2F;mosh-server</code></pre><br>
<h2>Notes</h2><br>
About this error:<br>
<br>
<pre><code>&#x2F;usr&#x2F;bin&#x2F;mosh: Did not find mosh server startup message.</code></pre><br>
If you are getting this is it because you did not use <code>--server=~&#x2F;bin&#x2F;mosh-server&#x27;</code> in your connect command.<br>
<br>
It is possible to add this location to the <code>PATH</code> to simplify the connection but is must be done in a specific way. So we (and the developer) instead recommend you use an alias for connecting, for example:<br>
<br>
<pre><code>alias moshcnct=&#x27;mosh username@server.feralhosting.com --server=~&#x2F;bin&#x2F;mosh-server&#x27;</code></pre><br>
If you must add it to your <code>PATH</code> you will need to:<br>
<br>
1: Add it to your <code>~&#x2F;.bashrc</code> and only this file.<br>
<br>
2: The <code>PATH</code> must be at the top of the file, before any <code>if</code> statements.<br>
<br>
This is what you will need to add:<br>
<br>
<pre><code>PATH=$HOME&#x2F;bin:$PATH</code></pre><br>
Or you can use this command. It will check for the line and if it does not already exist then insert it at line 1. This will fix your issue.<br>
<br>
<pre><code>[ ! &quot;$(grep &#x27;PATH=$HOME&#x2F;bin:$PATH&#x27; ~&#x2F;.bashrc)&quot; ] &amp;&amp; sed -i &#x27;1iPATH=$HOME&#x2F;bin:$PATH&#x27; ~&#x2F;.bashrc</code></pre><br>
<h2>MOSH on your OS:</h2><br>
iOS - <a href="https://itunes.apple.com/us/app/issh-ssh-vnc-console/id287765826">iSSH</a><br>
<br>
Android - <a href="https://play.google.com/store/apps/details?id=com.sonelli.juicessh&#x26;hl=en_GB">JuiceSSH</a><br>
<br>
Windows Cygwin x86 or x64 - <a href="https://www.feralhosting.com/faq/view?question=235">Cygwin - Linux tools on Windows</a><br>
<br>
OS X 10.6 or later - <a href="https://mosh.mit.edu/mosh-1.2.4-3.pkg">https:&#x2F;&#x2F;mosh.mit.edu&#x2F;mosh-1.2.4-3.pkg</a><br>
<br>
