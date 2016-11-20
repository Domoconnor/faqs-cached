<h1>Easily Split and Combine Large Files for Faster Parallel Transfers</h1>

        
<br>
You need to SSH to your slot to start&#x2F;complete this guide. Please see this <a href="https://www.feralhosting.com/faq/view?question=12">Basic SSH Guide</a><br>
<br>
Once in there, type this:<br>
<br>
<pre><code>split -b 5m .&#x2F;yourlargefile.avi</code></pre><br>
This will split it into several 5 megabyte files so that you can transfer it faster using parallel connections with an FTP&#x2F;SFTP client like FileZilla for significantly increased throughput. I prefer files around <code>5Mb</code>, but that&#x27;s really just preference. You can replace the 5 in the above line with any other number of megabytes you&#x27;d like, and&#x2F;or replace the <code>m</code> with a <code>k</code> for kilobytes.<br>
<br>
The naming conventions will be three-letter names all beginning with <code>x</code> by default. If you&#x27;d like to change the naming convention to where it starts with, say the word <code>new</code>, just add that to the end of the command that you entered. I&#x27;d recommend creating a temporary local folder where you can store all of them so that nothing gets mixed up once you&#x27;ve downloaded them all.<br>
<br>
Once you have the files on your computer, open Terminal and and cd into the directory where you put all of your files. Since they all begin with the letter <code>x</code>, you can type this, assuming you don&#x27;t have anything else in the directory beginning with that letter:<br>
<br>
<pre><code>cat x* &gt; thenameofyourcompletefile.avi</code></pre><br>
Give it a minute, and you&#x27;ll have a completely re-combined file.<br>
<br>
If, after the first step, you get an error saying something about file naming conventions being exhausted, that means that your file required more than 676 smaller files to be split into, assuming you&#x27;ve used the default naming convention. Consider choosing a larger piece size.<br>
<br>
