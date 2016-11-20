<h1>NCurses Disk Usage</h1>

        
Ncdu is a disk usage analyzer with an ncurses interface. It is designed to find space hogs on a remote server where you don&#x27;t have an entire graphical setup available, but it is a useful tool even on regular desktop systems. Ncdu aims to be fast, simple and easy to use, and should be able to run in any minimal POSIX-like environment with ncurses installed.<br>
<br>
You need to SSH into your slot to complete this guide. If you don&#x27;t know how to do this <a href="https://www.feralhosting.com/faq/view?question=12">here is a basic guide</a><br>
<br>
<h2>Automated Install</h2><br>
<pre><code>wget -qO ~&#x2F;ncdu.install <a href="http://git.io/vTwuq">http:&#x2F;&#x2F;git.io&#x2F;vTwuq</a> &amp;&amp; bash ~&#x2F;ncdu.install</code></pre><br>
<h2>Manual Install</h2><br>
Check to see if dependencies are installed:<br>
<br>
<pre><code>dpkg -s libncurses5-dev
dpkg -s libncursesw5-dev</code></pre><br>
If they are not, you will need to open a ticket for them to be installed before you continue.<br>
sample:<br>
<br>
<pre><code>Please can you install the libncurses5-dev libncursesw5-dev dependencies for NCDU?

<a href="https://packages.debian.org/en/wheezy/libncurses5-dev">https:&#x2F;&#x2F;packages.debian.org&#x2F;en&#x2F;wheezy&#x2F;libncurses5-dev</a>
<a href="https://packages.debian.org/en/wheezy/libncursesw5-dev">https:&#x2F;&#x2F;packages.debian.org&#x2F;en&#x2F;wheezy&#x2F;libncursesw5-dev</a>

apt-get install libncurses5-dev libncursesw5-dev

Thank you.</code></pre><br>
Now install NCurses Disk Usage using these commands:<br>
<br>
<pre><code>wget -qO ~&#x2F;ncdu-1.11.tar.gz <a href="http://dev.yorhel.nl/download/ncdu-1.11.tar.gz">http:&#x2F;&#x2F;dev.yorhel.nl&#x2F;download&#x2F;ncdu-1.11.tar.gz</a>
cd ~&#x2F; 
tar xvzf ncdu-1.11.tar.gz
cd ncdu-1.11
.&#x2F;configure --prefix=&quot;$HOME&quot;
make
make install
cd ~&#x2F;
rm -r ~&#x2F;ncdu-1.11*</code></pre><br>
If ~&#x2F;bin is already in your $PATH, then do this to run NCurses Disk Usage.<br>
<br>
<pre><code>ncdu ~&#x2F;</code></pre><br>
Otherwise, run it like this:<br>
<br>
<pre><code>~&#x2F;bin&#x2F;ncdu ~&#x2F;</code></pre><br>
<h2>Usage</h2><br>
Use the arrow keys, enter, and delete to navigate (or vim movement keys), and &#x27;q&#x27; to quit&quot;
<br>