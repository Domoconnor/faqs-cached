<h1>Get Help for Any Command in the Shell</h1>

        
<br>
There are a couple of different ways to get help with a command in Linux. This will be a brief overview of each method. You are encouraged to <a href="http://www.google.com">Google the internet</a> if you require more in-depth information on any command. There are some great resources out there, that we use ourselves, either for daily use, or for writing these FAQ&#x27;s.<br>
<br>
For help on connecting to the shell on your slot, please see <a href="https://www.feralhosting.com/faq/view?question=12">this FAQ</a>.<br>
<br>
The three ways of getting help for a command are:<br>
<br>
The Command Itself - command run without any options usually displays help on its usage<br>
The <code>-h</code> (or <code>--help</code>) switch - a switch that displays a quick and dirty version of help for the command<br>
The <code>man</code> (manual) command - the extensive and very detailed manual that is built into Linux.<br>
<br>
<br>
<strong>The Command Itself</strong><br>
<br>
Sometimes just running the command itself, without any switches or options, will give you information on how to use it. One example is the <code>unrar</code> command. When executed by itself in the shell, it gives the following output:<br>
<br>
<pre><code>UNRAR 3.90 freeware&nbsp; Copyright (c) 1993-2009 Alexander Roshal

Usage: unrar &lt;command&gt; -&lt;switch 1&gt; -&lt;switch N&gt; &lt;archive&gt; &lt;files...&gt;
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  &lt;@listfiles...&gt; &lt;path_to_extract\&gt;

&lt;Commands&gt;
&nbsp; e&nbsp; &nbsp; &nbsp; &nbsp;  Extract files to current directory
&nbsp; l[t,b]&nbsp; &nbsp; List archive [technical,bare]
&nbsp; p&nbsp; &nbsp; &nbsp; &nbsp;  Print file to stdout
&nbsp; t&nbsp; &nbsp; &nbsp; &nbsp;  Test archive files
&nbsp; v[t,b]&nbsp; &nbsp; Verbosely list archive [technical,bare]
&nbsp; x&nbsp; &nbsp; &nbsp; &nbsp;  Extract files with full path</code></pre><br>
(I have pasted only part of the output here, there are more options displayed.)<br>
<br>
For more information about the <code>unrar</code> command, please see <a href="https://www.feralhosting.com/heron/faq/view?question=36">this FAQ</a>.<br>
<br>
<strong>Important note</strong>: If the output scrolls off the screen before you have a chance to read it, you can simply scroll up, or use the <code>more</code> command to make it stop at each page-full:<br>
<br>
<pre><code>unrar | more</code></pre><br>
<code>|</code> - a pipe command that helps pass the output of one command to another<br>
more - a program that displays output one screen at a time<br>
unrar - the program whose output we are passing to more<br>
<br>
The output will stop when it reaches the bottom of your screen, and display a <code>--More--</code> prompt at the bottom. Use the <code>Spacebar</code> to go forward a full screen, or use <code>Enter key</code> to go forward one line at a time. Arrow keys also may work for up and down movement. Press the <code>Q key</code> to get back to the prompt without further scrolling.<br>
<br>
<h3>The help (-h) Switch</h3><br>
Almost all commands in Linux share a common switch for getting help for the command: <code>-h</code> (or <code>--help</code>). This is an agreed-upon standard by all program developers and should be present in each command. If one form does not work, try the other variant.<br>
<br>
Here is an example, using the <code>mktorrent</code> command:<br>
<br>
<pre><code>mktorrent -h</code></pre><br>
Will give something like:<br>
<br>
<pre><code>mktorrent 1.0 (c) 2007, 2009 Emil Renner Berthing

Usage: mktorrent [OPTIONS] &lt;target directory or filename&gt;

Options:
-a &lt;url&gt;[,&lt;url&gt;]* : specify the full announce URLs
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; at least one is required
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; additional -a adds backup trackers
-c &lt;comment&gt;&nbsp; : add a comment to the metainfo
-d&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; : don&#x27;t write the creation date
-h&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; : show this help screen
-l &lt;n&gt;&nbsp; &nbsp; &nbsp; &nbsp; : set the piece length to 2^n bytes,
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; default is 18, that is 2^18 = 256kb
-n &lt;name&gt;&nbsp; &nbsp;  : set the name of the torrent,
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; default is the basename of the target
-o &lt;filename&gt; : set the path and filename of the created file
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; default is &lt;name&gt;.torrent
-p&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; : set the private flag
-v&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; : be verbose</code></pre><br>
(I have trimmed some of the output to save space here.)<br>
<br>
As you can see, the help output gives you the syntax of the command (the order of options and switches in the command), as well as all of the options and switches that can be used when executing the command. For more info on using the <code>mktorrent</code> command, please see <a href="https://www.feralhosting.com/faq/view?question=71">this FAQ page</a>.<br>
<br>
<h3>The <code>man</code> Command</h3><br>
Linux includes a huge depository of help called <code>man</code> (short for <code>manual</code>). It is a way to store a software manuals on the system itself, without having to go to the web to locate the developer page. It covers nearly all of the common Linux commands.<br>
<br>
To use the man command, just prefix it to the command you want to know more about:<br>
<br>
<pre><code>man rtorrent</code></pre><br>
To navigate the man pages, the controls are similar to the <code>more</code> command from above:<br>
 <br>
Enter key - move forward by a single line<br>
Space bar - move forward by a whole screen<br>
Arrow keys - move up and down freely<br>
Pg Up + Pg Down - move up and down by whole screen freely<br>
Q key - quit the man session and go back to the prompt<br>
<br>
Please go here for more information about using rtorrent in <a href="https://www.feralhosting.com/faq/view?question=2">this FAQ</a>.<br>
<br>
I hope that this introduction will give you the skills and confidence to navigate the shell in Linux more comfortably.<br>
<br>
