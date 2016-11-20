<h1>Plexpy installation</h1>
        
In SSH do the commands described in this FAQ. If you do not know how to SSH into your slot use this FAQ: <a href="https://www.feralhosting.com/faq/view?question=12">SSH Guide - The Basics</a><br>
<br>
Your FTP &#x2F; SFTP &#x2F; SSH login information can be found on the Slot Details page for the relevant slot. Use this link in your Account Manager to access the relevant slot:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/slot_detail_link.png"><br>
<br>
You login information for the relevant slot will be shown here:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/slot_detail_ssh.png"><br>
<br>
<h2>Installing PlexPy</h2><br>
Run these commands to install and launch PlexPy. The commands also put PlexPy into a screen.<br>
<br>
<pre><code>git clone <a href="https://github.com/drzoidberg33/plexpy.git">https:&#x2F;&#x2F;github.com&#x2F;drzoidberg33&#x2F;plexpy.git</a>
sed -i &#x27;s|http_port = 8181|http_port = &#x27;$(shuf -i 10001-32001 -n 1)&#x27;|g&#x27; ~&#x2F;plexpy&#x2F;config.ini
screen -dmS plexpy python ~&#x2F;plexpy&#x2F;PlexPy.py
</code></pre><br>
Then, do this command to complete the setup of PlexPy:<br>
<br>
<pre><code>screen -r plexpy</code></pre><br>
The reason for the screen is to keep it running when you close the SSH connection. Once you&#x27;re done in the screen you can get out of it by pressing <code>ctrl + a + d</code>. In other words, hold down <code>ctrl</code> and press <code>a</code> and with both those held down still, press <code>d</code>.
<br>  
