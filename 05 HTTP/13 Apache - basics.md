<h1>Apache - basics</h1>

        
<br>
Here are some basic usages of Apache 2.<br>
<br>
<strong>Configuration files</strong><br>
<br>
Drop your custom <code>.conf</code> files in to this folder:<br>
<br>
<pre><code>~&#x2F;.apache2&#x2F;conf.d&#x2F;</code></pre><br>
Then restart Apache.<br>
<br>
<strong>Reload Apache configurations:</strong><br>
<br>
This command will reload your <code>conf</code> files instead of restarting.<br>
<br>
 <strong>Important note:</strong> This error below is normal and to be expected when reloading Apache2.<br>
<br>
<pre><code>mkdir: cannot create directory ‘&#x2F;var&#x2F;run&#x2F;apache2’: Permission denied</code></pre><br>
Use this command to reload Apache2:<br>
<br>
<pre><code>&#x2F;usr&#x2F;sbin&#x2F;apache2ctl -k graceful</code></pre><br>
<strong>Important note:</strong> You cannot restart or start Apache, only the system can do that. If you kill the process or it dies you will need to wait up to 5 minutes or it to restart. You can reload the configuration using the above command.<br>
<br>
<strong>List loaded modules:</strong><br>
<br>
This will list currently loaded modules that are usable:<br>
<br>
<pre><code>&#x2F;usr&#x2F;sbin&#x2F;apachectl -t -D DUMP_MODULES</code></pre><br>
<strong>List available modules.</strong><br>
<br>
This will list all available modules that you can load:<br>
<br>
<pre><code>ls -1 &#x2F;etc&#x2F;apache2&#x2F;mods-available&#x2F;</code></pre><br>
<strong>For example. Here is the way you would load the Auth Digest module:</strong><br>
<br>
To load a modules you will need to create and then edit a <code>~&#x2F;.apache2&#x2F;conf.d&#x2F;some.conf</code> file and then restart Apache like this:<br>
<br>
<pre><code>nano ~&#x2F;.apache2&#x2F;conf.d&#x2F;digest.conf</code></pre><br>
Now Add this line to the top of the file to load the auth digest module.<br>
<br>
<pre><code>Include &#x2F;etc&#x2F;apache2&#x2F;mods-available&#x2F;auth_digest.load</code></pre><br>
Save by pressing and holding <code>CTRL</code> and then pressing <code>x</code> then press <code>Y</code> to confirm.<br>
<br>
Reload the changes:<br>
<br>
<pre><code>&#x2F;usr&#x2F;sbin&#x2F;apache2ctl -k graceful</code></pre><br>
Test it is loaded: might be near the bottom<br>
<br>
<pre><code>&#x2F;usr&#x2F;sbin&#x2F;apachectl -t -D DUMP_MODULES</code></pre><br>
The error log is found here:<br>
<br>
<pre><code>~&#x2F;.apache2&#x2F;error.log</code></pre><br>
<br>
