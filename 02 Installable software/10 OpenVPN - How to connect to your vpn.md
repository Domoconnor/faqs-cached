<h1>OpenVPN - How to connect to your vpn</h1>

        
This software can be installed from the manager <a href="https://www.feralhosting.com/manager/">Install Software</a>.<br>
<br>
After OpenVPN has been set up on your server you will need to install an OpenVPN client on your own computer to use it. <br>
<br>
<h2>Windows</h2><br>
Using the <a href="http://openvpn.net/index.php/open-source/downloads.html">OpenVPN Stable&#x2F;Current</a> is relatively easy on a Windows machine.<br>
 <br>
After installing, you should connect to your server via SFTP (use an FTP&#x2F;SFTP client such as Filezilla) and download the contents of <br>
<br>
<pre><code>~&#x2F;private&#x2F;vpn&#x2F;</code></pre><br>
Full path will look something like: <br>
<br>
<pre><code>&#x2F;media&#x2F;DiskID&#x2F;home&#x2F;username&#x2F;private&#x2F;vpn&#x2F;</code></pre><br>
Copy the contents of this folder into:<br>
<br>
<pre><code>C:&#x2F;Program Files&#x2F;OpenVPN&#x2F;config&#x2F;</code></pre><br>
(or the location where OpenVPN was installed, maybe <code>Program Files (x86)</code>).<br>
<br>
So after you have downloaded the files to your:<br>
<br>
<pre><code>&#x2F;config folder</code></pre><br>
You will see inside it:<br>
<br>
<strong>1:</strong> client.ovpn<br>
<br>
<strong>2:</strong> keys directory<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Installable%20software/OpenVPN%20-%20How%20to%20connect%20to%20your%20vpn/keysdirectory.png"><br>
<br>
Now start the opengui as admin, once it has loaded you should be able to right click on the icon and Connect.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Installable%20software/OpenVPN%20-%20How%20to%20connect%20to%20your%20vpn/connect.png"><br>
<br>
<strong>NOTE:</strong> After some recent windows updates it seem you must run openvpn GUI as Admin. To check it is working after openvpn has connected and the icon is green check your IP in your default browser<br>
<br>
<strong>NOTE:</strong> <br>
<br>
On <code>some</code> Windows 7&#x2F;8 systems, internet traffic is not properly routed through the VPN. In such a case the client.ovpn file must be edited, adding these lines at the end:<br>
<br>
<pre><code>route-method exe
route-delay
route-metric 512
route 0.0.0.0 0.0.0.0</code></pre><br>
<strong>OS X &amp; Snow Leopard</strong><br>
<br>
The networking stack of OS X has VPN support built-in, however a dedicated client offers better configuration and is easier. <a href="http://www.tunnelblick.net/">Tunnelblick</a> is the best free client, however this is currently not working well in Snow Leopard. <a href="http://www.viscosityvpn.com/index.html">Viscosity</a>, which costs $9, has a much nicer GUI, better configuration, and fully supports both Leopard and Snow Leopard. <br>
<br>
You need to download the contents of <code>~&#x2F;private&#x2F;vpn&#x2F;</code> to a secure location in your home directory. Then in Viscosity Preferences, simply &quot;Import Connection&quot; and use the client.ovpn file; Viscosity will import all the needed data. You can then delete the vpn directory you downloaded as Viscosity stores the data in its own Library location.<br>
<br>
Update 2015-04-11 - The ovpn file doesn&#x27;t setup the TLS-Auth shared key properly. In Viscosity&#x27;s Authentication settings, under Extra &gt; Tls-Auth set the key to tls-auth.key and the direction to 1.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Installable%20software/OpenVPN%20-%20How%20to%20connect%20to%20your%20vpn/osx1.png"><br>
<br>
<h2>iOS</h2><br>
<strong>1:</strong> Download <a href="https://itunes.apple.com/us/app/openvpn-connect/id590379981?mt=8">OpenVPN Connect</a> from the app store.&nbsp; It&#x27;s a free download.<br>
<br>
<strong>2:</strong> Download the contents of ~&#x2F;private&#x2F;vpn to the machine you sync your device with.<br>
<br>
<strong>3:</strong> Open iTunes on your PC.&nbsp; Go to your device&#x27;s &#x27;apps&#x27; tab.&nbsp; Scroll down until you see file sharing and then select OpenVPN Connect in the list of apps.<br>
<br>
<strong>4:</strong> Add client.ovpn AND the files inside the &#x27;keys&#x27; folder (rather than the folder itself) to OpenVPN Connect&#x27;s folder.<br>
<br>
<strong>5:</strong> Launch OpenVPN Connect on your iOS device.&nbsp; It will prompt you to add a new connection; press the plus sign.<br>
<br>
<strong>6:</strong> Enjoy your new VPN.<br>
<br>
<h2>Android 4.0 +</h2><br>
Use this FAQ:<br>
<br>
<a href="https://www.feralhosting.com/faq/view?question=220">OpenVPN - Connect on Android 4.0 and up - using OpenVPN Connect</a><br>
<br>
<h2>Linux</h2><br>
Linux generally comes with clients built-in to their network managers.<br>
<br>
<code>Note: the file keys&#x2F;&lt;username&gt;.key should be secret at all times.</code> This includes never transferring it over an insecure connection or moving it to a place where you do not have complete control over. For this reason you should always use SFTP to transfer the file and not FTP. If there was a mistake made during this process a new key can be generated by <a href="https://www.feralhosting.com/manager/software-install">installing through the account manager</a> again.<br>
<br>
<h2>Ubuntu 10.04</h2><br>
First, make sure you have the keys folder and the client.ovpn file somewhere on your hard drive. They should have been downloaded from the &#x2F;private&#x2F;vpn&#x2F; folder of your server via SFTP (winscp works fine in wine).<br>
<br>
Open up the Ubuntu Software centre from the applications menu. Search for &quot;network-manager-openvpn&quot;.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Installable%20software/OpenVPN%20-%20How%20to%20connect%20to%20your%20vpn/ubuntu1.png"><br>
<br>
Choose the &quot;Gnome&quot; version which is highlighted above. You should see an install button where the remove button is. Click it. Openvpn will now be installed.<br>
<br>
Next, right-click on the network icon in the upper-right of the screen, and select &quot;Edit Connections&quot;.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Installable%20software/OpenVPN%20-%20How%20to%20connect%20to%20your%20vpn/ubuntu2.png"><br>
<br>
Navigate to the VPN tab and click &quot;import&quot;.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Installable%20software/OpenVPN%20-%20How%20to%20connect%20to%20your%20vpn/ubuntu3.png"><br>
<br>
Select your client.ovpn file that you downloaded earlier using SFTP. Make sure the keys folder and the client.ovpn file are in the same directory to make this a little easier.<br>
<br>
On this screen, everything should be filled in already. At the top you can change the name of the VPN connection and choose whether you want to connect to it automatically. Click apply, and close the &quot;network connections&quot; window.<br>
<br>
Now, your OpenVPN connection should be ready to go. Left-click on the network icon, select VPN connections, and then click the name of the one you just created. Within a few seconds you will notice a lock on your connection icon, signalling you are connected.<br>
<br>
Note: Rebooting your PC may also be necessary, so if OpenVPN fails to connect try a reboot.<br>
<br>
<h2>Confirmation of an Active VPN Connection</h2><br>
After this is set up and the OpenVPN GUI is running, you should check that your IP address appears the same as the server to websites you visit: go to <a href="http://whatismyipaddress.com/">http:&#x2F;&#x2F;whatismyipaddress.com&#x2F;</a> and make sure the server IP provided is reported back to you. If it isn&#x27;t and you appear to be connected, something has gone wrong and your communications are not being encrypted.<br>
<br>
<h2>ubuntu 11.10 OpenVPN connection instruction (likely to work on 10.04, 10.10, 11.04</h2><br>
<strong>1:</strong> Install openvpn software at <a href="https://www.feralhosting.com/manager/slot/install?service=20036">OpenVPN</a><br>
and wait a few minutes<br>
<br>
<strong>2:</strong> connect to account via scp or sftp and navigate to the private directory. Look for the file called client.ovpn and download it.<br>
Also in the vpn directory, there is another directory called keys that needs te be downloaded. Upon downloading locally, be certain all 6 files are in the same directory on your computer.&nbsp; <br>
Example path to files on feralhosting: &#x2F;media&#x2F;sdb1&#x2F;home&#x2F;YOURUSERNAME&#x2F;private&#x2F;vpn<br>
<br>
<strong>3:</strong> From here you will configure the vpn connection using the network manager in ubuntu. Click on configure VPN followed by import.<br>
<br>
<strong>4:</strong> Choose the client.ovpn to import which will select in the type (certificate).<br>
<br>
<strong>5:</strong> Name the connection and ensure the gateway is your feralhosting server. ex server.feralhosting.com<br>
<br>
<strong>6:</strong> Click on the file icon to choose you user certificate (ends in .crt) Moving on, choose the CA certificate called ca.crt and ending with the private key such as username.key.<br>
<br>
<strong>7:</strong> Locate the advanced icon in the lower right corner and click it. <br>
<br>
<strong>8:</strong> Select the tab &quot;TLS Authentication&quot;.<br>
<br>
<strong>9:</strong> Check the box &quot;Use additional TLS authentication&quot;.<br>
<br>
<strong>10:</strong> Choose the key file from the same directory as all the other files you have used, it will be called tls-auth.key.<br>
<br>
<strong>11:</strong> Save &amp; connect.<br>
<br>
<strong>12:</strong> open a terminal and type curl ifconfig.me to see what your IP address is.<br>
<br>
If you cannot connect, open a terminal up and type:<br>
<br>
<pre><code>tail -f &#x2F;var&#x2F;log&#x2F;syslog</code></pre><br>
This will monitor the NetworkManager as you try and connect to the VPN. Review and google the answers to best determine what is preventing the connection.<br>
<br>
<h2>Selective VPN routing</h2><br>
By default, the OpenVPN server will advertise itself as the default gateway for your client. If you don&#x27;t want this to happen, add the following to the end of your OpenVPN client configuration file (client.ovpn):<br>
<pre><code>
route-noexec
</code></pre><br>
<br>
After this, you can use routing commands to configure the desired routes. The method of doing this will vary based on your operating system, but here are some examples for a Linux based system. In each of these examples, it is assumed that your VPN network interface is named tun0:<br>
<pre><code>
# Add a route for all hosts on the network 123.45.67.0&#x2F;24 via the VPN:
route add -net 123.45.67.0&#x2F;24 dev tun0
# Add a route to 123.45.67.89 via the VPN:
route add -host 123.45.67.89 dev tun0
</code></pre>
<br>
