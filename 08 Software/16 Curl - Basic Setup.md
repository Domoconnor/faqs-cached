<h1>Curl -  Basic Setup</h1>

        
curl is an open source command line tool and library for transferring data with URL syntax, supporting DICT, FILE, FTP, FTPS, Gopher, HTTP, HTTPS, IMAP, IMAPS, LDAP, LDAPS, POP3, POP3S, RTMP, RTSP, SCP, SFTP, SMB, SMTP, SMTPS, Telnet and TFTP.<br>
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
<h2>Curl installation</h2><br>
 <strong>Important note:</strong> <code>curl</code>&nbsp; is already installed on your slot though it is located here instead:<br>
<br>
<pre><code>&#x2F;opt&#x2F;curl&#x2F;current</code></pre><br>
<h2>Curl manual installation:</h2><br>
Use these first two commands to create to do some pre requisite tasks:<br>
<br>
<pre><code>mkdir -p ~&#x2F;bin &amp;&amp; bash</code></pre><br>
Install the program using these commands:<br>
<br>
<pre><code>wget -qO ~&#x2F;curl.tar.gz <a href="http://curl.haxx.se/download/curl-7.41.0.tar.gz">http:&#x2F;&#x2F;curl.haxx.se&#x2F;download&#x2F;curl-7.41.0.tar.gz</a>
tar xf ~&#x2F;curl.tar.gz &amp;&amp; cd ~&#x2F;curl-7.41.0
.&#x2F;configure --prefix=$HOME
make &amp;&amp; make install
cd &amp;&amp; rm -rf curl{-7.41.0,.tar.gz}</code></pre><br>
Check your version:<br>
<br>
<pre><code>curl -V</code></pre><br>
<br>
