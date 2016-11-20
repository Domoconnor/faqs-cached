<h1>SSH tunnels - MyEnTunnel</h1>

        
<br>
<h2>What is an SSH Tunnel?</h2><br>
Unlike using OpenVPN that encrypts <strong>all</strong> network traffic at the driver level for that device, creating SSH tunnels enables you to route your for traffic&#x2F;applications selectively, providing they have a proxy option.<br>
<br>
For example: You could open a tunnel only for browsing or another just for an application, letting the rest of your traffic go through your ISP directly, unencrypted. This can prevent a lot of problems for casual usage, like using an imap application such as Thunderbird or using personal websites like Paypal where a VPN might trigger a security alert regarding your location.<br>
<br>
You can create and have open as many tunnels as you need per device which is more suited to on demand usage, while offering pretty much the same level of privacy as OpenVPN.<br>
<br>
<h3>Using MyEnTunnel</h3><br>
MyEnTunnel is a tiny, portable piece of software that will allow you to easily set up a secure, encrypted SSH tunnel to your Feral box and use it as a local SOCKS5 proxy.<br>
<br>
It&#x27;s easier to set up and configure than the <a href="https://www.feralhosting.com/faq/view?question=37">PuTTY method</a>. Another advantage of this set-up is that MyEnTunnel runs quietly in your system tray not clattering your desktop as PuTTY would. MyEnTunnel will also re-establish the tunnel automatically if connection to the server was dropped.<br>
<br>
<strong>Step 1 Downloads:</strong><br>
<br>
All downloads are from this site, go here if you want the installer.<br>
<br>
<a href="http://nemesis2.qx.net/pages/MyEnTunnel">http:&#x2F;&#x2F;nemesis2.qx.net&#x2F;pages&#x2F;MyEnTunnel</a><br>
<br>
<strong>Important note:</strong> MyEnTunnel Version <code>3.6.1</code> use plink <code>0.63</code><br>
<br>
A direct link to the installer <a href="https://github.com/feralhosting/feralfilehosting/raw/master/Feral%20Wiki/SSH/SSH%20tunnels%20-%20MyEnTunnel/myentunnel_setup-3.6.1.exe">3.6.1 installer Unicode x86 and x64</a><br>
<br>
Custom downloads:<br>
<br>
What are these? The installer contains both the x86 and x64 Unicode installers and will automatically detect and install the correct version for you. You can install it anywhere and use the files portably. This had been done for you and you have the extracted and portable files ready to use.<br>
<br>
<a href="https://github.com/feralhosting/feralfilehosting/raw/master/Feral%20Wiki/SSH/SSH%20tunnels%20-%20MyEnTunnel/MyEnTunnelx86.zip">MyEnTunnel x86 3.6.1 Unicode</a><br>
<br>
<a href="https://github.com/feralhosting/feralfilehosting/raw/master/Feral%20Wiki/SSH/SSH%20tunnels%20-%20MyEnTunnel/MyEnTunnelx64.zip">MyEnTunnel x64 3.6.1 Unicode</a><br>
<br>
Older version:<br>
<br>
 <a href="https://github.com/feralhosting/feralfilehosting/raw/master/Feral%20Wiki/SSH/SSH%20tunnels%20-%20MyEnTunnel/myentunnel-unicode.3.5.2.plink.0.62.zip">MyEnTunnel 3.5.2 and plink 0.62</a> This is a prezipped version that includes plink <code>0.62</code> for convenience.<br>
<br>
<strong>Important note:</strong> Myentunnel <code>3.5.2</code> only works with plink.exe <code>0.62</code> and not <code>0.63</code>. Use version <code>3.6.1</code> for plink <code>0.63</code><br>
<br>
<strong>Step 2 Optional:</strong><br>
<br>
Make a copy of your existing <a href="https://www.feralhosting.com/faq/view?question=13">private key</a>, rename it to <code>keyfile.ppk</code>, <strong>You must put this <code>.ppk</code> file in the same directory where your MyEnTunnel.exe was extracted to</strong><br>
<br>
Make sure your private key works before your proceed to the next step.<br>
<br>
<strong>Important note:</strong> If your keyfile requires a passphrase use <a href="https://www.feralhosting.com/faq/view?question=241">PAGEANT</a> to load the key into memory. This file comes as part of the PuTTy bundle or as a stand alone exe. MyEnTunnel does not support passing keyfile passphrases to the server. PAGEANT MUST BE USED or you will need to use a keyfile with no passphrase.<br>
<br>
If you installed putty using the putty installer then you can either double click on a keyfile to load it or find PAGEANT, located here <code>Program files (x86)&#x2F;PuTTy&#x2F;</code>, for creating a custom short cut as shown in the PAGEANT guide.<br>
<br>
<strong>Step 3</strong><br>
<br>
Launch <code>myentunnel.exe</code>, go to the <code>Settings</code> tab and fill out the fields according to the screen shot below:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/SSH%20tunnels%20-%20MyEnTunnel/1.png"><br>
<br>
Substitute <code>server</code> with your the name of the Feral server, and <code>username</code> with your actual Feral username. You can find this information on the <a href="https://www.feralhosting.com/manager/">Slot Details</a> page of your Account Manager.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/SSH%20tunnels%20-%20MyEnTunnel/2.png"><br>
<br>
<strong>If you using a private key file use these steps instead:</strong><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/SSH%20tunnels%20-%20MyEnTunnel/3.png"><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/SSH%20tunnels%20-%20MyEnTunnel/4.png"><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/SSH%20tunnels%20-%20MyEnTunnel/5.png"><br>
<br>
<strong>Step 4</strong><br>
<br>
Press <code>connect</code>.<br>
<br>
If your private key is function able and you filled out the connection details correctly, MyEnTunnel should establish a tunnel to your Feral box and listen for connections the local port you selected.<br>
<br>
<strong>Basic usage of tunnels in applications</strong><br>
<br>
See this FAQ for more info.<br>
<br>
<a href="https://www.feralhosting.com/faq/view?question=242">SSH Tunnels - How to use them with your applications</a><br>
<br>
