<h1>Icecast - streaming media server</h1>

        
In SSH do the commands described in this FAQ. If you do not know how to SSH into your slot use this FAQ: <a href="https://www.feralhosting.com/faq/view?question=12">SSH basics - Putty</a><br>
<br>
Your FTP &#x2F; SFTP &#x2F; SSH login information can be found on the Slot Details page for the relevant slot. Use this link in your Account Manager to access the relevant slot:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/slot_detail_link.png"><br>
<br>
You login information for the relevant slot will be shown here:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/slot_detail_ssh.png"><br>
<br>
<h2>Installing Icecast On To Your Feralhosting Slice!</h2><br>
<strong>0:</strong> Make sure you have enough time to do this. It can take from a couple minutes, to a couple hours! Hopefully this guide will keep it to a couple minutes! <br>
<br>
<strong>1:</strong> SSH in to your Feral slice<br>
<br>
<strong>2:</strong> Run this:<br>
<br>
<pre><code>svn co -q <a href="http://svn.xiph.org/icecast/trunk/icecast">http:&#x2F;&#x2F;svn.xiph.org&#x2F;icecast&#x2F;trunk&#x2F;icecast</a> ~&#x2F;icecast</code></pre><br>
This will download icecast SVN, you do not have to use the SVN.<br>
<br>
<strong>3:</strong> Once this has finished cd to your icecast folder:<br>
<br>
<pre><code>mkdir -p ~&#x2F;private&#x2F;icecast&#x2F;var&#x2F;log&#x2F;icecast &amp;&amp; cd ~&#x2F;icecast</code></pre><br>
<strong>4:</strong> Now, run autogen: <br>
<br>
<pre><code>.&#x2F;autogen.sh --prefix=&quot;$HOME&#x2F;private&#x2F;icecast&quot;</code></pre><br>
Where the prefix is the location you want to install icecast to. If you are following along with this guide for the first time or you are unsure of what to put at the prefix, simply use the provided command.<br>
<br>
<strong>Note:</strong> If you see a compilation error at the stage, please open a support ticket and request the following packages to be installed: libxslt1-dev libogg-dev libvorbis-dev<br>
<br>
<strong>5:</strong> Now we need to make, simply type: <br>
<br>
<pre><code>make &amp;&amp; make install</code></pre><br>
<strong>6:</strong> After &quot;make&quot; finishes, we need to run <br>
<br>
We should receive no errors. However, if you do receive a permissions error check your prefix that we set in step 5!<br>
<br>
<strong>7:</strong> After &quot;make install&quot; finishes you need to edit your &quot;icecast.xml&quot; to your liking, I will not cover editing that here, you can look elsewhere online on editing your &quot;icecast.xml&quot;. You can edit this via the ssh tunnel you have open or just open it directly in an FTP client then saving it back to the server. This file can be found in the folder:<br>
<br>
<pre><code>~&#x2F;private&#x2F;icecast&#x2F;etc&#x2F;icecast.xml</code></pre><br>
<strong>8:</strong> Now we need to run icecast on our server. First navigate to the bin folder: <br>
<br>
Now use this command to run the server: <br>
<br>
<pre><code>~&#x2F;private&#x2F;icecast&#x2F;bin&#x2F;.&#x2F;icecast -c ~&#x2F;private&#x2F;icecast&#x2F;etc&#x2F;icecast.xml</code></pre><br>
This will start our icecast server using the configuration file you set up in step five.<br>
<br>
<strong>9:</strong> Your server is now up and running the final thing you need to do is set up your source client.<br>
A few clients you can use are Nicecast(MAC), ices2, ices0.<br>
<br>
<strong>10:</strong> A final thing, make sure you set up your mount point in your source client! If you do not do this, no one will be able to listen to your stream!
<br>