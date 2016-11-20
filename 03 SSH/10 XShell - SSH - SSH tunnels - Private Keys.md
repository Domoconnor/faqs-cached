<h1>XShell - SSH - SSH tunnels - Private Keys</h1>

        
<br>
The guide follows a specific format for each section.<br>
<br>
<strong>1:</strong> Basic hostname&#x2F;server configuration<br>
<br>
<strong>2:</strong> Force UTF-8<br>
<br>
<strong>3:</strong> Basic authentication using a username and password<br>
<br>
<strong>4:</strong> Using keyfiles to connect ( the guide assumes you have already created these as it does not explain how)<br>
<br>
<strong>5:</strong> Creating SSH Tunnels.<br>
<br>
<strong>Important note:</strong> You only need to use the stages that apply to what you want to do.&nbsp; Complete only the steps that you require.<br>
<br>
<h2>Xshell 4&nbsp; SSH Client</h2><br>
Xshell is a very good SSH client with many useful and advanced features such as tabbed sessions, saving passwords, themes and lots more all available for free for home&#x2F;personal use.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/XShell%20-%20SSH%20-%20Private%20Keys%20-%20SSH%20tunnels/logo.png"><br>
<br>
<h2>Download XShell</h2><br>
<a href="http://www.netsarang.com/download/down_xsh.html">Download XShell - email required</a><br>
<br>
<h2>Topics covered:</h2><br>
- Connecting Via SSH using the default password<br>
- Importing and using private key files for authorisation.<br>
- Creating SSH tunnels.<br>
- Creating and managing keyfiles with xshell<br>
<br>
<h2>Key Features :</h2><br>
- Saves Passwords and Key file Pass phrases<br>
- Tabbed sessions<br>
- Easily configure multiple SSH tunnels from a single GUI.<br>
- Gui is feature rich with right click context options, theme changing and more<br>
- Can be be used with <a href="http://www.netsarang.com/products/xfp_overview.html">Xftp</a>, an FTP&#x2F;SFTP app by the same company, also free for home use.<br>
<br>
<h2>Installing XShell</h2><br>
After you have Downloaded XShell 4, run the installer and make sure to select the correct license when installing:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/XShell%20-%20SSH%20-%20Private%20Keys%20-%20SSH%20tunnels/1.png"><br>
<br>
The rest of the installer is very basic and you can safely use the default settings.<br>
<br>
Once XShell is installed, run the application using the Desktop short cut created and you will see a window similar to this. Follow the instructions in the images:<br>
<br>
Click on the <code>New</code> and then <code>Session</code> to open the Session Properties for our new session.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/XShell%20-%20SSH%20-%20Private%20Keys%20-%20SSH%20tunnels/2.png"><br>
<br>
<h2>Server&#x2F;Hostname configuration</h2><br>
Here we will configure the basic detail for connecting to our Feral server:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/XShell%20-%20SSH%20-%20Private%20Keys%20-%20SSH%20tunnels/3.png"><br>
<br>
The very next thing we will do is force Unicode&#x2F;UTF-8 for this session. Click on the <code>Terminal</code> Section and select <code>Unicode (UTF-8)</code> from the drop down menu.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/XShell%20-%20SSH%20-%20Private%20Keys%20-%20SSH%20tunnels/unicode.png"><br>
<br>
<strong>Important note:</strong> If you click OK now and then connect using the session, you can use XShell in the conventional (putty) way with your default password found in your Manager&#x2F;Slot&#x2F;Server page. You will be prompted for your username and password.<br>
<br>
Continue with the FAQ if you want XShell to store your username and password, to use Private Keys and SSH tunnels.<br>
<br>
<h2>Authentication using a Username and Password</h2><br>
XShell can store and save our username and password for the connection. This will mean it won&#x27;t prompt your for your username or password when connecting.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/XShell%20-%20SSH%20-%20Private%20Keys%20-%20SSH%20tunnels/4.png"><br>
<br>
Continue with the FAQ if you want to use Private Keys and SSH tunnels.<br>
<br>
<h2>Authentication using a public&#x2F;private key and Username</h2><br>
<strong>Important note:</strong> Please see last two sections of this FAQ for creating and managing keyfiles with XShell.<br>
<br>
XShell can also manage your private keys for your sessions with a built in SSH key manager.<br>
<br>
<strong>Important note:</strong> XShell uses the OpenSSH keyfile format. You will have to export your Putty PPK format keys using Puttygen to the OpenSSH format to use with XShell. please see the <a href="https://www.feralhosting.com/faq/view?question=13">Public Key Authentication for password-less login</a> FAQ for how to do this. It is quite easy to do.<br>
<br>
Select the Public Key option from the drop down menu, enter your username and then browse for a keyfile to use.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/XShell%20-%20SSH%20-%20Private%20Keys%20-%20SSH%20tunnels/privatekey.1.png"><br>
<br>
If you do not have any keyfiles imported you will need to import your OpenSSH format keyfile into XShell.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/XShell%20-%20SSH%20-%20Private%20Keys%20-%20SSH%20tunnels/privatekey.2.png"><br>
<br>
Browse to the location of you keyfile and then select it and click Open to import it.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/XShell%20-%20SSH%20-%20Private%20Keys%20-%20SSH%20tunnels/privatekey.3.png"><br>
<br>
If your keyfile is passphrase protected you will need to enter this passphrase to import it.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/XShell%20-%20SSH%20-%20Private%20Keys%20-%20SSH%20tunnels/privatekey.4.png"><br>
<br>
Once it is imported, select the keyfile and then click OK to use this keyfile.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/XShell%20-%20SSH%20-%20Private%20Keys%20-%20SSH%20tunnels/privatekey.5.png"><br>
<br>
Now briefly look over the settings to make sure things they are correct. <br>
<br>
<strong>Important note:</strong> XShell can save and store your keyfiles passphrase at this stage.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/XShell%20-%20SSH%20-%20Private%20Keys%20-%20SSH%20tunnels/privatekey.6.png"><br>
<br>
Continue with the FAQ if you to create and use SSH tunnels.<br>
<br>
<h2>Creating our SSH tunnel</h2><br>
Select the SSH&#x2F;Tunneling section. Then click on Add to begin creating a new tunnel<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/XShell%20-%20SSH%20-%20Private%20Keys%20-%20SSH%20tunnels/tunnel.1.png"><br>
<br>
Select Dynamic (SOCKS4&#x2F;5) from the drop down menu. Enter a port between 6000 and 60000. Give the tunnel and easy to remember name and then click OK to create it.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/XShell%20-%20SSH%20-%20Private%20Keys%20-%20SSH%20tunnels/tunnel.2.png"><br>
<br>
You will now see that our tunnel has been created and is listed in the list. Optionally you can add more tunnels or click OK to save and start using the Session.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/XShell%20-%20SSH%20-%20Private%20Keys%20-%20SSH%20tunnels/tunnel.3.png"><br>
<br>
<h2>Finalizing the set-up and connecting</h2><br>
This is the Session manager again. Here you can create, connect to or edits sessions. Make sure the box is ticked to &quot;Show this dialog box at startup&quot;<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/XShell%20-%20SSH%20-%20Private%20Keys%20-%20SSH%20tunnels/final.1.png"><br>
<br>
When you connect to a host for the first time you will get this warning box. Accept and Save the host key for your slot&#x27;s server.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/XShell%20-%20SSH%20-%20Private%20Keys%20-%20SSH%20tunnels/hostkey.png"><br>
<br>
Change the view options so that we can see the Tunnelling pane. This will let us easily manage out SSH tunnels.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/XShell%20-%20SSH%20-%20Private%20Keys%20-%20SSH%20tunnels/final.2.png"><br>
<br>
Click on the Forwarding Rules tab to see, edit, create and remove SSH tunnels for the current tabbed session.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/XShell%20-%20SSH%20-%20Private%20Keys%20-%20SSH%20tunnels/final.3.png"><br>
<br>
<h2>Creating Keyfiles.</h2><br>
You can use XShell you create and manager your public and private key pairs. Click on Tools in the menu and then select &quot;User Key Manager...&quot;<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/XShell%20-%20SSH%20-%20Private%20Keys%20-%20SSH%20tunnels/generate.0.png"><br>
<br>
Change the Key type to RSA and the Key length to 2048 then click Next.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/XShell%20-%20SSH%20-%20Private%20Keys%20-%20SSH%20tunnels/generate.1.png"><br>
<br>
Wait for the key to be generated. Don&#x27;t click Finish just yet, when the key is generated click Next.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/XShell%20-%20SSH%20-%20Private%20Keys%20-%20SSH%20tunnels/generate.2.png"><br>
<br>
Here you can name your keyfile. The default name is usually descriptive of the properties of the keyfile itself. You can also passphrase protect your keyfile here. Click Next when done<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/XShell%20-%20SSH%20-%20Private%20Keys%20-%20SSH%20tunnels/generate.3.png"><br>
<br>
Now it is recommended you &quot;Save as a file...&quot; to somewhere on your PC. You can also right click on the Public Key and &quot;Select all&quot; to paste it into your <code>~&#x2F;.ssh&#x2F;authorized_keys</code> files<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/XShell%20-%20SSH%20-%20Private%20Keys%20-%20SSH%20tunnels/generate.4.png"><br>
<br>
Save it somewhere. You can give it any name you want. The private key does not require a file extension. Once you have saved the keyfile click Finish.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/XShell%20-%20SSH%20-%20Private%20Keys%20-%20SSH%20tunnels/generate.5.png"><br>
<br>
Please see this the <a href="https://www.feralhosting.com/faq/view?question=13">Public Key Authentication for password-less login</a> for information on how to add the public key to your slot so you can connect with this keyfile.<br>
<br>
<h2>Managing Keyfiles</h2><br>
Now back in the Key Manager you will see your newly created keyfile. We will quickly cover some ways to manage it. Select your keyfile and then click on Properties.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/XShell%20-%20SSH%20-%20Private%20Keys%20-%20SSH%20tunnels/generate.6.png"><br>
<br>
In this windows you will have two tabs to use. The first is the General tab where you can 1: Change the key name 2: Change the passphrase for the keyfile.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/XShell%20-%20SSH%20-%20Private%20Keys%20-%20SSH%20tunnels/generate.7.png"><br>
<br>
In the Public Key tab you can get your public key as well as save the file.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/XShell%20-%20SSH%20-%20Private%20Keys%20-%20SSH%20tunnels/generate.8.png"><br>
<br>
