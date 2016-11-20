<h1>Making a Torrent in the Shell</h1>

        
<br>
<h2>Make a torrent</h2><br>
To make a .torrent file using command line, execute this command:<br>
<br>
<pre><code>mktorrent -v -p -l 21 -a <a href="http://tracker.url">http:&#x2F;&#x2F;tracker.url</a> -o filename.torrent folder_name</code></pre><br>
<code>-v</code> is for verbose<br>
<code>-p</code> is for private, as in not DHT or PeerExchange<br>
<code>-l</code> is for piece length (or size) for the torrent. It&#x27;s <code>2^n</code> bytes, so <code>-l 21</code> would create a <code>2^21 =2MB</code> piece size (<code>22=4MB</code> and <code>23=8MB</code>). Try to keep total of <code>1000</code> to <code>2000</code> pieces. Increase piece size if needed. <br>
<code>-a</code> is for tracker, the tracker URL follows (one is required; additional <code>-a</code> commands add backup trackers)<br>
<code>-o</code> is for output, the torrent file name follows<br>
<br>
<strong>Important note:</strong> The command needs to be all in one line, and quotes must be used around the folder name if it contains spaces.<br>
<br>
<h2>Example usage</h2><br>
If I wanted to make a torrent for What.cd from the data in the <code>VA - Summer Trance 2009</code> directory I already have on my server, I would go into the data folder:<br>
<br>
<pre><code>cd private&#x2F;tranmission&#x2F;data</code></pre><br>
 <br>
Then type the following command:<br>
<br>
<pre><code>mktorrent -v -p -l 21 -a <a href="http://tracker.what.cd:34000/xxxXXXxxx/announce">http:&#x2F;&#x2F;tracker.what.cd:34000&#x2F;xxxXXXxxx&#x2F;announce</a> -o VA-Summer_Trance_2009.torrent &quot;VA - Summer Trance 2009&quot;</code></pre><br>
Please note that you <strong>must</strong> use quotes if the target dir name contains spaces.<br>
<br>
<strong>Changing the piece-size</strong><br>
<br>
The default piece-size is <code>256kb</code>, which is too small for many files&#x2F;filepacks. (It results in bloated .torrent files and a lot of extra, unnecessary announce traffic.) The command to change the piece size is &#x27;-l XX&#x27; (that&#x27;s a lowercase &quot;L&quot;), according to the following values:<br>
<br>
<code>-l 18</code> = <code>256kb</code> piece-size (for filesizes under <code>512MB</code>)<br>
<code>-l 19</code> = <code>512kb</code> piece-size (for filesizes from <code>512MB</code> to <code>1024MB</code> &#x2F; <code>1GB</code>)<br>
<code>-l 20</code> = <code>1MB</code> (<code>1024kb</code>) piece-size (for filesizes from <code>1GB</code> to <code>2GB</code>)<br>
<code>-l 21</code> = <code>2MB</code> (<code>2048kb</code>) piece-size (for filesizes from <code>2GB</code> to <code>4GB</code>)<br>
<code>-l 22</code> = <code>4MB</code> (<code>4096kb</code>) piece-size (for filesizes from <code>4GB</code> to <code>8GB</code>)<br>
<code>-l 23</code> = <code>8MB</code> (<code>8192kb</code>) piece-size (for filesizes from <code>8GB</code> to <code>16GB</code>)<br>
<code>-l 24</code> = <code>16MB</code> (<code>16384kb</code>) piece-size (for filesizes above <code>16GB</code>)<br>
<br>
So, using the above example, the command to change the piece-size from the default <code>256kb</code> to <code>4MB</code> would be:<br>
<br>
<pre><code>mktorrent -v -p -l 22 -a <a href="http://tracker.what.cd:34000/xxxXXXxxx/announce">http:&#x2F;&#x2F;tracker.what.cd:34000&#x2F;xxxXXXxxx&#x2F;announce</a> -o VA-Summer_Trance_2009.torrent &quot;VA - Summer Trance 2009&quot;</code></pre><br>
<h2>Automate .torrent creation with a script</h2><br>
If you do this a lot, it might make sense to use the script below to automate things. To keep things simple, I suggest creating one shell script for each tracker that you are using on a regular basis. To stick with the example above, create a file mk-what-torrent.sh in your home directory, make it executable and open it in the nano editor<br>
<br>
<pre><code>echo -n &#x27;&#x27; &gt; ~&#x2F;mk-what-torrent.sh</code></pre><br>
<pre><code>chmod 700 ~&#x2F;mk-what-torrent.sh</code></pre><br>
<pre><code>nano ~&#x2F;mk-what-torrent.sh</code></pre><br>
Paste this code into the file, changing the tracker&#x27;s announce URL to what you actually need (also, remove the <code>-p</code> flag if your tracker is not a private tracker):<br>
<br>
<pre><code>#!&#x2F;bin&#x2F;sh
for i in &quot;$@&quot;; do
&nbsp; &nbsp;  mktorrent -v -p -a announce.url&#x2F;here -o &quot;$i.torrent&quot; &quot;$i&quot;
done</code></pre><br>
Once you have copied the code into the file press and hold <code>CTRL</code> and then press <code>x</code> to save. Press <code>y</code> to confirm.<br>
<br>
Then (optionally), edit your <code>~&#x2F;.bash_aliases</code> file<br>
<br>
<pre><code>nano ~&#x2F;.bash_aliases</code></pre><br>
Adding the line<br>
<br>
<pre><code>alias mk-what-torrent=&#x27;~&#x2F;mk-what-torrent.sh&#x27;</code></pre><br>
Then press and hold <code>CTRL</code> and then press <code>x</code> to save. Press <code>y</code> to confirm. Now restart bash using this command:<br>
<br>
<pre><code>bash </code></pre><br>
Now our new bash command&nbsp; <code>mk-what-torrent</code> is available for use via the alias. Now you can just navigate anywhere in your filesystem and create torrents for files and folders using wildcards. For example, <code>mk-what-torrent D*</code> will create torrent files (for what) of all files and folders starting with D in the current directory. <br>
<br>

