<h1>Split a Large File into Multiple Smaller Sized Ones</h1>

        
This is a bash script that uses the Linux <code>dd</code> command to split files into several smaller files and then merge them together using the cat command.<br>
<br>
First off, to be able to use the script from any directory you might be in, the catalog where the script is in should be included in the PATH environment variable. The easiest way to make that happen is actually to create a bin folder in your home catalog and then put the script there. <br>
<br>
Make sure you are in your home catalog. Quickest way to do that is typing cd and pressing enter at the command line. Then create the bin catalog.<br>
<br>
<pre><code>mkdir -p ~&#x2F;bin
source ~&#x2F;.bashrc &amp;&amp; source ~&#x2F;.profile</code></pre><br>
<pre><code>nano –w ~&#x2F;bin&#x2F;fsplit</code></pre><br>
Copy and paste the following script into your nano:<br>
<br>
<pre><code>#! &#x2F;bin&#x2F;sh
#
# splits a binary file into chunks.
# Written 1995 by Frank Pihofer &lt;fp@fpx.de&gt;
# Modified 2009 by Freilantzer
#
FILE=00
COUNT=0
INPUT=
SIZE=
NAME=
#
if [ $# != 2 ] ; then
&nbsp; &nbsp; echo usage: $0 \[filename \| -\] \&lt;size in kb\&gt;
&nbsp; &nbsp; exit 1
fi
#
if [ &quot;$1&quot; = &quot;-m&quot; ] ; then
&nbsp; &nbsp; cat $2.part* &gt; $2
&nbsp; &nbsp; echo parts merged to $2
&nbsp; &nbsp; exit 0
fi
#
if [ &quot;$1&quot; = &quot;-&quot; ] ; then
&nbsp; &nbsp; INPUT=
else
&nbsp; &nbsp; INPUT=if=$1
fi
#
NAME=$1
SIZE=$2
VALUE=0
#
while dd $INPUT bs=1k skip=$COUNT count=$SIZE of=$NAME.part$FILE 2&gt; &#x2F;dev&#x2F;null ; do
#
if [ ! -s $NAME.part$FILE ] ; then
&nbsp; &nbsp; break;
fi
#
if [ &quot;$INPUT&quot; != &quot;&quot; ] ; then
&nbsp; &nbsp; COUNT=$(echo $COUNT + $SIZE | bc)
fi
#
FILE=$(echo $FILE + 1 | bc)
#
if [ &quot;$(echo $FILE | cut -c 1)&quot; = &quot;$FILE&quot; ] ; then
&nbsp; &nbsp; FILE=0$FILE
fi
#
done
#
rm -f xx$FILE
#</code></pre><br>
Then press and hold <code>CTRL</code> and then press <code>x</code> to save. Press <code>y</code> to confirm. After that you have to make the file executable by doing:<br>
<br>
<pre><code>chmod 700 ~&#x2F;bin&#x2F;fsplit</code></pre><br>
<h3>To split a file:</h3><br>
<pre><code>fsplit filename filesize-in-kbytes</code></pre><br>
<pre><code>fsplit mylargefile.ext 50000</code></pre><br>
This command would split the file <code>mylargefile.ext</code> into several smaller files with a size about <code>50 MByte</code>. They will be named <code>mylargefile.ext.part00</code> and so on. <br>
<br>
<strong>Important note:</strong> There is currently no feedback on progress. A large file will take minutes or more to split.<br>
<br>
<strong>TIP</strong><br>
<br>
To add the command to WinSCP Custom Commands, add this line:<br>
<br>
<pre><code>fsplit &quot;!&quot; &quot;!?File -S:?50000!&quot;</code></pre><br>
It will give you a pop-box where you can change the split size. <br>
For more WinSCP Custom Commands, please see <a href="https://www.feralhosting.com/faq/view?question=27">this FAQ</a>.<br>
<br>
To merge the files:<br>
<br>
<pre><code>fsplit –m original filename</code></pre><br>
<pre><code>fsplit –m mylargefile.ext</code></pre><br>
This command will merge files named <code>mylargefile.ext.part00</code> and so on to a file named <code>mylargefile.ext</code><br>
<br>
<h3>Using split</h3><br>
One more easy way is to use a command called <code>split</code> that is pre-installed command.<br>
<br>
<pre><code>split -b 50 -d mylargefile.ext</code></pre><br>
<br>
