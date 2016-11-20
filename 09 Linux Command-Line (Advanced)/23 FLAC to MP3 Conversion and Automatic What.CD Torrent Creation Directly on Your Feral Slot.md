<h1>FLAC to MP3 Conversion and Automatic What.CD Torrent Creation Directly on Your Feral Slot</h1>

        
<br>
<strong>Important note:</strong> The scripts used in this tutorial are outdated, especially in their inability to correctly parse foreign characters. A more up-to-date script can be found at:<br>
<br>
<a href="https://github.com/RecursiveForest/whatmp3">http:&#x2F;&#x2F;github.com&#x2F;RecursiveForest&#x2F;whatmp3</a> <br>
<br>
Configuration and execution are very similar, with the exception that the word &quot;python&quot; should be substituted for &quot;perl&quot; in the instructions.<br>
<br>
<pre><code>wget -qO ~&#x2F;whatmp3 <a href="http://git.io/OfQ-bg">http:&#x2F;&#x2F;git.io&#x2F;OfQ-bg</a></code></pre><br>
For example:<br>
<br>
<pre><code>python whatmp3 some_arguments folder</code></pre><br>
<h2>Original FAQ:</h2><br>
This script requires <code>lame</code>, <code>flac</code> and <code>metaflac</code> be installed on the server (perl and rsync are installed by default on all servers).<br>
<br>
<h2>Testing Your Server for LAME, FLAC, and METAFLAC</h2><br>
<a href="https://www.feralhosting.com/faq/view?question=12">SSH to your server</a>, and type:<br>
<br>
<pre><code>lame</code></pre><br>
Then press <code>enter</code> to confirm. If you get a <code>command not found</code> message, this means LAME is not installed on the server.<br>
<br>
Then test your server for <code>flac</code> and <code>metaflac</code> (both lowercase).<br>
<br>
If any of them are missing, please <a href="https://www.feralhosting.com/manager/tickets/new">open a ticket</a> requesting them to be installed on your server.<br>
<br>
This guide assumes that you will be converting files residing in your rTorrent data dir. Converted files as well as the corresponding .torrent files for What.CD are to be found in the same location.<br>
<br>
<h2>Configuring the Script</h2><br>
Download the script in SSH using this command: <br>
<br>
<pre><code>wget -qO ~&#x2F;converter.pl <a href="http://git.io/S5BclQ">http:&#x2F;&#x2F;git.io&#x2F;S5BclQ</a></code></pre><br>
Using a text editor of your choice (if on Windows, may we suggest <a href="http://notepad-plus-plus.org/">notepad ++</a> and edit the following lines:<br>
<br>
<img src="https://raw.githubusercontent.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Linux%20Command-Line%20-%20Advanced/FLAC%20to%20MP3%20conversion%20and%20automatic%20What.CD%20torrent%20creation%20directly%20on%20your%20Feral%20slot/1.png"><br>
<br>
As the comment in the script explains, if set to 1 (equals <code>yes</code>), conversion will fail if the original .flac files you are converting from are not properly tagged. If you plan to convert files for your own use, consider setting this value to 0 (so that you can convert both tagged and untagged .flac files). However if you plan to upload your converted files to What.CD, please note that as per <a href="https://what.cd/rules.php?p=upload&#x23;h2.3">What.CD requirements</a> &quot;file names must accurately reflect the song titles. You may not have file names like 01track.mp3, 02track.mp3, etc. File names with incorrect song titles can be trumped by properly labeled torrents.&quot;<br>
<br>
Consider setting this value to 1 for What.CD uploads to make sure the converted MP3 files are named properly (the tradeback in this case is that you will not be able to convert untagged .flac files though).<br>
<br>
<img src="https://raw.githubusercontent.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Linux%20Command-Line%20-%20Advanced/FLAC%20to%20MP3%20conversion%20and%20automatic%20What.CD%20torrent%20creation%20directly%20on%20your%20Feral%20slot/2.png"><br>
<br>
Substitute the sample passkey with your actual What.CD passkey. Substitute <code>YOUR_USERNAME</code> in the path with your actual Feral username. Delete everything in between the quotes if you do not want to autocreate .torrents for the files you convert.<br>
<br>
You do not need to edit anything else. Save changes. Upload <code>converter.pl</code> to your rTorrent data dir:<br>
<br>
<pre><code>&#x2F;home&#x2F;YOUR_USERNAME&#x2F;private&#x2F;rtorrent&#x2F;data</code></pre><br>
<h2>Using the Script: Command Line</h2><br>
<a href="https://www.feralhosting.com/faq/view?question=12">SSH to your server</a> and copy and paste the following set of commands after the command prompt:<br>
<br>
<pre><code>cd ~&#x2F;private&#x2F;rtorrent&#x2F;data</code></pre><br>
This will transfer you to your rTorrent data dir.<br>
<br>
The script is to be run this way:<br>
<br>
<pre><code>perl converter.pl --v0 --320 &quot;NAME_OF_DIR&quot;</code></pre><br>
where <code>NAME_OF_DIR</code> is the name of the dir with the .flac files you want to convert (please note the use of double quotes).<br>
<br>
If the dir with your .flac files is called <code>Dry The River - The Chamblers &amp; The Valves 2009</code>, then the command you would use is:<br>
<br>
<pre><code>perl converter.pl --v0 --320 &quot;Dry The River - The Chamblers &amp; The Valves 2009&quot;</code></pre><br>
The command above will convert your files to MP3 v0, MP3 320, and create a private .torrent file for What.CD with your passkey in it, all in one go.<br>
<br>
If you want to convert to MP3 v0 only, use this command:<br>
<br>
<pre><code>perl converter.pl --v0 &quot;NAME_OF_DIR&quot;</code></pre><br>
If you want to convert to v2, use the <code>--v2</code> switch.<br>
<br>
Once the conversion is over, download your .torrent file to your local computer and upload it to What.CD (use the <code>Add format</code> link for that):<br>
<br>
<img src="https://raw.githubusercontent.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Linux%20Command-Line%20-%20Advanced/FLAC%20to%20MP3%20conversion%20and%20automatic%20What.CD%20torrent%20creation%20directly%20on%20your%20Feral%20slot/3.png"><br>
<br>
Then upload the .torrent to your rTorrent watch dir â€” rTorrent will hash check the files, and in a few seconds you will be seeding.<br>
<br>
<h2>SCRIPT LIMITATIONS:</h2><br>
<strong>does not handle multiple disc albums</strong>;<br>
<br>
(this <a href="http://rusak.pastebin.com/f7f2fa9f8">alternative script</a> can handle multiple disc albums perfectly, but doesn&#x27;t always play nice with WinSCP if that part is important to you; uses the same syntax as the one for the original script in this guide. Note that this alternate script does not handle files with single quote in the name, and the args are <code>--V0</code> &#x2F; <code>--V2</code> instead of <code>--v0</code> &#x2F; <code>--v2</code>)<br>
<br>
1: can only take 1 album at a time;<br>
<br>
2: cannot correctly label the .torrent of a Various Artist album (shouldn&#x27;t be a problem as the site will rename the .torrent anyway).<br>
<br>
<h2>Using the Script: WinSCP Custom Command</h2><br>
Please see our <a href="https://www.feralhosting.com/faq/view?question=27">WinSCP Guide</a> for more detailed instructions on how to configure custom commands in WinSCP.<br>
<br>
Since conversion may take up to a few minutes, you will need to increase the timeout setting in WinSCP. In the WinSCP Login configuration dialog, click on Connection in the left pane and set the server response timeout to 600 seconds as shown in the screenshot below.<br>
<br>
<img src="https://raw.githubusercontent.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Linux%20Command-Line%20-%20Advanced/FLAC%20to%20MP3%20conversion%20and%20automatic%20What.CD%20torrent%20creation%20directly%20on%20your%20Feral%20slot/4.png"><br>
<br>
Your custom command for converting to both v0 and 320 will be:<br>
<br>
<pre><code>perl converter.pl --v0 --320 &quot;!&quot;</code></pre><br>
<img src="https://raw.githubusercontent.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Linux%20Command-Line%20-%20Advanced/FLAC%20to%20MP3%20conversion%20and%20automatic%20What.CD%20torrent%20creation%20directly%20on%20your%20Feral%20slot/5.png"><br>
<br>
For converting just to v0:<br>
<br>
<pre><code>perl converter.pl --v0 &quot;!&quot;</code></pre><br>
<img src="https://raw.githubusercontent.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Linux%20Command-Line%20-%20Advanced/FLAC%20to%20MP3%20conversion%20and%20automatic%20What.CD%20torrent%20creation%20directly%20on%20your%20Feral%20slot/6.png"><br>
<br>
