<h1>Creating and Checking SFV or MD5 Hash Files</h1>

        
To check and create hash-check files on your slice use the cfv program. It works with, and creates standard .sfv and .md5 files that many downloads come with. It should be installed on your server already, but if it&#x27;s missing, please <a href="http://www.feralhosting.com/heron/manager/support/">open a ticket</a> requesting it.<br>
<br>
To check files, run this command in the folder that contains the .sfv file (it will look for the .sfv file automatically):<br>
<br>
<pre><code>cfv</code></pre><br>
<br>
To create a hash file, run this command in the folder that contains the files you want to hash (it will create a .sfv file with the name of the folder you are currently in as its filename): <br>
<br>
<pre><code>cfv -C -t sfv *</code></pre><br>
<br>
-C â€” is for &quot;create mode&quot;;<br>
-t â€” sets the file type to create (.sfv in this case);<br>
* â€” will select all files withint the folder.<br>
<br>
For more help with the cfv command, including which other file types it supports, please type this to get the build-in help:<br>
<br>
<pre><code>cfv --help</code></pre><br>
<br>
or for more in depth guide:<br>
<br>
<pre><code>man cfv</code></pre><br>
<br>