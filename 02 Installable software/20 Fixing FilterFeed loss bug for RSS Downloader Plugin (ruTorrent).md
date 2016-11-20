<h1>Fixing Filter&#x2F;Feed loss bug for RSS Downloader Plugin (ruTorrent)</h1>

        
<br>
to fix this problem, I&#x27;ve spent some time figuring how the plugin works and after a few months of testing I&#x27;m finally releasing my fix to this problem<br>
<br>
<h2>1: what this fix exactly does:</h2><br>
when adding a new feed&#x2F;filter it creates a backup file automatically for either the feeds or the filters.<br>
<br>
these backup files are automatically updated when you add new or do changes to the feeds&#x2F;filters and when the feeds&#x2F;filters are correctly loaded<br>
<br>
in my tests so far i encountered some errors regarding the feeds&#x2F;filters but but haven&#x27;t lost any of the feeds or filters so far<br>
<br>
<h2>2: how to get this fix</h2><br>
you can either download the <code>rss.php</code> file from <a href="https://mega.co.nz/&#x23;&#x21;i01wlA7I&#x21;0q4l0jYnXTYVfI8ww-5bVsd8eOEWJ76kQZCpT-pZcGg">here</a> and replace your current <code>rss.php</code> in your rutorrent director<br>
I created this fix with rutorrent that you can install from your account manager.<br>
so I don&#x27;t know if this works with other version of rutorrent.<br>
<br>
or you can add the following parts by yourself<br>
<br>
<strong>2.1</strong> open your rss.php in your rutorrent directory.<br>
<br>
<strong>2.2</strong> got to line 821. there you will see &quot;public function rRSSManager()&quot;<br>
<br>
<strong>2.3</strong> in that function after the line with &quot;$this-&gt;cache&nbsp; = new rCache( &#x27;&#x2F;rss&#x2F;cache&#x27; );&quot;<br>
<br>
replace the following 3 lines<br>
<br>
<pre><code>$this-&gt;rssList = new rRSSMetaList();
$this-&gt;cache-&gt;get($this-&gt;rssList);
$this-&gt;rssList-&gt;resetErrors();</code></pre><br>
with<br>
<br>
<pre><code>$this-&gt;MetalListLoadAndBackup();</code></pre><br>
<strong>2.4</strong> once done go to line 831 add a line after it and add the following code<br>
<br>
<pre><code>private function MetalListLoadAndBackup() {
&nbsp; &nbsp; $this-&gt;rssList = new rRSSMetaList();

&nbsp; &nbsp; $name = $this-&gt;rssList-&gt;hash;
&nbsp; &nbsp; if($this-&gt;cache-&gt;get($this-&gt;rssList)) {
&nbsp; &nbsp; &nbsp; &nbsp; $this-&gt;rssList-&gt;hash = $name . &quot;_backup&quot;;
&nbsp; &nbsp; &nbsp; &nbsp; $this-&gt;cache-&gt;set($this-&gt;rssList);
&nbsp; &nbsp; &nbsp; &nbsp; $this-&gt;rssList-&gt;hash = $name;
&nbsp; &nbsp; } else {
&nbsp; &nbsp; &nbsp; &nbsp; $this-&gt;rssList-&gt;hash = $name . &quot;_backup&quot;;
&nbsp; &nbsp; &nbsp; &nbsp; $this-&gt;cache-&gt;get($this-&gt;rssList);
&nbsp; &nbsp; &nbsp; &nbsp; $this-&gt;rssList-&gt;hash = $name;
&nbsp; &nbsp; }
&nbsp; &nbsp; $this-&gt;rssList-&gt;resetErrors();
}</code></pre><br>
<strong>2.5</strong> now go to line 873 and add a new line after that and add the following<br>
<br>
<pre><code>private function FilterListLoadAndBackup() {
&nbsp; &nbsp; $flts = new rRSSFilterList();

&nbsp; &nbsp; $name = $flts-&gt;hash;
&nbsp; &nbsp; if($this-&gt;cache-&gt;get($flts)) {
&nbsp; &nbsp; &nbsp; &nbsp; $flts-&gt;hash = $name . &quot;_backup&quot;;
&nbsp; &nbsp; &nbsp; &nbsp; $this-&gt;cache-&gt;set($flts);
&nbsp; &nbsp; } else {
&nbsp; &nbsp; &nbsp; &nbsp; $flts-&gt;hash = $name . &quot;_backup&quot;;
&nbsp; &nbsp; &nbsp; &nbsp; $this-&gt;cache-&gt;get($flts);
&nbsp; &nbsp; }
&nbsp; &nbsp; $flts-&gt;hash = $name;
&nbsp; &nbsp; 
&nbsp; &nbsp; return $flts;
}</code></pre><br>
now we are almost there<br>
<br>
<strong>2.6</strong> on line 891 replace the following<br>
<br>
<pre><code>$flts = new rRSSFilterList();
&nbsp; &nbsp; &nbsp; &nbsp; $this-&gt;cache-&gt;get($flts);</code></pre><br>
with<br>
<br>
<pre><code>$flts = $this-&gt;FilterListLoadAndBackup();</code></pre><br>
now we are done... this should do the trick<br>
these functions will do the backup and load the backup if the actual file is corrupted (as explained at the top)<br>
<br>
