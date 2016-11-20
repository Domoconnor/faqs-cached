<h1>Putting your WWW folder to use</h1>

        
<br>
All plans come with a public folder that you can access via your web browser. By default anyone can view the files (including Google) displayed in there. <br>
<br>
If you follow the rest of this guide please be sure to <a href="https://www.feralhosting.com/faq/view?question=22">protect your files with a password</a>. The login and password for this folder will be separate from your other details and can be setup to allow access to multiple users.<br>
<br>
There are various useful and interesting ways to make use of this WWW folder, shown in some of the other FAQs in this section. In this FAQ we are going to focus on simplicity.<br>
<br>
<h2>Let&#x27;s get started </h2><br>
Your <code>public_html</code> folder is located here:<br>
<br>
<pre><code>~&#x2F;www&#x2F;username.servername.feralhosting.com&#x2F;public_html</code></pre><br>
An easy way to execute SSH commands in this folder is to use this command:<br>
<br>
<pre><code> ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;</code></pre><br>
This command will work for everyone to automatically find your username and servername and will be used through this FAQ.<br>
<br>
<h2>Prevent search indexing - robots.txt</h2><br>
To prevent indexing by search engines use this command.<br>
<br>
<pre><code>echo -e &#x27;User-agent: *\nDisallow: &#x2F;&#x27; &gt; ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;robots.txt</code></pre><br>
<a href="http://www.robotstxt.org/robotstxt.html">http:&#x2F;&#x2F;www.robotstxt.org&#x2F;robotstxt.html</a><br>
<br>
<h2>Creating Symbolic links</h2><br>
In SSH do these commands. Use this faq if you do not know how to SSH into your slot: <a href="https://www.feralhosting.com/faq/view?question=12">SSH basics - Putty</a><br>
<br>
First we create a directory that will be home to our custom links in this guide.<br>
<br>
<pre><code>mkdir -p ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;links</code></pre><br>
This will create a folder called <code>links</code> inside your WWW folder.<br>
<br>
Here are some examples of how you would create symlinks to make folders available.<br>
<br>
The format of the symbolic link command is like this:<br>
<br>
<pre><code>ln -s ~&#x2F;the&#x2F;folder&#x2F;or&#x2F;file&#x2F;i&#x2F;want&#x2F;linked&#x2F;to ~&#x2F;the&#x2F;destination&#x2F;of&#x2F;the&#x2F;shortcut&#x2F;and&#x2F;the&#x2F;name</code></pre><br>
<h2>rtorrent data symbolic link</h2><br>
<pre><code>ln -s ~&#x2F;private&#x2F;rtorrent&#x2F;data&#x2F; ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;links&#x2F;rtorrent_data</code></pre><br>
Please make sure this is the correct path to your rTorrent your data folder if different from the default location.<br>
<br>
<h2>Tranmission default data folder</h2><br>
<pre><code>ln -s ~&#x2F;private&#x2F;transmission&#x2F;data&#x2F; ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;links&#x2F;transmission_data</code></pre><br>
Please make sure this is the correct path to your Transmission your data folder if different from the default location<br>
<br>
<h2>Deluge default data folder</h2><br>
<pre><code>ln -s ~&#x2F;private&#x2F;deluge&#x2F;data&#x2F; ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;links&#x2F;deluge_data</code></pre><br>
Please make sure this is the correct path to your Deluge your data folder if different from the default location<br>
<br>
Now visit your WWW <code>links</code> folder in your browser, click on the newly created symbolic links, and you should be able to see a nice index of whatever files are inside the folders you have just linked to. Now you can use a browser or a download manager to download your stuff.<br>
<br>
<h2>Optional</h2><br>
<a href="http://larsjung.de/h5ai/">h5ai directory indexer</a><br>
<br>
<strong>Important note:</strong> The main <code>_h5ai</code> directory does not like being anywhere else except the server root. To only apply the indexing to certain directories please use the options described below. Do not try to install the actual <code>_h5ai</code> directory to a sub directory.<br>
<br>
The screen shot below illustrates the result:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Putting%20your%20WWW%20folder%20to%20use/h5ai.png"><br>
<br>
To download _h5ai 0.27 (custom with dual URL format fix) use these commands in SSH.<br>
<br>
 <strong>Important note:</strong> This is a very <a href="https://github.com/feralhosting/_h5ai_custom/commit/170dd526ea2fa1a17b10dd73b0db35777bd17ea2">lightly modified</a> version to allow it work with both URL formats you are provided at Feral.<br>
<br>
<pre><code>wget -qO ~&#x2F;h5ai.zip <a href="http://git.io/dEazsw">http:&#x2F;&#x2F;git.io&#x2F;dEazsw</a>
unzip -qo ~&#x2F;h5ai.zip -d ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;</code></pre><br>
<strong>For Apache only:</strong><br>
<br>
Use this command to append the required entry to an existing <code>.htaccess</code> files or it will create one if needed.<br>
<br>
<pre><code>echo -e &#x27;\nDirectoryIndex&nbsp; index.html&nbsp; index.php&nbsp; &#x2F;_h5ai&#x2F;server&#x2F;php&#x2F;index.php&#x27; &gt;&gt; ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;.htaccess</code></pre><br>
<code>_h5ai</code> will now be ready to use in your WWW. By default this works from the WWW root down. <br>
<br>
If you would like to make it specific to certain folders you need to edit the <code>.htaccess </code> files and remove this:<br>
<br>
<pre><code>DirectoryIndex&nbsp; index.html&nbsp; index.php&nbsp; &#x2F;_h5ai&#x2F;server&#x2F;php&#x2F;index.php</code></pre><br>
Then, inside the directory you want to use <code>_h5ai</code> create either:<br>
<br>
1: Create a <code>.htaccess</code> file if there is not one present, or add the line to it <br>
<br>
2: Add the line to any existing <code>.htaccess</code> files. This will make it work for this folder and folders within.<br>
<br>
<strong>For nginx only:</strong><br>
<br>
Run these two commands:<br>
<br>
<pre><code>echo -e &#x27;location &#x2F; {\n&nbsp; &nbsp; index&nbsp; index.html&nbsp; index.php&nbsp; &#x2F;_h5ai&#x2F;server&#x2F;php&#x2F;index.php;\n}&#x27; &gt; ~&#x2F;.nginx&#x2F;conf.d&#x2F;000-default-server.d&#x2F;h5ai.conf
&#x2F;usr&#x2F;sbin&#x2F;nginx -s reload -c ~&#x2F;.nginx&#x2F;nginx.conf</code></pre><br>
Once it has restarted the h5ai should be working.<br>
<br>
<h2>h5ai custom directory with nginx that is not password protected</h2><br>
For a specific directory only, you can change the location in the <code>h5ai.conf</code> if the directory you want to use is not already password protected:<br>
<br>
<strong>Important note:</strong> The location is relative to your WWW root. Make sure the location exists in your WWW.<br>
<br>
For example we can edit the <code>h5ai.conf</code> to this:<br>
<br>
<pre><code>location &#x2F;links {
&nbsp; &nbsp; index&nbsp; index.html&nbsp; index.php&nbsp; &#x2F;_h5ai&#x2F;server&#x2F;php&#x2F;index.php;
}</code></pre><br>
Then reload your nginx configuration:<br>
<br>
<pre><code>&#x2F;usr&#x2F;sbin&#x2F;nginx -s reload -c ~&#x2F;.nginx&#x2F;nginx.conf</code></pre><br>
<h2>h5ai custom directory with nginx that is also password protected </h2><br>
If the directory you want to use h5ai with is already password protected then you must merge the changes into the <code>.conf</code> for that location and then remove the <code>h5ai.conf</code> or nginx won&#x27;t restart:<br>
<br>
So for example we edit the <code>links.conf</code> to be like this:<br>
<br>
<pre><code>location &#x2F;links {
&nbsp; &nbsp; index&nbsp; index.html&nbsp; index.php &#x2F;_h5ai&#x2F;server&#x2F;php&#x2F;index.php;
&nbsp; &nbsp; auth_basic &quot;Please log in&quot;;
&nbsp; &nbsp; auth_basic_user_file &#x2F;path&#x2F;to&#x2F;the&#x2F;.htpasswd;
}</code></pre><br>
Then delete the <code>h5ai.conf</code> and then reload your nginx configuration:<br>
<br>
<pre><code>&#x2F;usr&#x2F;sbin&#x2F;nginx -s reload -c ~&#x2F;.nginx&#x2F;nginx.conf</code></pre><br>
<h2>Contribute:</h2><br>
The repo for this custom file can be found here for users to check or to contribute to.<br>
<br>
<a href="https://github.com/feralhosting/_h5ai_custom">https:&#x2F;&#x2F;github.com&#x2F;feralhosting&#x2F;_h5ai_custom</a><br>
<br>
