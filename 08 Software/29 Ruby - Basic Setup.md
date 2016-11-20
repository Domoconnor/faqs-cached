<h1>Ruby - Basic Setup</h1>

        
<br>
In SSH do the commands described in this FAQ. If you do not know how to SSH into your slot use this FAQ: <a href="https://www.feralhosting.com/faq/view?question=12">SSH basics - Putty</a><br>
<br>
Your FTP &#x2F; SFTP &#x2F; SSH login information can be found on the Slot Details page for the relevant slot.<br>
<br>
Use this link in your Account Manager to access the relevant slot:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/slot_detail_link.png"><br>
<br>
You login information for the relevant slot will be shown here:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/slot_detail_ssh.png"><br>
<br>
<h2>Ruby installation</h2><br>
 <strong>Important note:</strong> Ruby 1.9 is already installed on your slot. Use this command to check the existing version:<br>
<br>
<pre><code>ruby -v</code></pre><br>
<h2>Ruby manual installation</h2><br>
Use this command to create the <code>~&#x2F;bin</code> directory and reload your shell for this change to take effect.<br>
<br>
<pre><code>mkdir -p ~&#x2F;bin &amp;&amp; bash</code></pre><br>
Use these first two commands to create to do some pre requisite tasks:<br>
<br>
First we need a pretty important, but optional, ruby dependency.&nbsp; This lets us have a &quot;history&quot; in our ruby shell.<br>
<br>
<pre><code>wget -qO ~&#x2F;readline.tar.gz <a href="ftp://ftp.cwru.edu/pub/bash/readline-6.3.tar.gz">ftp:&#x2F;&#x2F;ftp.cwru.edu&#x2F;pub&#x2F;bash&#x2F;readline-6.3.tar.gz</a>
tar xf ~&#x2F;readline.tar.gz &amp;&amp; cd readline-6.3
.&#x2F;configure --prefix=$HOME &amp;&amp; make &amp;&amp; make install
cd &amp;&amp; rm -rf readline{.tar.gz,-6.3}</code></pre><br>
Install the program using these commands:<br>
<br>
<pre><code>echo &#x27;gem: --no-document&#x27; &gt; ~&#x2F;.gemrc
wget -qO ~&#x2F;ruby.tar.gz <a href="http://cache.ruby-lang.org/pub/ruby/2.2/ruby-2.2.2.tar.gz">http:&#x2F;&#x2F;cache.ruby-lang.org&#x2F;pub&#x2F;ruby&#x2F;2.2&#x2F;ruby-2.2.2.tar.gz</a>
tar xf ~&#x2F;ruby.tar.gz &amp;&amp; cd ~&#x2F;ruby-2.2.2
.&#x2F;configure --prefix=$HOME --disable-install-doc&nbsp; &amp;&amp; make &amp;&amp; make install
cd &amp;&amp; rm -rf ruby{-2.2.2,.tar.gz}</code></pre><br>
Now these to check your versions:<br>
<br>
<pre><code>ruby -v
gem -v</code></pre><br>
This command to update gems:<br>
<br>
<pre><code>gem update --system</code></pre><br>
<br>
