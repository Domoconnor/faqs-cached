<h1>Unrar - How to Install a Newer Version</h1>

        
Winrar - How to install a newer version than the slot version (3.90)<br>
<br>
<pre><code>mkdir -p ~&#x2F;bin &amp;&amp; bash
wget -qO ~&#x2F;unrar.tar.gz <a href="http://www.rarlab.com/rar/unrarsrc-5.3.9.tar.gz">http:&#x2F;&#x2F;www.rarlab.com&#x2F;rar&#x2F;unrarsrc-5.3.9.tar.gz</a>
tar xf ~&#x2F;unrar.tar.gz &amp;&amp; cd ~&#x2F;unrar
make &amp;&amp; make install DESTDIR=~
cd &amp;&amp; rm -rf unrar{,.tar.gz}</code></pre><br>
You should now be able to use this program like this:<br>
<br>
<pre><code>unrar</code></pre><br>
If you do not get version 5 + then log out then back into SSH.
<br>
