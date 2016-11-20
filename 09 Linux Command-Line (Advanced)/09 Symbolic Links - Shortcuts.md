<h1>Symbolic Links - Shortcuts</h1>

        
<br>
<h2>Definition of Symlinks</h2><br>
What is a Symbolic Link?<br>
<br>
If you&#x27;ve ever made a &quot;Shortcut&quot; to a file in Windows, you will easily be able to understand the Linux equivalent (where &quot;aliases&quot; and &quot;shortcuts&quot; came from in the first place!), called a &quot;Symbolic Link&quot;. The easiest definition to understand is directly from the man page, A Symbolic Link is useful for maintaining multiple copies of a file in many places at once without using up storage for the &#x27;copies&#x27;; instead, a link &#x27;points&#x27; to the original copy.<br>
<br>
(If you want to read more about it, type <code>man ln</code> in the Terminal.)<br>
<br>
Let&#x27;s say you have a folder you need to get to and it is buried deep in your folders. You can simply type:<br>
<br>
<pre><code>cd &#x2F;some&#x2F;folder&#x2F;name&#x2F;deep&#x2F;inside&#x2F;other&#x2F;folders</code></pre><br>
For a real example on feral servers:<br>
<br>
<pre><code>cd ~&#x2F;www&#x2F;flatlinebb.mauve.feralhosting.com&#x2F;public_html&#x2F;</code></pre><br>
It can get annoying to type the long path every time.&nbsp; A symbolic link will solve the problem.<br>
<br>
To create the link, simply type the following:<br>
<br>
<pre><code>cd ~</code></pre><br>
(this will put you in your home folder)<br>
<br>
<pre><code>ln -s ~&#x2F;www&#x2F;flatlinebb.mauve.feralhosting.com&#x2F;public_html&#x2F; web_folder</code></pre><br>
That&#x27;s it. <code>ln -s</code> makes a new file called <code>web_folder</code> which points to the deeply buried folder <code>~&#x2F;www&#x2F;flatlinebb.mauve.feralhosting.com&#x2F;public_html&#x2F;</code>.<br>
I used an underscore, because Linux doesn&#x27;t like spaces, and then you can also complete the name of the folder just by typing we and hitting tab to have the system auto-complete it for you.<br>
<br>
To see that this worked, you can simply type:<br>
<br>
<pre><code>ls -l</code></pre><br>
You should see a line with the following text:<br>
<br>
<pre><code>web_folder -&gt; ~&#x2F;www&#x2F;flatlinebb.mauve.feralhosting.com&#x2F;public_html&#x2F;</code></pre><br>
The arrow shows you exactly what you did... A file named <code>web_folder</code> points to <code>~&#x2F;www&#x2F;flatlinebb.mauve.feralhosting.com&#x2F;public_html&#x2F;</code>.<br>
<br>
<strong>Important note:</strong> While this method can be used to put a data folder in the web directory, for http sharing with others, please use this faq to setup password protection for that folder:<br>
<br>
<a href="https://www.feralhosting.com/faq/view?question=20">Putting your WWW folder to use</a><br>
<a href="https://www.feralhosting.com/faq/view?question=22">Password protect your WWW folder</a><br>
<br>
<strong>Acknowledgment:</strong><br>
<br>
Parts of this tutorial have been inspired by <a href="http://www.macosxhints.com/article.php?story=2001110610290643">this site</a>.<br>
<br>
