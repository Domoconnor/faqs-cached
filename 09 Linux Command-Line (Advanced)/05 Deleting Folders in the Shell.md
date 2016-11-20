<h1>Deleting Folders in the Shell</h1>

        
<br>
<h2>Remove a folder:</h2><br>
To remove a whole folder, with files still in it, execute this command:<br>
<br>
<strong>Important note:</strong> You will need to use quotes for folder names with spaces. for example <code>&quot;some folder name&#x2F;&quot;</code><br>
<br>
<pre><code>rm -rfv foldername&#x2F;</code></pre><br>
<code>-r</code> is for recursive<br>
<code>-f</code> is for force removal<br>
<code>-v</code> is for verbose - shows that is being deleted (can be omitted)<br>
<br>
If the folder name has a space in it, use quotes around the folder name:<br>
<br>
<pre><code>rm -rfv &quot;some folder name&quot;</code></pre><br>
<h2>Remove a file:</h2><br>
<pre><code>rm -fv filename</code></pre><br>
<h2>Notes:</h2><br>
The above commands are relative. This means that they will look for the file from where your current location in the shell is. Generally this is the safe way to remove files to prevent accidentally deleting important files or folders. The default after a successful login is your <code>$HOME</code> folder or slot root.<br>
<br>
For example:<br>
<br>
<strong>Warning:</strong> This command would delete the entire contents of your slot. because we used <code>~&#x2F;</code>. That is bad, do not use this.<br>
<br>
<pre><code>rm -rf ~&#x2F;</code></pre><br>
So it is recommended you <code>cd</code> to a location then remove the files you want to delete.<br>
<br>
For example:<br>
<br>
<pre><code>cd ~&#x2F;private&#x2F;rtorrent&#x2F;data</code></pre><br>
Then delete your files or folders<br>
<br>
<pre><code>rm -rf &quot;some folder name&quot;</code></pre><br>
<br>
