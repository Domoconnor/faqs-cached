<h1>FLAC to MP3 Conversion in Perl - Recursive</h1>

        
<br>
The listing below will recursively convert flac to mp3 and tags using flac, metaflac and lame. <br>
<br>
It is written in Perl and creates the files in a seperate directory tree and also copies across any artwork, so will handle multi discs and compilations. Probably not very elegant but it works :)<br>
<br>
Script URL: <br>
<br>
<pre><code>wget -qO ~&#x2F;convert.pl <a href="http://git.io/V1P_Dg">http:&#x2F;&#x2F;git.io&#x2F;V1P_Dg</a></code></pre><br>
Now you can use the script like this:<br>
<br>
<strong>Important note:</strong> Folder names with spaces will require that your wrap them in quotes, for example <code>&quot;folder name&quot;</code>.<br>
<br>
<pre><code>perl convert.pl foldername bitrate</code></pre><br>
<code>foldername</code> should be the full path as found in your ftp client, if it contains spaces it must be enclosed in quotes. <br>
<br>
<code>bitrate</code> can be any legitimate <code>bitrate</code> from <code>128</code> to <code>320</code> for constant <code>bitrates</code> and <code>V2</code>,<code>V0</code> for a variable bitrate.<br>
<br>
Constant bitrate options:<br>
<br>
<code>128</code><br>
<code>164</code><br>
<code>192</code><br>
<code>224</code><br>
<code>256</code><br>
<code>320</code><br>
<br>
Variable bitrate options:<br>
<br>
<code>V2</code><br>
<code>V0</code><br>
<br>
<h2>Usage example</h2><br>
<pre><code>perl convert.pl &quot;private&#x2F;rtorrent&#x2F;data&#x2F;my music folder&quot; 320</code></pre><br>
<br>
