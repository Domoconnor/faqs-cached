<h1>node.js - How to install</h1>

        
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
<h2>node.js installation</h2><br>
Use this command to create the <code>~&#x2F;bin</code> directory and reload your shell for this change to take effect.<br>
<br>
<pre><code>mkdir -p ~&#x2F;bin &amp;&amp; bash</code></pre><br>
This command downloads the <code>node-v4.3.1-linux-x64.tar.gz</code> and then saves it as <code>node.tar.gz</code> in your servers root directory.<br>
<br>
<pre><code>wget -qO ~&#x2F;node.js.tar.gz <a href="https://nodejs.org/dist/v4.3.1/node-v4.3.1-linux-x64.tar.gz">https:&#x2F;&#x2F;nodejs.org&#x2F;dist&#x2F;v4.3.1&#x2F;node-v4.3.1-linux-x64.tar.gz</a></code></pre><br>
This unpacks the folder archived inside the node.tar.gz.<br>
<br>
<pre><code>tar xf ~&#x2F;node.js.tar.gz --strip-components=1 -C ~&#x2F;</code></pre><br>
This deletes the tar archive and unpacked folder we no longer need.<br>
<br>
<pre><code>cd &amp;&amp; rm -rf node.js.tar.gz</code></pre><br>
Tries to call <code>node.js</code> to check the version:<br>
<br>
<pre><code>node -v</code></pre><br>
Which should return:<br>
<br>
<pre><code>v4.3.1</code></pre><br>
If you see the version then it is ready to use.<br>
<br>
Once you have done this, you are ready to start writing and running your <code>node.js</code> apps from anywhere in your account. I personally put all my apps in <code>~&#x2F;node&#x2F;apps&#x2F;</code> to keep things tidy though.<br>
<br>
<h2>Install from source</h2><br>
<strong>Important note:</strong> node takes a very long time to compile from source.<br>
<br>
Use this command to create the <code>~&#x2F;bin</code> directory and reload your shell for this change to take effect.<br>
<br>
<pre><code>mkdir -p ~&#x2F;bin &amp;&amp; bash</code></pre><br>
Now run these commands:<br>
<br>
<pre><code>wget -qO ~&#x2F;node.js.tar.gz <a href="https://nodejs.org/dist/v4.3.1/node-v4.3.1.tar.gz">https:&#x2F;&#x2F;nodejs.org&#x2F;dist&#x2F;v4.3.1&#x2F;node-v4.3.1.tar.gz</a>
tar xf ~&#x2F;node.js.tar.gz &amp;&amp; cd ~&#x2F;node-v4.3.1
.&#x2F;configure --prefix=$HOME
make &amp;&amp; make install &amp;&amp; cd
rm -rf ~&#x2F;node{-v4.3.1,.js.tar.gz}</code></pre><br>
<br>
