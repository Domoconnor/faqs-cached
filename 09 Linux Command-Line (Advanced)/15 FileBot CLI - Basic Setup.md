<h1>FileBot CLI - Basic Setup</h1>

        
<strong>Important note:</strong> You will need to have Java 1.8 installed locally to use this program - <a href="https://www.feralhosting.com/faq/view?question=183">Java 1.8</a><br>
<br>
From the <a href="https://www.filebot.net/forums/viewtopic.php?f=3&#x26;t=7&#x23;p7">Filebot FAQ</a><br>
<br>
<strong>Q:</strong> When I try to start filebot it crashes immediately with an UnsupportedClassVersionError. What does that mean?<br>
<br>
<strong>A:</strong> If you get an error like Exception in thread &quot;main&quot; java.lang.UnsupportedClassVersionError: net&#x2F;filebot&#x2F;Main : Unsupported major.minor version 52.0 it means that you&#x27;re running Java 6 or 7 but Java 8 is required for running FileBot.<br>
<br>
<h2>Filebot:</h2><br>
Filebot basic installation to use the command line options (no GUI) on your Feral slot.<br>
<br>
FileBot is the ultimate tool for organizing and renaming your movies, tv shows or anime, and music well as downloading subtitles and artwork. It&#x27;s smart and just works.<br>
<br>
Powerful and full-featured cmdline interface and scripting interface for any kind of automation<br>
<br>
<a href="http://www.filebot.net/cli.html">Filebot Command Line</a><br>
<br>
<h2>FileBot CLI setup</h2><br>
The download, unpacking and editing.<br>
<br>
<pre><code>wget -qO ~&#x2F;filebot.zip <a href="http://downloads.sourceforge.net/project/filebot/filebot/FileBot_4.6/FileBot_4.6-portable.zip">http:&#x2F;&#x2F;downloads.sourceforge.net&#x2F;project&#x2F;filebot&#x2F;filebot&#x2F;FileBot_4.6&#x2F;FileBot_4.6-portable.zip</a>
unzip -qo ~&#x2F;filebot.zip -d ~&#x2F;filebot &amp;&amp; rm -f ~&#x2F;filebot.zip</code></pre><br>
Now to run filebot you would do this, which will also show you the <code>-help</code> page to:<br>
<br>
<h2>FileBot CLI - usage</h2><br>
<pre><code>~&#x2F;filebot&#x2F;filebot.sh</code></pre><br>
<pre><code>~&#x2F;filebot&#x2F;bin&#x2F;filebot.sh -rename &quot;$HOME&#x2F;path&#x2F;to&#x2F;episodes&quot;</code></pre><br>
Use <code>&quot; &quot;</code> around paths. Use <code>$HOME</code> in paths instead of <code>~</code>. Filebot gets confused about the <code>~</code><br>
<br>
Please refer to this page: <a href="http://www.filebot.net/cli.html">Filebot Command Line</a> for more options. <br>
<br>
Scripts for media center automation can be found in <a href="http://www.filebot.net/forums/viewtopic.php?t=215">this</a> thread on the <a href="http://www.filebot.net/forums">Filebot forum</a>.<br>
<br>
<h2>Troubleshooting</h2><br>
If you have installed Java 8 as per the instructions at the top of this page and it still won&#x27;t work, please execute this command and try running filebot again:<br>
<br>
<pre><code>sed -i &quot;s|java -Dunix|~&#x2F;bin&#x2F;java -Dunix|g&quot; ~&#x2F;filebot&#x2F;filebot.sh</code></pre>
<br>