<h1>SSH Tunnels Guide - The Basics</h1>

        
<h2>Information:</h2><br>
Unlike using OpenVPN that encrypts <em>all</em> network traffic at the driver level for that device, creating SSH tunnels enables you to route your for traffic&#x2F;applications selectively. <br>
<br>
For example: You could open a tunnel only for browsing or an application, letting the rest of your traffic go through your ISP directly, unencrypted. This can prevent a lot of problems for casual usage, such as using an imap application such as Thunderbird or using Personal websites like Paypal.<br>
<br>
You can create and have open as many tunnels as you need per device which is more suited to on demand usage, while offering pretty much the same level of privacy as OpenVPN.<br>
<br>
 <strong>Important note:</strong> You do not need OpenVPN installed for creating and using an SSH tunnel with your Feral slot. You can also create multiple SSH tunnels on different ports.<br>
<br>
You can also follow our tutorial on <a href="https://www.feralhosting.com/faq/view?question=13">Setting up Public Key Authentication on Windows</a>. This way you will not have to type in your password each time you initiate a session (unless a keyfile passphrase is used).<br>
<br>
 <strong>Important note:</strong> KiTTY cannot save pass phrases for protected keyfiles (you must use <a href="https://www.feralhosting.com/faq/view?question=241">PAGEANT</a> for this). For saving your pass phrases for a session use <a href="https://www.feralhosting.com/faq/view?question=238">XShell</a><br>
<br>
<h2>Creating an SSH Tunnel to use as a local SOCKS proxy with KiTTY.</h2><br>
<a href="https://www.feralhosting.com/faq/view?question=12">SSH Guide - The Basics</a> is a prerequisite of this guide. Please follow the steps there to SSH before using these next steps.<br>
<br>
 <strong>Important note:</strong> You can add and create more than one tunnel per session if needed.<br>
<br>
<strong>1:</strong> Navigate to the <code>Session</code> panel if not already there (this panel is the default when opening KiTTY)<br>
<br>
<strong>2:</strong> Select the session you want to load<br>
<br>
<strong>3:</strong> Click on <code>Load</code> to load this session and all configurations associated with it.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Kitty%20-%20SSH%20-%20Private%20Keys%20-%20SSH%20tunnels/10.png"><br>
<br>
<strong>1:</strong> Navigate to the <code>Connection</code> panel.<br>
<br>
<strong>2:</strong> Navigate down to the `SSH Panel.<br>
<br>
<strong>3:</strong> Select the <code>Tunnels</code> panel.<br>
<br>
<strong>4:</strong> Configure the new dynamic forwarded port that will act as a local SOCKS proxy (see next image for details)<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Kitty%20-%20SSH%20-%20Private%20Keys%20-%20SSH%20tunnels/11.png"><br>
<br>
<strong>1:</strong> Select the <code>Auto</code> radio (this should already be selected by default)<br>
<br>
<strong>2:</strong> Select the <code>Dynamic</code> radio<br>
<br>
<strong>3:</strong> Select and enter a port between the range of <code>10001</code> to <code>32001</code><br>
<br>
<strong>4:</strong> Click <code>Add</code> to add this SSH tunnel.<br>
<br>
<strong>5:</strong> Once added you will see the tunnel listed in the <code>Forwarded ports</code> window.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Kitty%20-%20SSH%20-%20Private%20Keys%20-%20SSH%20tunnels/12.png"><br>
<br>
 <strong>Important note:</strong> Don&#x27;t forget to save this session after making any new changes.<br>
<br>
<strong>1:</strong> Navigate back to the <code>Session</code> panel.<br>
<br>
<strong>2:</strong> Select the session you want to save and merge the new configuration settings with.<br>
<br>
<strong>3:</strong> Click on <code>Save</code> to have these new settings saved to the selected session.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Kitty%20-%20SSH%20-%20Private%20Keys%20-%20SSH%20tunnels/13.png"><br>
<br>
<h2>OS X Built-in SSH Client using private&#x2F;public key pair</h2><br>
SSH is the built-in OS X SSH client and is very powerful and simple to use if you follow the instructions in this guide.<br>
<br>
<h2>Connecting Via SSH using the default password and using private key files.</h2><br>
<strong>1:</strong> In terminal on mac run<br>
<br>
<pre><code>ssh-keygen -t rsa</code></pre><br>
Press enter for the default file save location<br>
<br>
Press enter when prompted for passphrase (no passphrase simplifies the process)<br>
&nbsp;  <br>
<strong>2:</strong> Then run:<br>
<br>
<pre><code>cat ~&#x2F;.ssh&#x2F;id_rsa.pub | pbcopy</code></pre><br>
to copy the key to your clipboard so we can save it to our slot.<br>
<br>
<strong>3:</strong> Then run this command (don&#x27;t copy it or you will lose the key info in the clipboard:<br>
<br>
 <strong>Important note:</strong>&nbsp; This is NOT a number 1. It is a non-capitalised letter <code>L</code><br>
<br>
<pre><code>ssh -l username server.feralhosting.com</code></pre><br>
Replace <code>username</code> and&nbsp; <code>server</code> with your own details provided to by Feral. Use the SSH password from your feral Manager Slot details page for the relevant slot.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/slot_detail_ssh.png"><br>
<br>
<strong>4:</strong> Once logged into your feral slot via SSH run:<br>
<br>
<pre><code>nano ~&#x2F;.ssh&#x2F;authorized_keys</code></pre><br>
<strong>5:</strong> Paste your clipboard contents into the file, ensuring that the contents are all on one line (remove line breaks)<br>
<br>
<strong>6:</strong> Then press and hold <code>CTRL</code> and then press <code>x</code> to save. Press <code>y</code> to confirm.<br>
<br>
<strong>7:</strong> Type <code>exit</code> to leave SSH session on feral slot<br>
<br>
<h2>Creating SSH tunnels:</h2><br>
<strong>1:</strong> In terminal, type <br>
<br>
<pre><code>ssh -D 12345 -l username server.feralhosting.com</code></pre><br>
Replace <code>username</code> and <code>server</code> with your own details.<br>
<br>
 <strong>Important note:</strong> You must change <code>12345</code> to another port number if you wish. Use a port between the range of <code>10001</code> to <code>32001</code>.<br>
<br>
<strong>2:</strong> You have now created an Socks proxy on port your selected port. See instructions later in this article for instructions on how to use this proxy.<br>
<br>
<h2>Creating SSH tunnels in background</h2><br>
You can semi-automate the above process by creating an alias for the tunnel command and setting it up to run in a screen session in the background<br>
<br>
<strong>1:</strong> in terminal type <br>
<br>
<pre><code>nano ~&#x2F;.bash_profile</code></pre><br>
<strong>2:</strong> In the resulting&nbsp; editor window type <br>
<br>
<pre><code>alias feraltun=&quot;screen ssh -D 12345 -l username server.feralhosting.com&quot;</code></pre><br>
Replace <code>username</code> and <code>server</code> with your own details.<br>
<br>
 <strong>Important note:</strong> You must change <code>12345</code> to another port number if you wish. Use a port between the range of <code>10001</code> to <code>32001</code>. If you&#x27;re using a tunnel to complete the Plex installation process do <strong>not</strong> use port 32400 here.<br>
<br>
<strong>3:</strong> Then press and hold <code>CTRL</code> and then press <code>x</code> to save. Press <code>y</code> to confirm.<br>
<br>
<strong>4:</strong> To enable the new alias in your current session type:<br>
<br>
<pre><code>source ~&#x2F;.bash_profile</code></pre><br>
<br>
<strong>To use your new alias:</strong><br>
<br>
<strong>1:</strong> Type:<br>
<br>
<pre><code>feraltun</code></pre><br>
Your SSH tunnel is now active.<br>
<br>
<strong>2:</strong> Then press and hold <code>CTRL</code> and <code>a</code> then press <code>d</code> to detach from the screen. This leaves it running in the background.<br>
<br>
<strong>3:</strong> You can now close terminal and use your tunnel<br>
<br>
 <strong>Important note:</strong>&nbsp; If you have any questions about this procedure for OS X or suggestions on improving the instructions, please contact liriel in IRC.<br>
<br>
<h2>Basic usage of tunnels in applications</h2><br>
See this FAQ for more info.<br>
<br>
<a href="https://www.feralhosting.com/faq/view?question=242">SSH Tunnels - How to use them with your applications</a><br>
<br>
