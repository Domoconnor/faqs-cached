<h1>How do I make thumbnails of video files</h1>

        
<strong><a href="http://moviethumbnail.sourceforge.net/">Movie Thumbnailer (mtn)</a></strong><br>
<br>
<pre><code>Movie thumbnailer (mtn) -- saves thumbnails (screenshots) of movie or video files to jpeg files. 
It uses FFmpeg&#x27;s libavcodec as its engine, so it supports all popular codecs, e.g. divx h264 mpeg1 mpeg2 mp4 vc1 wmv xvid, 
and formats, e.g. .3gp .avi .dat .mkv .wmv. mtn is open source software. It should run on all operating systems which have gcc, 
FFmpeg, and GD, for example, Linux and Windows.</code></pre><br>
This FAQ assumes you know how to <a href="https://www.feralhosting.com/faq/view?question=12">SSH</a> into your slot.<br>
<br>
<strong>1:</strong> Download <a href="http://moviethumbnail.sourceforge.net/">mtn</a> and extract mtn<br>
<br>
<strong>copy and paste this entire thing as one command, or break it into three at the &#x27;&amp;&amp;&#x27;s</strong><br>
<br>
<pre><code>wget <a href="http://sourceforge.net/projects/moviethumbnail/files/movie%20thumbnailer%20linux%20binary/mtn-200808a-linux/mtn-200808a-linux.tgz/download">http:&#x2F;&#x2F;sourceforge.net&#x2F;projects&#x2F;moviethumbnail&#x2F;files&#x2F;movie%20thumbnailer%20linux%20binary&#x2F;mtn-200808a-linux&#x2F;mtn-200808a-linux.tgz&#x2F;download</a> -O mtn.tar.gz &amp;&amp; tar xfvz mtn.tar.gz &amp;&amp; cd mtn-200808a-linux&#x2F;</code></pre><br>
<strong>2:</strong> Downloading the font files needed.<br>
&nbsp; <br>
We&#x27;ll use the free Liberation fonts from the Debian repo<br>
<br>
<strong>a:</strong> Download <br>
<br>
<pre><code>wget <a href="http://ftp.us.debian.org/debian/pool/main/f/fonts-liberation/fonts-liberation_1.07.4-1_all.deb">http:&#x2F;&#x2F;ftp.us.debian.org&#x2F;debian&#x2F;pool&#x2F;main&#x2F;f&#x2F;fonts-liberation&#x2F;fonts-liberation_1.07.4-1_all.deb</a></code></pre><br>
<strong>b:</strong> Extract the .deb<br>
<br>
<pre><code> ar x fonts-liberation_1.07.4-1_all.deb</code></pre><br>
<strong>c:</strong> Extract the data.tar.xz (where the font files are)<br>
<br>
<pre><code>tar xf data.tar.xz</code></pre><br>
In order to use <a href="http://moviethumbnail.sourceforge.net/">mtn</a>, you must supply the path to the font files we just downloaded because the servers have no fonts installed by default.<br>
<br>
Your commands will look something like this(I recommend adding an alias, see below):<br>
<br>
<pre><code>~&#x2F;mtn-200808a-linux&#x2F;mtn ~&#x2F;private&#x2F;rtorrent&#x2F;data&#x2F;movie.avi -f ~&#x2F;mtn-200808a-linux&#x2F;usr&#x2F;share&#x2F;fonts&#x2F;truetype&#x2F;liberation&#x2F;LiberationMono-Bold.ttf -c 3 -r 3 -s 600</code></pre><br>
The -f needs to be followed by the path to your font.tff file. The -c and -r are for number of columns and number of rows, respectively.&nbsp; -s takes the image every 600 seconds, until you&#x27;ve hit your r&#x2F;x limit.<br>
<br>
Gives you an image that looks like this: <br>
<br>
<img src="http://i.imgur.com/QYX3T.jpg"><br>
<br>
To simplify things you can add the following line to your <strong>~.bashrc</strong><br>
<br>
<pre><code>alias mtn=&quot;~&#x2F;mtn-200808a-linux&#x2F;mtn -f ~&#x2F;mtn-200808a-linux&#x2F;usr&#x2F;share&#x2F;fonts&#x2F;truetype&#x2F;liberation&#x2F;LiberationMono-Bold.ttf -c # -r # -s #&quot;</code></pre><br>
Be sure to replace the #&#x27;s with actual numbers, based on how you want the image to look.&nbsp; Or if you plan on using many different setups, remove the &quot;-c # -r # -s #&quot; and add those in when using the command.<br>
<br>
And then use the command by running<br>
<br>
<pre><code>mtn ~&#x2F;path&#x2F;to&#x2F;cute.kitties.awww.mp4</code></pre><br>
<br>
