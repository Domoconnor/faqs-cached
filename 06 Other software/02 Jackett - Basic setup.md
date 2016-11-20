<h1>Jackett - Basic setup</h1>

        
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
<h2>Installing Jackett</h2><br>
<strong>Important note:</strong> Jackett requires mono to function. But, since it is also a tool for use with Sonarr you should already have this installed. Please see <a href="https://www.feralhosting.com/faq/view?question=303">this</a> page for a guide to installing mono and Sonarr.<br>
<br>
Then run these commands to get and install Jackett:<br>
<br>
<pre><code>wget -qO ~&#x2F;Jackett.tar.gz <a href="https://github.com/Jackett/Jackett/releases/download/v0.7.303/Jackett.Binaries.Mono.tar.gz">https:&#x2F;&#x2F;github.com&#x2F;Jackett&#x2F;Jackett&#x2F;releases&#x2F;download&#x2F;v0.7.303&#x2F;Jackett.Binaries.Mono.tar.gz</a>
tar xf ~&#x2F;Jackett.tar.gz
rm -rf ~&#x2F;Jackett.tar.gz</code></pre><br>
Start Jackett:<br>
<br>
<pre><code>screen -dmS jackett mono --debug ~&#x2F;Jackett&#x2F;JackettConsole.exe &amp;&amp; screen -list</code></pre><br>
Attach to this screen at any time by using the command <code>screen -r jackett</code><br>
You can stop Jackett with ctrl+c to get the config file created.<br>
<br>
Your configuration will be saved here at <code>~&#x2F;.config&#x2F;Jackett&#x2F;ServerConfig.json</code><br>
Now we need to randomize the start port because the default is 9117 (and this may already be taken):<br>
<br>
<pre><code>sed -i &#x27;s|&quot;Port&quot;: 9117,|&quot;Port&quot;: &#x27;$(shuf -i 10001-59001 -n 1)&#x27;,|g&#x27; ~&#x2F;.config&#x2F;Jackett&#x2F;ServerConfig.json</code></pre><br>
You can read the port&nbsp; and find the access URL with:<br>
<pre><code>echo -e &quot;\n<a href="http://">http:&#x2F;&#x2F;</a>$(hostname -f):$(sed -rn &#x27;s|(.*)&quot;Port&quot;: (.*),|\2|p&#x27; ~&#x2F;.config&#x2F;Jackett&#x2F;ServerConfig.json)&quot;</code></pre> 
<br>