<h1>Mount Your Server as a Local Filesystem - Linux</h1>

        
This guide is intended for GNU Linux users who wish to mount their server onto their local file system so they can quickly access files stored there. This guide is prepared for Ubuntu but users of other Linux distributions should use their own package managers to install to necessary software. <br>
<br>
<h3>Installation &amp; Configuration</h3><br>
<strong>1:</strong> Install the <em>sshfs</em> package (use <em>apt-get</em> instead of <em>aptitude</em> on some versions)<br>
<br>
<pre><code>sudo aptitude install sshfs</code></pre><br>
<strong>2:</strong> Add yourself to group <em>fuse</em><br>
<br>
<pre><code>sudo adduser $USER fuse</code></pre><br>
If using <em>$USER</em> creates problems, substitute it for your local username.<br>
<br>
<strong>3:</strong> Log out and log back in again for the changes to take effect<br>
<br>
<strong>4:</strong> Create a local directory where you want to mount your data<br>
<br>
<pre><code>mkdir ~&#x2F;feral</code></pre><br>
<strong>5:</strong> Perform initial test to see if you can mount manually<br>
<br>
<pre><code>sshfs -o idmap=user <strong>username</strong>@<strong>serve</strong>r.feralhosting.com:&#x2F;media&#x2F;<strong>DiskID&#x2F;home&#x2F;username</strong> ~&#x2F;feral</code></pre><br>
<strong>6:</strong> If all went well and you don&#x27;t want to automount (and automate) this, then you are finished. Simply run the previous command whenever you want accesss! Run this command to safely unmount: <br>
<br>
<pre><code>fusermount -u ~&#x2F;feral</code></pre><br>
<h3>Advanced</h3><br>
<strong>7:</strong> Those who wish to automount their server need to edit &#x2F;etc&#x2F;fstab:<br>
<br>
<pre><code>sudo nano &#x2F;etc&#x2F;fstab</code></pre><br>
<strong>8:</strong> Add the following line to the end of fstab:<br>
<br>
<pre><code>user@server.feralhosting.com:&#x2F;path&#x2F;to&#x2F;your&#x2F;disk&#x2F; &#x2F;mnt&#x2F;file&#x2F; fuse auto_cache,reconnect,allow_other,idmap=user</code></pre><br>
<strong>9:</strong> Run <em>sudo mount -a</em> and your server should mount OK. On the next reboot it should all work automatically.<br>
<br>
