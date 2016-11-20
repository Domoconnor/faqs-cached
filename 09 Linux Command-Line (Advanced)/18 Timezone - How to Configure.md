<h1>Timezone - How to Configure</h1>

        
<br>
Tired of seeing everything in the wrong timezone? irssi in particular annoyed me, so here&#x27;s a fix for everyone.<br>
<br>
To set your personal timezone on your slot for your user, use the following command.<br>
<br>
<pre><code>export TZ=&quot;&#x2F;usr&#x2F;share&#x2F;zoneinfo&#x2F;{zone-dir}&#x2F;{zone-file}&quot;</code></pre><br>
For example:<br>
<br>
<pre><code>export TZ=&quot;&#x2F;usr&#x2F;share&#x2F;zoneinfo&#x2F;Australia&#x2F;Adelaide&quot;</code></pre><br>
That will set the timezone until for this SSH session. <br>
<br>
To make it permanent, you can modify and use this command in SSH:<br>
<br>
<pre><code>echo &#x27;export TZ=&quot;&#x2F;usr&#x2F;share&#x2F;zoneinfo&#x2F;{zone-dir}&#x2F;{zone-file}&quot;&#x27; &gt;&gt; ~&#x2F;.bashrc</code></pre><br>
<strong>Important note:</strong> Don&#x27;t forget to edit it to match your timezone first.<br>
<br>
For example:<br>
<br>
<pre><code>echo &#x27;export TZ=&quot;&#x2F;usr&#x2F;share&#x2F;zoneinfo&#x2F;Europe&#x2F;London&quot;&#x27; &gt;&gt; ~&#x2F;.bashrc</code></pre><br>
Then type this and press enter to reload your shell:<br>
<br>
<pre><code>bash</code></pre><br>
Restart bash&#x2F;screen&#x2F;session and your timezone will be updated. <br>
<br>
This command will show you the timezone:<br>
<br>
<pre><code>date</code></pre><br>
If you are unsure of which timezone settings to use run this command:<br>
<br>
<pre><code>tzselect</code></pre><br>
And follow the prompts to find yours.<br>
<br>
