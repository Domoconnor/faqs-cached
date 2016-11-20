<h1>SpiderOak</h1>

        
SpiderOak is an US based online backup and file hosting service that allows users to access, synchronize and share data using a cloud-based server.<br>
<br>
In SSH do these commands. Use this faq if you do not know how to SSH into your slot: <a href="https://www.feralhosting.com/faq/view?question=12">SSH basics - Putty</a><br>
<br>
Execute these commands:<br>
<br>
<pre><code>mkdir -p ~&#x2F;spideroak
wget -qO ~&#x2F;spideroak.deb &#x27;<a href="https://spideroak.com/getbuild?platform=ubuntu&#x26;arch=x86_64">https:&#x2F;&#x2F;spideroak.com&#x2F;getbuild?platform=ubuntu&amp;arch=x86_64</a>&#x27;
dpkg-deb -x ~&#x2F;spideroak.deb ~&#x2F;spideroak
cp -rf ~&#x2F;spideroak&#x2F;usr&#x2F;bin&#x2F;. ~&#x2F;spideroak
rm -rf ~&#x2F;spideroak&#x2F;etc ~&#x2F;spideroak&#x2F;usr ~&#x2F;spideroak.deb</code></pre><br>
These commands below will do required start-up script edits for you. There are 4 commands in total:<br>
<br>
<pre><code>sed -i &quot;3iSPIDEROAK_ROOT=$(ls -d $HOME&#x2F;spideroak)\n&quot; ~&#x2F;spideroak&#x2F;SpiderOakONE
sed -i &#x27;s|LD_LIBRARY_PATH=&quot;&#x2F;opt|LD_LIBRARY_PATH=&quot;$SPIDEROAK_ROOT&#x2F;opt|g&#x27; ~&#x2F;spideroak&#x2F;SpiderOakONE
sed -i &#x27;s|QT_PLUGIN_PATH=&quot;&#x2F;opt|QT_PLUGIN_PATH=&quot;$SPIDEROAK_ROOT&#x2F;opt|g&#x27; ~&#x2F;spideroak&#x2F;SpiderOakONE
sed -i &#x27;s|exec &quot;&#x2F;opt|exec &quot;$SPIDEROAK_ROOT&#x2F;opt|g&#x27; ~&#x2F;spideroak&#x2F;SpiderOakONE</code></pre><br>
<h3>Optionally you can do the start-up script edits manually:</h3><br>
<pre><code>ls -d $HOME&#x2F;spideroak</code></pre><br>
You will see a result like this:<br>
<br>
<pre><code>&#x2F;media&#x2F;DiskID&#x2F;home&#x2F;username&#x2F;spideroak</code></pre><br>
Edit the <code>~&#x2F;spideroak&#x2F;SpiderOak</code> startup script with a text editor. It will look like this:<br>
<br>
<pre><code>#!&#x2F;bin&#x2F;sh

LD_LIBRARY_PATH=&quot;&#x2F;opt&#x2F;SpiderOak&#x2F;lib:$LD_LIBRARY_PATH&quot;
export LD_LIBRARY_PATH
QT_PLUGIN_PATH=&quot;&#x2F;opt&#x2F;SpiderOak&#x2F;lib&#x2F;plugins&#x2F;&quot; ; export QT_PLUGIN_PATH
SpiderOak_EXEC_SCRIPT=$(cd <code>dirname $0</code> ; pwd)&#x2F;SpiderOak
export SpiderOak_EXEC_SCRIPT
exec &quot;&#x2F;opt&#x2F;SpiderOak&#x2F;lib&#x2F;SpiderOak&quot; &quot;$@&quot;</code></pre><br>
We must edit it to be like this:<br>
<br>
<pre><code>#!&#x2F;bin&#x2F;sh

SPIDEROAK_ROOT=&#x2F;media&#x2F;DiskID&#x2F;home&#x2F;username&#x2F;spideroak

LD_LIBRARY_PATH=&quot;$SPIDEROAK_ROOT&#x2F;opt&#x2F;SpiderOak&#x2F;lib:$LD_LIBRARY_PATH&quot;
export LD_LIBRARY_PATH
QT_PLUGIN_PATH=&quot;$SPIDEROAK_ROOT&#x2F;opt&#x2F;SpiderOak&#x2F;lib&#x2F;plugins&#x2F;&quot; ; export QT_PLUGIN_PATH
SpiderOak_EXEC_SCRIPT=$(cd <code>dirname $0</code> ; pwd)&#x2F;SpiderOak
export SpiderOak_EXEC_SCRIPT
exec &quot;$SPIDEROAK_ROOT&#x2F;opt&#x2F;SpiderOak&#x2F;lib&#x2F;SpiderOak&quot; &quot;$@&quot;</code></pre><br>
<strong>1:</strong> Create the new line using your result from the <code>ls -d $HOME&#x2F;spideroak</code> command: <code>SPIDEROAK_ROOT=&#x2F;media&#x2F;DiskID&#x2F;home&#x2F;username&#x2F;spideroak</code><br>
<strong>2:</strong> Edit the <code>LD_LIBRARY_PATH=&quot;...</code><br>
<strong>3:</strong> Edit the <code>QT_PLUGIN_PATH=&quot;...</code><br>
<strong>4:</strong> Edit the <code>exec &quot;...</code><br>
<br>
Then save the file, uploading and overwriting if necessary:<br>
<br>
<h3>SpiderOak First run.</h3><br>
You need to have already created an account on the website. If you have not already done so, please do this now here: <a href="https://spideroak.com/signup/">SpiderOak signup</a><br>
<br>
You also need to have set-up the application on your main device before setting it up on a Feral Slot. If you try to login before doing this you will get an error like this:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Software/SpiderOak/setuperror.png"><br>
<br>
Once you have done that then execute this command to configure SpiderOak:<br>
<br>
<pre><code>~&#x2F;spideroak&#x2F;SpiderOak --setup=-</code></pre><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Software/SpiderOak/setup1.png"><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Software/SpiderOak/setup2.png"><br>
<br>
When you install SpiderOak for the first time onto your machine you will create a &quot;device&quot;. This will be linked to your main account. In this example i have already configured other devices elsewhere.<br>
<br>
Leave this option blank when following this FAQ to create a new device, which we will call <strong>FeralSpider</strong> in this example.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Software/SpiderOak/setup3.png"><br>
<br>
After you have named your new device it will take some time to synchronise.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Software/SpiderOak/setup4.png"><br>
<br>
When you see this it is done.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Software/SpiderOak/setup5.png"><br>
<br>
<h3>Run SpiderOak in a screen:</h3><br>
Type this command<br>
<br>
<pre><code>screen -S SpiderOak</code></pre><br>
Once inside the screen type this:<br>
<br>
<pre><code>~&#x2F;spideroak&#x2F;SpiderOak --headless</code></pre><br>
You will get no result as shown in the below image. No error is a good thing. If you get an error re check the step in this FAQ for configuring the start up script.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Software/SpiderOak/screen.png"><br>
<br>
Press this keyboard sequence to detach from the screen<br>
<br>
<pre><code>ctrl a d</code></pre><br>
SpiderOak is now running on your slot.<br>
<br>
By default in v5 of SpiderOak it will be syncing to a newly created HIVE folder in your home&#x2F;root directory. You can find this folder at:<br>
<br>
<pre><code>~&#x2F;SpiderOak Hive</code></pre><br>
Anything you put in here will sync to your other devices Hive directory.<br>
<br>
<h3>Mini FAQ:</h3><br>
Q: Where are the configuration files stored?<br>
<br>
A: When you run the set-up a new, hidden directory is created at: <code>~&#x2F;.SpiderOak</code><br>
<br>
<h3>Useful links:</h3><br>
<a href="https://spideroak.com/faq/questions/67/how_can_i_use_spideroak_from_the_commandline/">Command Line Help</a><br>
<br>
<a href="https://spideroak.com/faq/">SpiderOak FAQs</a><br>
<br>
