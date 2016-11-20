<h1>Check your disk quota in SSH</h1>

        
In SSH do the commands described in this FAQ. If you do not know how to SSH into your slot use this FAQ: <a href="https://www.feralhosting.com/faq/view?question=12">SSH basics - Putty</a><br>
<br>
<h3>The easy way</h3><br>
Run the below command in SSH, it will output your disk usage.<br>
<br>
For less than <code>1TB</code> results<br>
<br>
<pre><code>du -s --si ~&#x2F;</code></pre><br>
For more than <code>1TB</code> results<br>
<br>
<pre><code>du -sB GB ~&#x2F;</code></pre><br>
For a list, sorted by size, of the files&#x2F;folders in the current directory use:<br>
<br>
<pre><code>du -s --si * | sort -h</code></pre><br>
<h3>The prettier way</h3><br>
<img src="http://idzr.org/w7tn?.png"><br>
<br>
<strong>Step 1:</strong> SSH into your slot.<br>
<br>
First, run the command the matches your slot type, then move to Step 2:<br>
&nbsp; <br>
For instance, for a <code>Helium-4</code> run you would run <code>echo &#x27;400000&#x27; &gt;&gt; ~&#x2F;.quotaspace</code><br>
<br>
Helium-3<br>
<br>
<pre><code>echo -n &#x27;333000&#x27; &gt; ~&#x2F;.quotaspace</code></pre><br>
Helium-4<br>
 <br>
<pre><code>echo -n &#x27;400000&#x27; &gt; ~&#x2F;.quotaspace</code></pre><br>
Helium-5<br>
<br>
<pre><code>echo -n &#x27;500000&#x27; &gt; ~&#x2F;.quotaspace</code></pre><br>
Helium-6<br>
<br>
<pre><code>echo -n &#x27;500000&#x27; &gt; ~&#x2F;.quotaspace</code></pre><br>
Helium-7<br>
<br>
<pre><code>echo -n &#x27;666000&#x27; &gt; ~&#x2F;.quotaspace</code></pre><br>
Helium-8<br>
<br>
<pre><code>echo -n &#x27;1000000&#x27; &gt; ~&#x2F;.quotaspace</code></pre><br>
Neon-3<br>
<br>
<pre><code>echo -n &#x27;500000&#x27; &gt; ~&#x2F;.quotaspace</code></pre><br>
Neon-4 <br>
<br>
<pre><code>echo -n &#x27;600000&#x27; &gt; ~&#x2F;.quotaspace</code></pre><br>
Neon-5<br>
<br>
<pre><code>echo -n &#x27;750000&#x27; &gt; ~&#x2F;.quotaspace</code></pre><br>
Neon-6<br>
<br>
<pre><code>echo -n &#x27;750000&#x27; &gt; ~&#x2F;.quotaspace</code></pre><br>
Neon-7<br>
<br>
<pre><code>echo -n &#x27;1000000&#x27; &gt; ~&#x2F;.quotaspace</code></pre><br>
Neon-8<br>
<br>
<pre><code>echo -n &#x27;1500000&#x27; &gt; ~&#x2F;.quotaspace</code></pre><br>
Argon-3<br>
<br>
<pre><code>echo -n &#x27;666000&#x27; &gt; ~&#x2F;.quotaspace</code></pre><br>
Argon-4<br>
<br>
<pre><code>echo -n &#x27;800000&#x27; &gt; ~&#x2F;.quotaspace</code></pre><br>
Argon-5<br>
<br>
<pre><code>echo -n &#x27;1000000&#x27; &gt; ~&#x2F;.quotaspace</code></pre><br>
Argon-6<br>
<br>
<pre><code>echo -n &#x27;1000000&#x27; &gt; ~&#x2F;.quotaspace</code></pre><br>
Argon-7<br>
<br>
<pre><code>echo -n &#x27;1333000&#x27; &gt; ~&#x2F;.quotaspace</code></pre><br>
Argon-8<br>
<br>
<pre><code>echo -n &#x27;2000000&#x27; &gt; ~&#x2F;.quotaspace</code></pre><br>
Xenon-3<br>
<br>
<pre><code>echo -n &#x27;1000000&#x27; &gt; ~&#x2F;.quotaspace</code></pre><br>
Xenon-4<br>
<br>
<pre><code>echo -n &#x27;1200000&#x27; &gt; ~&#x2F;.quotaspace</code></pre><br>
Xenon-5<br>
<br>
<pre><code>echo -n &#x27;1500000&#x27; &gt; ~&#x2F;.quotaspace</code></pre><br>
Xenon-6<br>
<br>
<pre><code>echo -n &#x27;1500000&#x27; &gt; ~&#x2F;.quotaspace</code></pre><br>
Xenon-7<br>
<br>
<pre><code>echo -n &#x27;2000000&#x27; &gt; ~&#x2F;.quotaspace</code></pre><br>
Krypton-8<br>
<br>
<pre><code>echo -n &#x27;3000000&#x27; &gt; ~&#x2F;.quotaspace</code></pre><br>
Radon-4<br>
<br>
<pre><code>echo -n &#x27;3000000&#x27; &gt; ~&#x2F;.quotaspace</code></pre><br>
Radon-7<br>
<br>
<pre><code>echo -n &#x27;5000000&#x27; &gt; ~&#x2F;.quotaspace</code></pre><br>
Radon-8<br>
<br>
<pre><code>echo -n &#x27;8000000&#x27; &gt; ~&#x2F;.quotaspace</code></pre><br>
<h2>SSD Slots</h2><br>
Neon<br>
<br>
<pre><code>echo -n &#x27;150000&#x27; &gt; ~&#x2F;.quotaspace</code></pre><br>
Argon<br>
<br>
<pre><code>echo -n &#x27;200000&#x27; &gt; ~&#x2F;.quotaspace</code></pre><br>
Krypton<br>
<br>
<pre><code>echo -n &#x27;300000&#x27; &gt; ~&#x2F;.quotaspace</code></pre><br>
Xenon<br>
<br>
<pre><code>echo -n &#x27;600000&#x27; &gt; ~&#x2F;.quotaspace</code></pre><br>
Radon<br>
<br>
<pre><code>echo -n &#x27;1200000&#x27; &gt; ~&#x2F;.quotaspace</code></pre><br>
<strong>Step 2:</strong> After SSHing into your slot, run the following the commands<br>
<br>
<pre><code>mkdir -p ~&#x2F;bin
wget -qO ~&#x2F;bin&#x2F;quota <a href="http://git.io/FolBxw">http:&#x2F;&#x2F;git.io&#x2F;FolBxw</a>
chmod 700 ~&#x2F;bin&#x2F;quota
source ~&#x2F;.bashrc &amp;&amp; source ~&#x2F;.profile</code></pre><br>
Now running the command:<br>
<br>
<pre><code>quota</code></pre><br>
In SSH will give you your disk quota.<br>
<br>
