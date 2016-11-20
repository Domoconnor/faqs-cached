<h1>Python - Usage and Installation</h1>

        
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
<strong>Important Note:</strong> Do not install Python manually without a good reason. It will most likely cause more problems than is solves.<br>
<br>
<strong>Python 2.7.9 is already installed on your slot</strong><br>
<br>
Type to show the current version:<br>
<br>
<pre><code>python -V</code></pre><br>
<code>pip</code> is installed on all servers ready to be used. You do no need to install <code>pip</code> locally first. To use it do this:<br>
<br>
<pre><code>pip install --user modulename</code></pre><br>
For example:<br>
<br>
<pre><code>pip install --user requests</code></pre><br>
<h2>Installing Modules locally and&#x2F;or overriding installed modules</h2><br>
This step is required otherwise you&#x27;ll get an error.<br>
<br>
<pre><code>pip install --user --ignore-installed pip</code></pre><br>
Now you can overwrite modules locally using this command:<br>
<br>
<pre><code>pip install --user --ignore-installed modulename</code></pre><br>
<h2>Installing Python locally:</h2><br>
You <strong>do not</strong> need to follow this FAQ to use python or python scripts. If you have a missing module you can open a ticket and ask staff to install it or use the above section to install it locally.<br>
<br>
This is a basic guide to installing Python to your home directory . You will also be able to use <code>easy_install</code> to install mods.<br>
<br>
<h2>Installing Python 2.7 from source:</h2><br>
In SSH do these commands. Use this FAQ if you do not know how to SSH into your slot: <a href="https://www.feralhosting.com/faq/view?question=12">SSH basics - Putty</a><br>
<br>
<strong>Important note:</strong> We do not recommend you install directly to <code>$HOME</code> or use this installation in the <code>PATH</code> over the existing version.&nbsp; There will be problems if you do. Do something like this instead:<br>
<br>
<pre><code>--prefix=$HOME&#x2F;python&#x2F;python.2.7</code></pre><br>
<pre><code>mkdir -p ~&#x2F;python&#x2F;python2
wget -qO ~&#x2F;Python.tgz <a href="https://www.python.org/ftp/python/2.7.10/Python-2.7.10.tgz">https:&#x2F;&#x2F;www.python.org&#x2F;ftp&#x2F;python&#x2F;2.7.10&#x2F;Python-2.7.10.tgz</a>
tar xf ~&#x2F;Python.tgz &amp;&amp; cd ~&#x2F;Python-2.7.10
.&#x2F;configure --prefix=$HOME&#x2F;python&#x2F;python2 &amp;&amp; make &amp;&amp; make install</code></pre><br>
The configuration and installation can take some time to be patient.<br>
<br>
When it is finished installing, do some clean up with this command.<br>
<br>
<pre><code>cd &amp;&amp; rm -rf ~&#x2F;Python{-2.7.10,.tgz}</code></pre><br>
Python has been installed. Now check which version is in use:<br>
<br>
<pre><code>~&#x2F;python&#x2F;python2&#x2F;bin&#x2F;python -V</code></pre><br>
Using <code>easy_install</code> from the command line to install mods:<br>
<br>
<pre><code>~&#x2F;python&#x2F;python2&#x2F;bin&#x2F;easy_install pip</code></pre><br>
<pre><code>~&#x2F;python&#x2F;python2&#x2F;bin&#x2F;pip install virtualenv</code></pre><br>
<pre><code>~&#x2F;python&#x2F;python2&#x2F;bin&#x2F;pip install flexget</code></pre><br>
<h2>Python 3</h2><br>
<pre><code>mkdir -p ~&#x2F;python&#x2F;python3
wget -qO ~&#x2F;python.tar.xz&nbsp; <a href="https://www.python.org/ftp/python/3.5.0/Python-3.5.0.tar.xz">https:&#x2F;&#x2F;www.python.org&#x2F;ftp&#x2F;python&#x2F;3.5.0&#x2F;Python-3.5.0.tar.xz</a>
tar xf ~&#x2F;python.tar.xz &amp;&amp; cd ~&#x2F;Python-3.5.0
.&#x2F;configure --prefix=$HOME&#x2F;python&#x2F;python3 &amp;&amp; make &amp;&amp; make install</code></pre><br>
The configuration and installation can take some time to be patient.<br>
<br>
When it is finished installing, do some clean up with this command.<br>
<br>
<pre><code>cd &amp;&amp; rm -rf ~&#x2F;python{-3.5.0,.tar.xz}</code></pre><br>
Python has been installed. Now check which version is in use:<br>
<br>
<pre><code>~&#x2F;python&#x2F;python3&#x2F;bin&#x2F;python3 -V</code></pre><br>
Using <code>easy_install</code> from the command line to install mods:<br>
<br>
<pre><code>~&#x2F;python&#x2F;python3&#x2F;bin&#x2F;pip3 install virtualenv</code></pre><br>
<br>
