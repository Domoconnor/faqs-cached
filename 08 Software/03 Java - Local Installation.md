<h1>Java - Local Installation</h1>

        
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
<strong>Important note:</strong> FeralHosting does not allow gameservers of any type, especially those based on Java.&nbsp; Java-based applications that consume large amounts of memory and other resources will also not be tolerated; this includes BTC&#x2F;LTC mining and encoding<br>
<br>
If you need java 1.6 it&#x27;s likely already installed by request of another user. If not, open a ticket and request it to be installed.<br>
<br>
If you need a newer version of Java, such as 1.7, follow these directions. These directions can be adapted to support any version of Java.<br>
&nbsp; &nbsp; <br>
<h2>Installing Java locally</h2><br>
Use this command to create the <code>~&#x2F;bin</code> directory and reload your shell for this change to take effect.<br>
<br>
<pre><code>mkdir -p ~&#x2F;bin &amp;&amp; bash</code></pre><br>
Files found via <a href="http://www.java.com/en/download/manual.jsp?locale=en">http:&#x2F;&#x2F;www.java.com&#x2F;en&#x2F;download&#x2F;manual.jsp?locale=en</a>. You want the <code>.tar.gz</code> file, not the <code>.deb</code> or <code>.rpm</code> -- those are used when you are installing with root privileges.<br>
&nbsp; &nbsp;  <br>
This method will download and install&#x2F;update the 64 bit Java files for Linux<br>
<br>
<h3>Java 1.8 U65</h3><br>
Download v8:<br>
<br>
<pre><code>wget -qO ~&#x2F;java.tar.gz <a href="http://javadl.sun.com/webapps/download/AutoDL?BundleId=111681">http:&#x2F;&#x2F;javadl.sun.com&#x2F;webapps&#x2F;download&#x2F;AutoDL?BundleId=111681</a></code></pre><br>
Unpack the files:<br>
<br>
<pre><code>tar xf ~&#x2F;java.tar.gz --strip-components=1 -C ~&#x2F;</code></pre><br>
This command also removes the folders and archives we don&#x27;t need after we are done with them.<br>
<br>
Manually call <code>java</code> it like this:<br>
<br>
<pre><code>~&#x2F;bin&#x2F;java -version</code></pre><br>
You will see this:<br>
<br>
<pre><code>java version &quot;1.8.0_65&quot;
Java(TM) SE Runtime Environment (build 1.8.0_65-b17)
Java HotSpot(TM) 64-Bit Server VM (build 25.65-b01, mixed mode)</code></pre><br>
Unless you used the <code>-version</code> command before installing the update can just do this command below, otherwise log into a new SSH session for the changes to take effect and then check your version again.<br>
<br>
<pre><code>java -version</code></pre><br>
You should see the same result as before.<br>
<br>
