<h1>Mumble - Installing Murmur on your slot.</h1>

        
Mumble is an open source, low-latency, high quality voice chat software primarily intended for use while gaming.<br>
<br>
<h1>Installing Murmur</h1><br>
<h2>&quot;Magic&quot; Installer</h2><br>
To install Murmur on your seedbox, you should use this script<br>
<br>
<pre><code>wget -qO ~&#x2F;install.murmur <a href="http://git.io/-mVd3g">http:&#x2F;&#x2F;git.io&#x2F;-mVd3g</a> &amp;&amp; bash ~&#x2F;install.murmur</code></pre><br>
Simply grab the script with wget or curl on your machine, run it, and you&#x27;ll have Murmur installed at <br>
<br>
<pre><code>~&#x2F;murmur&#x2F;murmurd</code></pre><br>
Once you&#x27;re done with that, please read the <code>Configuring Murmur.ini</code> section.<br>
<br>
Note: This script does nothing malicious. If you find a bug, please edit this Wiki page to note it, or message<br>
<br>
<pre><code>zovt</code></pre><br>
on IRC.<br>
<br>
<h2>Configuring Murmur.ini </h2><br>
At this point, running<br>
<br>
<pre><code>~&#x2F;murmur&#x2F;murmurd</code></pre><br>
will start murmur and leave you with a working server. However, this will pollute whatever directory you&#x27;re running it from with log files and database files. If you don&#x27;t want that, read on.<br>
<br>
By default, the above script should have created a file called<br>
<br>
<pre><code>murmur.ini</code></pre><br>
in<br>
<br>
<pre><code>~&#x2F;murmur&#x2F;</code></pre><br>
Fire up your favorite text editor and edit<br>
<br>
<pre><code>~&#x2F;murmur&#x2F;murmur.ini</code></pre><br>
and change the paths on the following lines in the file to whatever you like:<br>
<br>
<pre><code>database=
logfile=
pidfile=</code></pre><br>
I personally like just using the murmur folder at &#x2F;full path to your home dir&#x2F;murmur<br>
<br>
<h2>All Done! </h2><br>
Now, run murmur with<br>
<br>
<pre><code>~&#x2F;murmur&#x2F;murmurd -ini ~&#x2F;murmur&#x2F;murmur.ini</code></pre><br>
connect, and you&#x27;re good to go!<br>
<br>
