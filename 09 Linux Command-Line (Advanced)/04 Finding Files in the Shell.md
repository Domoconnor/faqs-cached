<h1>Finding Files in the Shell</h1>

        
<br>
<h2>Find files</h2><br>
To find specific files by name in your home folder, use this command:<br>
<br>
<pre><code>find ~ -name &quot;name_of_file&quot;</code></pre><br>
<code>~</code> stands for your home folder, the same as <code>$HOME</code> or <code>&#x2F;home&#x2F;username</code><br>
<br>
Example:<br>
<br>
<pre><code>find ~ -name blueray</code></pre><br>
This will find all files with the word <code>blueray</code> in the name. You can use wildcards like * to search a partial name, like <code>blue*</code><br>
<br>
To find files by extension, use this command:<br>
<br>
<pre><code>find ~ -name &quot;*.given_extension&quot;</code></pre><br>
Example:<br>
<br>
<pre><code>find ~ -name &quot;*.jpg&quot;</code></pre><br>
This will show you all files, with the <code>.jpg</code> extension.<br>
<br>
There are many more uses and examples <a href="http://www.go2linux.org/usages-examples-of-find-command">here</a>.<br>
<br>
