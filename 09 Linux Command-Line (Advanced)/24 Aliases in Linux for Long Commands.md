<h1>Aliases in Linux for Long Commands</h1>

        
<br>
<h2>Aliases Overview</h2><br>
One of the great conveniences in Linux is the ability to set-up aliases for commands. When you have a command that you find yourself typing in frequently, it is a perfect candidate for an alias.<br>
<br>
For example, the command to check your used space is:<br>
<br>
<pre><code>du ~&#x2F; -s --si</code></pre><br>
 While some people have really good memories and can remember all the switches easily, I do not. So I created an alias for it, called <code>space</code>. Now all I have to type is the word <code>space</code> in the shell and it executes the long command for me.<br>
<br>
<h2>How to setup an Alias</h2><br>
To create an alias, you need to edit or create a file in your home directory, called <code>~&#x2F;.bash_aliases</code>. Notice that this file starts with a dot. You may already have some aliases there that were automatically created by the system or the administrator. In this file, you will enter your alias definition, one per line: <br>
<br>
Edit the file in <a href="https://www.feralhosting.com/faq/view?question=12">SSH</a> using this command:<br>
<br>
<pre><code>nano -w ~&#x2F;.bash_aliases</code></pre><br>
The copy and paste or type this on a new line:<br>
<br>
<pre><code>alias space=&#x27;du ~&#x2F; -s --si&#x27;</code></pre><br>
Notice the lack of spaces around the equal sign (=), and also the single quotes around the command itself (&#x27;) - those elements are very important for the alias to work properly. <br>
<br>
Save your file by pressing and holding <code>CTLR</code> then pressing <code>x</code>. To see the effect of the alias you just created, you can log off and back on, or, easier, type<br>
<br>
<pre><code>source ~&#x2F;.bash_aliases</code></pre><br>
Which forced the system to re-read that file as if you just logged freshly on. You could make that command an alias as well - you can call it <code>reload</code>: <br>
<br>
<pre><code>alias reload=&#x27;source ~&#x2F;.bash_aliases&#x27;</code></pre><br>
As you can see, all sorts of command can be made into aliases to make your life easier.<br>
<br>
Once you have some aliases created a really quick way to review them is to just type <code>alias</code> at the prompt - it will list your aliases for you.<br>
<br>
<strong>Important note:</strong> Alias names should not have spaces in them. You can use an underscore to make multi-word aliases, for example: <code>alias some_alias</code><br>
<br>
<h2>Some More Examples</h2><br>
Here is some of my <code>~&#x2F;.bash_aliases</code> file as an example. I will try to explain what each one does.<br>
<br>
<pre><code>alias ll=&#x27;ls -lh&#x27;</code></pre><br>
Tells the ls command to display file sizes in human readable form (KB&#x27;s and MB&#x27;s), and use the long format of file listing. <br>
<br>
<pre><code>alias la=&#x27;ls -lAh&#x27;</code></pre><br>
Same as above, but also will force the display of hidden files (starting with a dot)<br>
<br>
<pre><code>alias space=&#x27;du ~&#x2F; -s --si&#x27;</code></pre><br>
This command tells you the used space in your slice<br>
<br>
<pre><code>alias wspace=&#x27;watch -n 60 du ~&#x2F; -s --si&#x27;</code></pre><br>
This command displays an updating version of the command above. It will update every 60 seconds.<br>
<br>
<pre><code>alias speed=&#x27;bwm-ng&#x27;</code></pre><br>
This command will display a bandwidth meter for your server. <br>
<br>
These should get you started with the concept. There are many great resources on the web for more fun aliases.<br>
<br>
