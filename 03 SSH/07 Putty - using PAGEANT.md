<h1>Putty - using PAGEANT</h1>

        
<br>
<h3>PAGEANT = For use with .ppk</h3><br>
This will cover the use of PAGEANT for loading private <code>.PPK</code> keyfiles generated with puttygen with pass phrases for easy use with other programs that do not directly support private key files with pass phrases. As mentioned in the guide for setting up public&#x2F;private key files, if you use a very complicated password for your keyfile (maybe a password generator) then things can be complicated to set up.<br>
<br>
So instead of entering our complicated (or simple) password every time we SSH to our server we can enter it one time and PAGEANT will forward it for us.<br>
<br>
<h4>How to get PAGEANT?</h4><br>
If you have already installed the <a href="https://www.feralhosting.com/faq/view?question=12">puTTy installer</a> or downloaded the <a href="https://www.feralhosting.com/faq/view?question=12">Putty zip</a> file you have PAGEANT already. For the installer look under the installation directory (Program files (x86)&#x2F;PuTTy&#x2F;) or where you extracted the zip file to.<br>
<br>
<h4>How to use PAGEANT?</h4><br>
Now using PAGEANT is a very simple process. You double click on the exe and the programs icons will appear in the task bar. You can right or double click on this icon to &quot;Add Key&quot;. Point the program to where you keyfile is located and it will ask for a pass phrase and then load your key into memory.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Putty%20-%20using%20PAGEANT/1.png"><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Putty%20-%20using%20PAGEANT/2.png"><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Putty%20-%20using%20PAGEANT/3.png"><br>
<br>
<h4>Create a Unique shortcut for you keyfile</h4><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Putty%20-%20using%20PAGEANT/4.png"><br>
<br>
<strong>Target:</strong> &quot;C:\Program Files\PuTTY\pageant.exe&quot; C:\Path\to\myKeys\MyKey.ppk<br>
<br>
For multiple keys this is where the field &quot;Start in&quot; can help. By changing it we can tell Pageant to start in the folder containing our keys and load them by file name:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Putty%20-%20using%20PAGEANT/4.5.png"><br>
<br>
<strong>Target:</strong> &quot;C:\Program Files\PuTTY\Pageant.exe&quot; key1.ppk key2.ppk key3.ppk<br>
<br>
<strong>Start in:</strong> &quot;C:\Documents and Settings\myaccount\My Documents\myKeys&quot;<br>
<br>
<strong>Have it start with Windows</strong><br>
<br>
You will need to add this new short cut you you start-up folder. Which is located here ( replace USERNAME with your own)<br>
<br>
press the <code>Windows</code> + <code>R</code> and enter this in the run box.( you need to have Replaced USERNAME with your own.)<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/Putty%20-%20using%20PAGEANT/5.png"><br>
<br>
<code>C:\Users\USERNAME\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Startup\</code><br>
<br>
Copy and paste your short cut here<br>
<br>

