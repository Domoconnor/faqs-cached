<h1>Public Key Authentication for password-less login</h1>

        
There is a Mac version at the end of the guide.<br>
<br>
<strong>A little background first.</strong><br>
 <br>
Public key authentication is an alternative means of identifying yourself to a login server, instead of typing a password. It is more secure and more flexible, but more difficult to set up. You generate a key pair, consisting of a public key (which everybody is allowed to know), and a private key (which you keep secret and do not give to anybody). The private key is able to generate signatures. A signature created using your private key cannot be forged by anybody who does not have that key; but anybody who has your public key can verify that a particular signature is genuine. There is more than one public-key algorithm available. The one we will use is RSA.<br>
<br>
We will generate the public and private key on your home computer and then copy the public key to your feral server via FTP or client in command line using&nbsp; SSH.<br>
<br>
<strong>Step 1: Using PuTTYgen to Generate the Key Pair</strong><br>
<br>
You can generate the key pair using PuTTYgen which is maintained by the author of PuTTy. It generates pairs of public and private keys to be used with PuTTY, PSCP, and Plink, as well as the PuTTy authentication agent, Pageant. PuTTYgen generates RSA and DSA keys using the .ppk format. If you downloaded the Putty installer package, you already have PuTTYgen located in the place you installed PuTTy to, usually <strong>Program files&#x2F;PuTTy</strong>. If not, you can download it by itself from <a href="http://the.earth.li/&#x7E;sgtatham/putty/latest/x86/puttygen.exe">here</a> as a single executable file.<br>
<br>
<strong>After you locate it or download PuTTygen, it&#x27;s time to run it.</strong><br>
<br>
First, you need to select which type of key you want to generate, and also select the strength of the key. <strong>We will be using RSA and 2048</strong> as the strength. Click the radio button next to SSH-2 RSA at the bottom of the PuTTYgen window, and then type 2048 in the box below it ( if the value is different)<br>
&nbsp;  <br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Public%20Key%20Authentication%20for%20password-less%20login/1.png"><br>
<br>
<strong><a href="http://www.javamex.com/tutorials/cryptography/rsa_key_length.shtml">Click here for more Info for Understanding RSA Key lengths</a></strong><br>
 <br>
Then press the &quot;Generate&quot; button to actually generate the key. First, a progress bar will appear and PuTTYgen will ask you to move the mouse around to generate randomness. Wave the mouse in circles over the blank area in the PuTTYgen window, and the progress bar will gradually fill up as PuTTYgen collects enough randomness. You don&#x27;t need to wave the mouse in particularly imaginative patterns (although it can&#x27;t hurt); PuTTYgen will collect enough randomness just from the fine detail of exactly how far the mouse has moved each time Windows samples its position.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Public%20Key%20Authentication%20for%20password-less%20login/2.png"><br>
<br>
When the progress bar reaches the end, PuTTYgen will begin creating the key. The progress bar will reset to the start, and gradually move up again to track the progress of the key generation. It will not move evenly, and may occasionally slow down to a stop; this is unfortunately unavoidable, because key generation is a random process and it is impossible to reliably predict how long it will take. <br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Public%20Key%20Authentication%20for%20password-less%20login/3.png"><br>
	<br>
Once you have generated the key, select a comment field and (optionally) a pass-phrase. (You can read more about why you would want to set a pass-phrase <a href="http://the.earth.li/&#x7E;sgtatham/putty/0.58/htmldoc/Chapter8.html&#x23;puttygen-passphrase">here</a>.)<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Public%20Key%20Authentication%20for%20password-less%20login/4.png"><br>
<br>
<strong>IMPORTANT INFORMATION</strong><br>
<br>
The comment field is a good place to store info about which server you will be connecting to, especially if you have several other keys. To alter the key comment, just type your comment text into the &quot;Key comment&quot; box before saving the private key. If you want to change the comment later, you can load the private key back into PuTTYgen, change the comment, and save it again. <br>
<br>
For now, leave the pass-phrase field blank. If you want to use it, <strong>do not forget your pass-phrase. There is no way to recover it</strong>.<br>
<br>
What using a Pass-phrase means to you: ( For the guide, from the list below, 1 &amp; 2 are best, 3 is overkill and does not make things easier)<br>
<br>
<strong>1:</strong> NO pass-phrase = easy to use and safe for home usage: but anyone with access to your key file can use it until you revoke it.<br>
<br>
<strong>2:</strong> A Good but &quot;easily remembered&quot; and &quot;easy to type&quot; pass phrase&nbsp; = easy to use and prevents most unauthorized usage. reasonably safe if used portably.<br>
<br>
<strong>3:</strong> A super complicated generated pass phrase = very secure if lost i.e. portable but not very easy to use with out PAGEANT ( and there is no PAGEANT for OpenSSH keys). This is not the most convenient route. There is no PAGEANT equivalent for our exported OpenSHH .pub keyfiles. Some software can remember your pass phrase but most do not on purpose and require you to enter it on each use.<br>
<br>
Now you&#x27;re ready to save the private key to disk. Press the &quot;Save private key&quot; button. PuTTYgen will put up a dialogue box asking you where to save the file. Select a directory, type in a file name, and press &quot;Save&quot;. This file is in PuTTy&#x27;s native format (*.PPK); it is the one you will need to tell PuTTy to use for authentication.<br>
<br>
Also it will be a good idea to export the key to the OpenSSH format for use with other programs, since a lot of software works with public&#x2F;private keys but does not support the .ppk format, instead they support the OpenSSH .pub format instead. This will just make our key more compatible and make sure we can use it wherever we need to.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Public%20Key%20Authentication%20for%20password-less%20login/5.png"><br>
<br>
After you have saved both files your Super Secret Location should look like this:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Public%20Key%20Authentication%20for%20password-less%20login/6.png"><br>
	<br>
Saving the public key: not necessary for feral server.<br>
<br>
<strong>Step 2: Transferring the Public Key to the Server</strong><br>
<br>
You will now want to copy the public key file to your SSH server machine. The field labelled <strong>Public key for pasting into authorized_keys file</strong> gives the public key data in the correct one-line format for the SSH-2 protocol that feralhosting uses. You will want to select the entire contents of the box using the mouse, press <strong>ctrl + C</strong> to copy it to the clipboard, and then paste the data into a PuTTy session which is connected to the server. <br>
	<br>
Open PuTTy and connect to your slice. Log in with your username and password and we will use the below command to open the <strong>authorized_keys</strong> file to edit:<br>
<br>
We are going to use an editor (we&#x27;ll use Nano in this tutorial), and edit the authorized_keys file. If it does not already exists, we will create it by opening nano using the command below and saving the file. <br>
<br>
<pre><code>nano -w ~&#x2F;.ssh&#x2F;authorized_keys</code></pre><br>
So it will look like this:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Public%20Key%20Authentication%20for%20password-less%20login/7.png"><br>
<br>
Once Nano has opened the file you will see something like this:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Public%20Key%20Authentication%20for%20password-less%20login/8.png"><br>
<br>
The first thing we do is Immediately press the RETURN&#x2F;ENTER key then Press the UP arrow key. it will then look like this<br>
	<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Public%20Key%20Authentication%20for%20password-less%20login/9.png"><br>
<br>
Now paste the key using right-click into your PuTTy window.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Public%20Key%20Authentication%20for%20password-less%20login/10.png"><br>
<br>
It will then look something like this: Notice the <strong>== rsa-key</strong>&nbsp; near the end of the line.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Public%20Key%20Authentication%20for%20password-less%20login/11.png"><br>
&nbsp;  <br>
Press <strong>ctrl + x</strong> to exit Nano. It will ask if you want to save â€” press Y:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Public%20Key%20Authentication%20for%20password-less%20login/12.png"><br>
<br>
Then press Enter. Nano will close and you will have a key file saved:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Public%20Key%20Authentication%20for%20password-less%20login/13.png"><br>
	<br>
<strong>Step 4: Chmod&#x27;ing the .ssh Directory</strong><br>
<br>
You will need to ensure that your .ssh directory and the authorized_keys file are not group-writable or world-writable. You do this by using this command:<br>
<br>
<pre><code>chmod 700 ~&#x2F;.ssh</code></pre><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Public%20Key%20Authentication%20for%20password-less%20login/test.png"><br>
<br>
Your server should now be configured to accept authentication using your private key. Now you need to configure PuTTy to attempt authentication using your private key.<br>
<br>
<strong>Step 5: Configuring PuTTy to use Private Key for Authentication</strong><br>
<br>
Open another PuTTy window. Select your saved session and press LOAD.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Public%20Key%20Authentication%20for%20password-less%20login/kitty%20key%20file.png"><br>
<br>
On the left, double-click on the SSH section to expand it, then click on the Auth section. On the right side, click the Browse button to point PuTTy to your freshly-created private key that you saved in Step 1.<br>
 <br>
(Optional) To make logins even easier, click on the Data key on the left side, it&#x27;s just a little above the SSH section, right under Connection. Fill out the auto-login details with your username.<br>
<br>
Now we need to save the changes we just made. Click on the Session section on the left side of PuTTy, then press the SAVE button. This will save the private key setting you just made. <br>
&nbsp;  <br>
If now you click Open, Putty will connect to your server, give it your username and use the private key to authenticate. You should be logged in, without having to type anything!<br>
<br>
* More information for the interested can be found on the official PuTTy <a href="http://the.earth.li/&#x7E;sgtatham/putty/0.62/htmldoc/Chapter8.html&#x23;pubkey">manual page</a>.<br>
<br>
<strong>For Mac Users:</strong><br>
<br>
Open up terminal.<br>
<br>
Type this in and press Enter:<br>
 <br>
<pre><code>ssh-keygen -t rsa</code></pre><br>
It will ask you what directory to save it in, just leave that blank (default) the files we create will be located in <strong>&#x2F;Users&#x2F;Yourusername&#x2F;.ssh</strong> (In the finder task bar click on Go and go to folder since <strong>.ssh</strong> is hidden by default)<br>
<br>
Next it will ask you to enter a pass-phrase.&nbsp; Enter something easy to remember but not too easy to guess.&nbsp; You can later add this to your key-chain and never have to type it in again.<br>
<br>
Login to your Feral account with SSH as usual and type in:<br>
<br>
<pre><code>touch .ssh&#x2F;authorized_keys</code></pre><br>
This will create the file for you.<br>
<br>
Next open up the file <strong>id_rsa.pub</strong> on your Mac and copy the entire contents of it.<br>
<br>
Go back to your Feral terminal and type:<br>
<br>
<pre><code>cd ~&#x2F;.ssh</code></pre><br>
Then type: <br>
<br>
<pre><code>nano authorized_keys</code></pre><br>
This will open up a text editor.&nbsp; Paste your key into the very last line and make sure it looks similar to the others (it doesn&#x27;t have an extra space after the first few words)<br>
<br>
It should look like this:<br>
<br>
<img src="http://i49.tinypic.com/313rgio.png"><br>
<br>
Press Ctrl+X or Cmd+X (however you have your keyboard set up) type y to save the changes and press enter to save the changes to authorized_keys.<br>
<br>
Next you need to chmod it. To do this type:<br>
<br>
<pre><code>chmod 600 authorized_keys</code></pre><br>
Close the feral terminal and your other terminal.<br>
<br>
Open up a new terminal and start to login to feral. Type your username@color.feralhosting.com&nbsp; you will notice a box pops up put your pass-code that I told you to make earlier (the one I told you that you could remember easy but wasn&#x27;t to easy to guess) and tick the remember password box.&nbsp; Click okay.<br>
<br>
Next time you go to login all you will have to do is type:<br>
<br>
<pre><code>ssh username@color.feralhosting.com</code></pre><br>
and it will login without you needing to worry about a password.<br>
<br>
If you would like a video reference to all of this please go <a href="http://peter.upfold.org.uk/blog/2009/09/11/set-up-public-key-authentication-for-ssh-on-the-mac/">here</a>.<br>
<br>
