<h1>Git - How to Install</h1>

        
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
<h2>Git 1.7.10.4</h2><br>
This command will show you your installed Git version<br>
<br>
<pre><code>git --version</code></pre><br>
If you specifically need a higher version you can used this FAQ to install a newer version.<br>
<br>
<h2>Git 2.1.3</h2><br>
You need to SSH into your slot to complete this guide. If you don&#x27;t know how to do this <a href="https://www.feralhosting.com/faq/view?question=12">here is a basic guide</a><br>
<br>
<pre><code>mkdir -p ~&#x2F;bin &amp;&amp; bash</code></pre><br>
Now install git using these commands:<br>
<br>
<pre><code>wget -qO ~&#x2F;git.tar.gz <a href="https://www.kernel.org/pub/software/scm/git/git-2.1.3.tar.gz">https:&#x2F;&#x2F;www.kernel.org&#x2F;pub&#x2F;software&#x2F;scm&#x2F;git&#x2F;git-2.1.3.tar.gz</a>
tar xf ~&#x2F;git.tar.gz &amp;&amp; cd ~&#x2F;git-2.1.*
.&#x2F;configure --prefix=$HOME --with-curl=&#x2F;opt&#x2F;curl&#x2F;current
make &amp;&amp; make install
cd &amp;&amp; rm -rf git{-2.1.*,.tar.gz}</code></pre><br>
Then do this to check the version.<br>
<br>
<pre><code>git --version</code></pre><br>
If the version is still <code>1.7.10.4</code> then open a new SSH connection for the changes to take effect:<br>
<br>
You can now do things like clone. Here is an example command:<br>
<br>
<pre><code>git clone git:&#x2F;&#x2F;github.com&#x2F;username&#x2F;repo.git ~&#x2F;where&#x2F;you&#x2F;want&#x2F;this&#x2F;repo
git clone <a href="https://github.com/username/repo.git">https:&#x2F;&#x2F;github.com&#x2F;username&#x2F;repo.git</a> ~&#x2F;where&#x2F;you&#x2F;want&#x2F;this&#x2F;repo</code></pre><br>
<h2>Install from github source.</h2><br>
For the latest git you can do this.<br>
<br>
 <strong>Important note:</strong> Only use this method if you require the very latest code. Otherwise user the officially released tar ball in the previous section.<br>
<br>
<pre><code>wget -qO ~&#x2F;git.zip <a href="https://github.com/git/git/archive/master.zip">https:&#x2F;&#x2F;github.com&#x2F;git&#x2F;git&#x2F;archive&#x2F;master.zip</a>
unzip -qo ~&#x2F;git.zip &amp;&amp; cd git-master
make configure
.&#x2F;configure --prefix=$HOME --with-curl=&#x2F;opt&#x2F;curl&#x2F;current
make &amp;&amp; make install
cd &amp;&amp; rm -rf git{.zip,-master}</code></pre><br>
<br>
