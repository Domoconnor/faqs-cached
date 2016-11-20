<h1>Pydio - Basic setup</h1>

        
<br>
 <strong>Important note:</strong> To fully configure Pydio with the valid https URL please see the last section of this article.<br>
<br>
<h2>Install Pydio</h2><br>
Formerly AjaXplorer, file sharing platform for the enterprise<br>
<br>
In SSH do these commands. Use this FAQ if you do not know how to SSH into your slot: <a href="https://www.feralhosting.com/faq/view?question=12">SSH basics - Putty</a><br>
<br>
<pre><code>wget -qO ~&#x2F;pydio.tar.gz <a href="http://downloads.sourceforge.net/project/ajaxplorer/pydio/stable-channel/6.0.8/pydio-core-6.0.8.tar.gz">http:&#x2F;&#x2F;downloads.sourceforge.net&#x2F;project&#x2F;ajaxplorer&#x2F;pydio&#x2F;stable-channel&#x2F;6.0.8&#x2F;pydio-core-6.0.8.tar.gz</a>
tar xf ~&#x2F;pydio.tar.gz
cp -rf ~&#x2F;pydio-core-6.0.8&#x2F;. ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;pydio
sed -i &#x27;s|&#x2F;&#x2F;define(&quot;AJXP_LOCALE&quot;, &quot;en_EN.UTF-8&quot;);|define(&quot;AJXP_LOCALE&quot;, &quot;en_GB.UTF-8&quot;);|g&#x27; ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;pydio&#x2F;conf&#x2F;bootstrap_conf.php
cd &amp;&amp; rm -rf pydio{-core-6.0.8,.tar.gz}</code></pre><br>
The last command sets the locale to <code>en.GB.UTF-8</code>.<br>
<br>
Or you could edit it to be say <code>en_US.UTF-8</code> if you wanted.<br>
<br>
If you are using nginx you will need to do this:<br>
<br>
<strong>1:</strong> Create a <code>.conf</code> file on the <code>~&#x2F;.nginx&#x2F;conf.d&#x2F;000-default-server.d</code> directory. We can use <code>nano</code> to do this:<br>
<br>
We will call it <code>pydio.conf</code>.<br>
<br>
<pre><code>nano -w ~&#x2F;.nginx&#x2F;conf.d&#x2F;000-default-server.d&#x2F;pydio.conf</code></pre><br>
Now add these lines to it and save the changes.<br>
<br>
<pre><code>location &#x2F;pydio&#x2F; { }
location &#x2F;pydio&#x2F;conf&#x2F;&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  { deny all; }
location &#x2F;pydio&#x2F;data&#x2F;&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  { deny all; }
location &#x2F;pydio&#x2F;data&#x2F;public&nbsp; &nbsp;  { allow all; }
location &#x2F;pydio&#x2F;robots.txt&nbsp; &nbsp; &nbsp; { access_log off; log_not_found off; }
location &#x2F;pydio&#x2F;favicon.ico&nbsp; &nbsp;  { access_log off; log_not_found off; }
location ~ &#x2F;pydio&#x2F;\.&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; { access_log off; log_not_found off; deny all; }
location ~ &#x2F;pydio&#x2F;~$&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; { access_log off; log_not_found off; deny all; }</code></pre><br>
Then press and hold <code>CTRL</code> and then press <code>x</code> to save. Press <code>y</code> to confirm.<br>
<br>
Now reload the configurations using this command (You can ignore errors about the log file):<br>
<br>
<pre><code>&#x2F;usr&#x2F;sbin&#x2F;nginx -s reload -c ~&#x2F;.nginx&#x2F;nginx.conf</code></pre><br>
Now visit the URL (where <code>server</code> is name of your Feral Slot&#x27;s server and your username):<br>
<br>
<pre><code><a href="https://server.feralhosting.com/username/pydio">https:&#x2F;&#x2F;server.feralhosting.com&#x2F;username&#x2F;pydio</a></code></pre><br>
Ignore the warnings.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Pydio%20-%20Basic%20setup/1.png"><br>
<br>
Click &quot;Start Wizard&quot;<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Pydio%20-%20Basic%20setup/setup1.png"><br>
<br>
This is an overview of the setup wizard:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Pydio%20-%20Basic%20setup/setup2.png"><br>
<br>
Enter a username and password:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Pydio%20-%20Basic%20setup/setup2.5.png"><br>
<br>
Configure the Global options as you wish, they can be left as they are:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Pydio%20-%20Basic%20setup/setup3.png"><br>
<br>
Select &quot;Database&quot; from the drop down menu:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Pydio%20-%20Basic%20setup/setup4.png"><br>
<br>
For this FAQ we use sqlite, so select sqlite from the drop down menu, the path is relative to the installation folder&#x27;s root.<br>
<br>
For mysql:<br>
<br>
The socket path must start with <code>:</code> , for example:<br>
<br>
<pre><code>:&#x2F;media&#x2F;DiskID&#x2F;username&#x2F;private&#x2F;mysql&#x2F;socket</code></pre><br>
This is a relevant FAQ - <a href="https://www.feralhosting.com/faq/view?question=213">Mysql - Change php settings using htaccess</a> which will allow you to use <code>localhost</code> as the hostname.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Pydio%20-%20Basic%20setup/setup5.png"><br>
<br>
Optional: Add some users if you wish. This can be done later:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Pydio%20-%20Basic%20setup/setup6.png"><br>
<br>
Click on &quot;Install AjaXplorer Now!&quot; to finish the installation.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Pydio%20-%20Basic%20setup/setup7.png"><br>
<br>
Once you have installed AjaXplorer you will create a &quot;Workspace&quot;<br>
<br>
You start this process by clicking on your <code>username</code> in the top right, then clicking on <code>settings</code><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Pydio%20-%20Basic%20setup/workspace1.png"><br>
<br>
In the settings page click on <code>Workspaces</code> to view the drop down menu and then click on <code>New Workspace</code><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Pydio%20-%20Basic%20setup/workspace2.png"><br>
<br>
Now you can configure some basics of your new workspace. In this example I have used:<br>
<br>
<strong>Access Driver:</strong> File System (Standard)<br>
<strong>Path:</strong> The full path to the root of this workspace, which in my example is my root folder.<br>
<strong>File Creation Mask:</strong> 0700 (0666 is the default)<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Pydio%20-%20Basic%20setup/workspace3.png"><br>
<br>
<h2>Valid https for share URLs and plug-ins</h2><br>
To fully configure Pydio to work with the valid https URL you must configure a setting post installation. Start by going to the settings page.<br>
<br>
<img src="https://raw.githubusercontent.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Pydio%20-%20Basic%20setup/url1.png"><br>
<br>
Choose: <code>Application Core</code><br>
<br>
From the side menu:<br>
<br>
<img src="https://raw.githubusercontent.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Pydio%20-%20Basic%20setup/url2.png"><br>
<br>
or from the main window:<br>
<br>
<img src="https://raw.githubusercontent.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Pydio%20-%20Basic%20setup/url3.png"><br>
<br>
Choose: <code>Pydio Main Options</code><br>
<br>
<img src="https://raw.githubusercontent.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Pydio%20-%20Basic%20setup/url4.png"><br>
<br>
Then you will need to change the <code>Server URL</code> setting in the <code>Main Options</code><br>
<br>
<img src="https://raw.githubusercontent.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Pydio%20-%20Basic%20setup/url5.png"><br>
<br>
Using the settings according to this FAQ the URL will be like this:<br>
<br>
<pre><code><a href="https://server.feralhosting.com/username/pydio">https:&#x2F;&#x2F;server.feralhosting.com&#x2F;username&#x2F;pydio</a></code></pre><br>
This will change the Server URL for all Pydio plug-ins.<br>
<br>
