<h1>ruTorrent Plugin - Unpack</h1>

        
<h2>Installing Unpack</h2>If you&#x27;re using 3.6 of ruTorrent (which is the default version installed here at Feral) you won&#x27;t be able to use the general plugin install method described on <a href="https://www.feralhosting.com/faq/view?question=282">this page</a>. Instead, execute these commands:<br>
<br>
<pre><code>rm -rf ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;rutorrent&#x2F;plugins&#x2F;unpack
wget -q <a href="https://bintray.com/novik65/generic/download_file?file_path=plugins%2Funpack-3.6.tar.gz">https:&#x2F;&#x2F;bintray.com&#x2F;novik65&#x2F;generic&#x2F;download_file?file_path=plugins%2Funpack-3.6.tar.gz</a>
tar xf download_file\?file_path\=plugins%2Funpack-3.6.tar.gz -C ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;rutorrent&#x2F;plugins&#x2F;
rm download_file\?file_path\=plugins%2Funpack-3.6.tar.gz
</code></pre><br>
The first command removes any existing instance of unpack in case you previously installed an incorrect version. Naturally if you are using the 3.7 version of ruTorrent then you can install unpack by following the general plugin install method.
<br>
