<h1>Mollify - yet another web-based file manager</h1>

        
<strong>Important note:</strong> Apache only<br>
<br>
<h2>What is Mollify?</h2><br>
Mollify is a web file manager for publishing and managing files hosted in a web server of your choice. Different users can have access to different files and with different permissions.<br>
<br>
User interface is simple and intuitive, and it is totally customizable. See Features for complete list of features.<br>
<br>
Mollify is published with GPLv2 license. For details and commercial license, see license.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Software/Mollify%20-%20yet%20another%20web-based%20file%20manager/example.png"><br>
<br>
<h2>Features</h2><br>
<a href="http://www.mollify.org/features.php">http:&#x2F;&#x2F;www.mollify.org&#x2F;features.php</a><br>
<br>
<h2>Installation</h2><br>
2.1: Move to the WWW root using this command via SSH<br>
<br>
<pre><code>cd ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;</code></pre><br>
2.2: Download and unzip the file using wget and zip via SSH using this command <br>
<br>
<pre><code>wget -qO mollify.zip <a href="http://www.mollify.org/download/latest.php">http:&#x2F;&#x2F;www.mollify.org&#x2F;download&#x2F;latest.php</a>
unzip -qo mollify.zip &amp;&amp; rm -f mollify.zip</code></pre><br>
2.3: Create and open a file called <code>configuration.php</code> using this command: <br>
<br>
<pre><code>nano -w mollify&#x2F;backend&#x2F;configuration.php</code></pre><br>
For a very simple and fast setup just copy and paste this:<br>
<br>
<pre><code>&lt;?php
$CONFIGURATION = array(
&nbsp; &nbsp; &quot;db&quot; =&gt; array(
&nbsp; &nbsp; &nbsp; &nbsp; &quot;type&quot; =&gt; &quot;sqlite3&quot;,
&nbsp; &nbsp; &nbsp; &nbsp; &quot;file&quot; =&gt; &quot;my.db&quot;
&nbsp; &nbsp; )
);
?&gt; </code></pre><br>
Then press and hold <code>CTRL</code> and then press <code>x</code> to save. Press <code>y</code> to confirm.<br>
<br>
You are now ready to create an admin account and start using mollify. The wizard can be accessed from the following link:<br>
<br>
<pre><code><a href="http://server.feralhosting.com/user/mollify/backend/install/">http:&#x2F;&#x2F;server.feralhosting.com&#x2F;user&#x2F;mollify&#x2F;backend&#x2F;install&#x2F;</a></code></pre><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Software/Mollify%20-%20yet%20another%20web-based%20file%20manager/2.png"><br>
<br>
<h2>Installation options.</h2><br>
<strong>Important note:</strong> There is commas at the end of each line are important in the configuration file and are required except for the last. Make sure each line insdie the <code>&quot;db&quot; =&gt; array( )</code> is terminated with a&nbsp; <code>,</code> except for the last line. For example:<br>
<br>
<pre><code>&quot;db&quot; =&gt; array(
&quot;type&quot; =&gt; &quot;&quot;,
&quot;user&quot; =&gt; &quot;&quot;,
&quot;password&quot; =&gt; &quot;&quot;,
&quot;table_prefix&quot; =&gt; &quot;&quot;
)</code></pre><br>
<h3>Using mysql:</h3><br>
1: It is required you have installed MySQL via your Manager for the relevant slot. Use this FAQ - <a href="https://www.feralhosting.com/faq/view?question=6">Installing Software</a><br>
<br>
2: It is suggested you create a limited user following this FAQ <a href="https://www.feralhosting.com/faq/view?question=116">adminer</a>. This is an optional but recommended step, to create a limited user.<br>
<br>
Once you have done both of these steps you can continue to install Mollify using MySQL<br>
<br>
1: You will need to change the <code>SOCKETPATH</code> with the path to your MySQL socket found on the Slot details page for the relevant slot.<br>
2: You will need to use a valid MySQL username and replace <code>USERNAME</code> with your username.<br>
3: You will need to use this users&#x27; password and replace <code>PASSWORD</code> with this users password.<br>
<br>
<pre><code>&lt;?php
$CONFIGURATION = array(
&nbsp; &nbsp; &quot;db&quot; =&gt; array(
&nbsp; &nbsp; &nbsp; &nbsp; &quot;type&quot; =&gt; &quot;mysql&quot;,
&nbsp; &nbsp; &nbsp; &nbsp; &quot;user&quot; =&gt; &quot;USERNAME&quot;,
&nbsp; &nbsp; &nbsp; &nbsp; &quot;password&quot; =&gt; &quot;PASSWORD&quot;,
&nbsp; &nbsp; &nbsp; &nbsp; &quot;socket&quot; =&gt; &quot;&#x2F;media&#x2F;DiskID&#x2F;home&#x2F;username&#x2F;private&#x2F;mysql&#x2F;socket&quot;,
&nbsp; &nbsp; &nbsp; &nbsp; &quot;database&quot; =&gt; &quot;mollify&quot;,
&nbsp; &nbsp; &nbsp; &nbsp; &quot;table_prefix&quot; =&gt; &quot;mollify_&quot;,
&nbsp; &nbsp; &nbsp; &nbsp; &quot;charset&quot; =&gt; &quot;utf8&quot;
&nbsp; &nbsp; )
);
?&gt; </code></pre><br>
<br>
