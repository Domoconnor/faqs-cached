<h1>Disk Usage - Check your usage in SSH</h1>

        
<strong>Important note:</strong> Feral uses powers of 1000 to calculate your usage!<br>
<br>
<code>1000</code> = <code>kB</code> &#x2F; <code>MB</code> &#x2F; <code>GB</code> &#x2F; <code>TB</code><br>
<br>
<code>1024</code> = <code>KiB</code> &#x2F; <code>MiB</code> &#x2F; <code>GiB</code> &#x2F; <code>TiB</code><br>
<br>
To check the amount of space used in your slice, type this command:<br>
<br>
<pre><code>du -sB GB ~&#x2F;</code></pre><br>
<code>-s</code> is for summarize, instead of each folder size listed separately<br>
<br>
<code>-B</code> is for block size. In this case it is <code>GB</code><br>
<br>
There might be a delay before any response is displayed, it may possibly take up to 3 minutes for the system to calculate the amount of data in your slice.<br>
<br>
To check the size of a folder you can do:<br>
<br>
<pre><code>du -sB GB ~&#x2F;private&#x2F;rtorrent&#x2F;data</code></pre><br>
<h3>Tip</h3><br>
You can create an alias for the above command (or any command) in your <code>.bash_aliases</code> file, which is located in your <code>~&#x2F;</code> (home) directory. Just edit the <code>.bash_aliases</code> file, and add this line to it:<br>
<br>
<pre><code>alias space=&#x27;du -sB GB ~&#x2F;&#x27;</code></pre><br>
You can name it whatever you want - I happen to call it <code>space</code>, because it&#x27;s easy for me to remember.<br>
<br>

