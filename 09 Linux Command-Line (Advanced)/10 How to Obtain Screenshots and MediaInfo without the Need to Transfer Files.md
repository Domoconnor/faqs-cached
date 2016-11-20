<h1>How to Obtain Screenshots and MediaInfo without the Need to Transfer Files</h1>

        
You need to SSH top your slot to start&#x2F;complete this guide. Please see this <a href="https://www.feralhosting.com/faq/view?question=12">Basic SSH Guide</a><br>
<br>
Now that you&#x27;ve logged in, you need to navigate to your downloads directory. This can be done by <br>
<br>
<pre><code>cd Path&#x2F;to&#x2F;your&#x2F;downloads&#x2F;Directory_name</code></pre><br>
Don&#x27;t type the whole name, just the first few letters and press tab. Let autocomplete do the job for you. Now that you&#x27;re in your downloads directory, the terminal should say something like this: <br>
<br>
<pre><code>&#x2F;media&#x2F;sdb1&#x2F;home&#x2F;belligerant&#x2F;private&#x2F;rtorrent&#x2F;data</code></pre><br>
<strong>1: To prepare mediainfo:</strong> <br>
 <br>
<pre><code>mediainfo filename.avi &gt; filename.txt</code></pre><br>
You&#x27;ll find filename.txt in the folder you ran the command in. Remember, autocomplete is your friend. <br>
<br>
<strong>2: To prepare Screenshots:</strong> <br>
<br>
<strong>Important note:</strong>&nbsp; You can use <a href="https://www.feralhosting.com/faq/view?question=268">Static ffmpeg builds</a> if needed.)<br>
<br>
<pre><code>ffmpeg -ss 00:05:00 -i &quot;Filename.avi&quot; -vframes 1 -y -f image2 &quot;screenshot1.png&quot;
ffmpeg -ss 00:10:00 -i &quot;Filename.avi&quot; -vframes 1 -y -f image2 &quot;screenshot2.png&quot;
ffmpeg -ss 00:15:00 -i &quot;Filename.avi&quot; -vframes 1 -y -f image2 &quot;screenshot3.png&quot;</code></pre><br>
or<br>
<br>
<strong>Important note:</strong> If <code>mplayer</code> shows <code>command not found</code> you will need to open a ticket and ask staff to install it.<br>
<br>
<pre><code>mplayer &quot;Filename.avi&quot; -nosound -vo png:z=0 -ss 360 -frames 1
mplayer &quot;Filename.avi&quot; -nosound -vo png:z=0 -ss 600 -frames 1
mplayer &quot;Filename.avi&quot; -nosound -vo png:z=0 -ss 900 -frames 1</code></pre><br>
(You will need a FTP Client to download the screens and mediainfo.txt)<br>
<br>
<strong>Important note:</strong> Folder names with spaces will require that your wrap them in quotes, for example <code>&quot;folder name&quot;</code><br>
<br>
