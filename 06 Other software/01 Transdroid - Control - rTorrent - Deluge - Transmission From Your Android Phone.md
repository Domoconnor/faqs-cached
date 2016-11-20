<h1>Transdroid - Control - rTorrent - Deluge - Transmission From Your Android Phone</h1>

        
<br>
<a href="http://transdroid.org">Transdroid</a> can be used to control rTorrent from your Android phone.<br>
<br>
<h2>Required prerequisites</h2><br>
 <strong>Important note:</strong> To use transdroid with rutorrent&#x2F;rtorrent you are required to:<br>
<br>
<strong>1:</strong> Have rutorrent&#x2F;rtorrent installed already via the Software Install page for the relevant slot.<br>
<br>
<strong>2:</strong> You must then <a href="https://www.feralhosting.com/faq/view?question=231">update to nginx using this FAQ</a>. Once you have done that, use this information below to use transdroid to connect to rutorrent.<br>
<br>
<h2>Automated Setup</h2><br>
 <strong>Important note:</strong> Requires Transdrone&#x2F;Transdroid 2.3.0 or newer.<br>
<br>
Use this script to generate a qrcode of a fully configured server that you can import directly into Transdrone&#x2F;Transdroid.<br>
<br>
<strong>1:</strong> Rutorrent<br>
<strong>2:</strong> Deluge<br>
<strong>3:</strong> Transmission<br>
<br>
 <strong>Important note:</strong> If you get an error and the program crashes when trying to scan a qrcode make sure you have installed the qrcode scanner: <a href="https://play.google.com/store/apps/details?id=com.google.zxing.client.android&#x26;hl=en_GB">Barcode Scanner</a><br>
<br>
<pre><code>wget -qO ~&#x2F;transdroid.setup <a href="http://git.io/lU_B9w">http:&#x2F;&#x2F;git.io&#x2F;lU_B9w</a> &amp;&amp; bash ~&#x2F;transdroid.setup</code></pre><br>
<h2>Manual Setup</h2><br>
Open Transdroid 2 on your device. Click on the menu button and then click on <code>settings</code>.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Transdroid%20-%20Control%20rTorrent%20-%20Deluge%20-%20Transmission%20From%20Your%20Android%20Phone/main/settings.png"><br>
<br>
Then click on <code>Add new server</code>.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Transdroid%20-%20Control%20rTorrent%20-%20Deluge%20-%20Transmission%20From%20Your%20Android%20Phone/main/addserver.png"><br>
<br>
You will now see this list of main options:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Transdroid%20-%20Control%20rTorrent%20-%20Deluge%20-%20Transmission%20From%20Your%20Android%20Phone/main/mainoptions.png"><br>
<br>
<h2>rutorrent</h2><br>
<strong>Name:</strong> Can be anything you want, such as <code>rutorrent</code><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Transdroid%20-%20Control%20rTorrent%20-%20Deluge%20-%20Transmission%20From%20Your%20Android%20Phone/rutorrent/name.png"><br>
<br>
<strong>Server type:</strong> <code>rTorrent</code><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Transdroid%20-%20Control%20rTorrent%20-%20Deluge%20-%20Transmission%20From%20Your%20Android%20Phone/rutorrent/servertype.png"><br>
<br>
<strong>IP or host name:</strong> <code>server.feralhosting.com</code> (where <code>server</code> is the name of the actual server that hosts the relevant slot)<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Transdroid%20-%20Control%20rTorrent%20-%20Deluge%20-%20Transmission%20From%20Your%20Android%20Phone/main/hostname.png"><br>
<br>
<strong>User Name:</strong> <code>rutorrent</code><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Transdroid%20-%20Control%20rTorrent%20-%20Deluge%20-%20Transmission%20From%20Your%20Android%20Phone/rutorrent/username.png"><br>
<br>
<strong>Password:</strong> <code>*********</code>&nbsp; This password will be the password shown in your Slot Details page for the relevant slot.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/rutorrent.slotdetails.png"><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Transdroid%20-%20Control%20rTorrent%20-%20Deluge%20-%20Transmission%20From%20Your%20Android%20Phone/main/password.png"><br>
<br>
<h3>Advanced Options</h3><br>
Click on <code>Advanced Options</code> now. You will see this list of options.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Transdroid%20-%20Control%20rTorrent%20-%20Deluge%20-%20Transmission%20From%20Your%20Android%20Phone/main/advancedoptions.png"><br>
<br>
*<strong>Port number</strong> <code>443</code><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Transdroid%20-%20Control%20rTorrent%20-%20Deluge%20-%20Transmission%20From%20Your%20Android%20Phone/main/port.png"><br>
<br>
<strong>SCGI&#x2F;Folder:</strong> <code>&#x2F;username&#x2F;rtorrent&#x2F;rpc</code> (case sensitive and where username is your Feral username)<br>
<br>
 <strong>Important note:</strong> You need the <code>&#x2F;</code> at the beginning and no trailing slash.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Transdroid%20-%20Control%20rTorrent%20-%20Deluge%20-%20Transmission%20From%20Your%20Android%20Phone/rutorrent/scgipath.png"><br>
<br>
<strong>Use SSL</strong> Make sure to tick this box<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Transdroid%20-%20Control%20rTorrent%20-%20Deluge%20-%20Transmission%20From%20Your%20Android%20Phone/main/ssl.png"><br>
<br>
<h3>Optional Settings</h3><br>
Click on <code>Optional Settings</code> now.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Transdroid%20-%20Control%20rTorrent%20-%20Deluge%20-%20Transmission%20From%20Your%20Android%20Phone/main/optionalsettings.png"><br>
<br>
<strong>Server OS:</strong> <code>Linux</code><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Transdroid%20-%20Control%20rTorrent%20-%20Deluge%20-%20Transmission%20From%20Your%20Android%20Phone/main/serveros.png"><br>
<br>
 <strong>Important note:</strong><br>
<br>
You may need to close and restart Transdroid for it to actually connect. It can fail with an error until you force a restart.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Transdroid%20-%20Control%20rTorrent%20-%20Deluge%20-%20Transmission%20From%20Your%20Android%20Phone/main/forceend.png"><br>
<br>
If all settings were correctly entered you should now be able to connect:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Transdroid%20-%20Control%20rTorrent%20-%20Deluge%20-%20Transmission%20From%20Your%20Android%20Phone/rutorrent/rutorrentfinal.png"><br>
<br>
<h2>Deluge</h2><br>
<strong>Name:</strong> Can be anything you want, such as <code>deluge</code><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Transdroid%20-%20Control%20rTorrent%20-%20Deluge%20-%20Transmission%20From%20Your%20Android%20Phone/deluge/name.png"><br>
<br>
<strong>Server type:</strong> <code>deluge</code><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Transdroid%20-%20Control%20rTorrent%20-%20Deluge%20-%20Transmission%20From%20Your%20Android%20Phone/deluge/servertype.png"><br>
<br>
<strong>Set IP&#x2F;domain:</strong> <code>server.feralhosting.com</code> (where <code>server</code> is the name of the actual server that hosts the relevant slot)<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Transdroid%20-%20Control%20rTorrent%20-%20Deluge%20-%20Transmission%20From%20Your%20Android%20Phone/main/hostname.png"><br>
<br>
<strong>Deluge web password:</strong> <code>*********</code>&nbsp; This password will be the password shown in your Slot Details page for the relevant slot.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/deluge.slotdetails.png"><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Transdroid%20-%20Control%20rTorrent%20-%20Deluge%20-%20Transmission%20From%20Your%20Android%20Phone/deluge/webpassword.png"><br>
<br>
<h3>Advanced Options</h3><br>
Click on <code>Advanced Options</code> now. You will see this list of options.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Transdroid%20-%20Control%20rTorrent%20-%20Deluge%20-%20Transmission%20From%20Your%20Android%20Phone/main/advancedoptions.png"><br>
<br>
<strong>Port number</strong> <code>443</code><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Transdroid%20-%20Control%20rTorrent%20-%20Deluge%20-%20Transmission%20From%20Your%20Android%20Phone/main/port.png"><br>
<br>
<strong>SCGI&#x2F;Folder:</strong> <code>&#x2F;username&#x2F;deluge</code> (case sensitive and where username is your Feral username)<br>
<br>
 <strong>Important note:</strong> You need the <code>&#x2F;</code> at the beginning and no trailing slash.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Transdroid%20-%20Control%20rTorrent%20-%20Deluge%20-%20Transmission%20From%20Your%20Android%20Phone/deluge/folderpath.png"><br>
<br>
<strong>Use SSL</strong> Make sure to tick this box<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Transdroid%20-%20Control%20rTorrent%20-%20Deluge%20-%20Transmission%20From%20Your%20Android%20Phone/main/ssl.png"><br>
<br>
<h3>Optional Settings</h3><br>
Click on <code>Optional Settings</code> now.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Transdroid%20-%20Control%20rTorrent%20-%20Deluge%20-%20Transmission%20From%20Your%20Android%20Phone/main/optionalsettings.png"><br>
<br>
<strong>Server OS:</strong> <code>Linux</code><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Transdroid%20-%20Control%20rTorrent%20-%20Deluge%20-%20Transmission%20From%20Your%20Android%20Phone/main/serveros.png"><br>
<br>
 <strong>Important note:</strong><br>
<br>
You may need to close and restart Transdroid for it to actually connect. It can fail with an error until you force a restart.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Transdroid%20-%20Control%20rTorrent%20-%20Deluge%20-%20Transmission%20From%20Your%20Android%20Phone/main/forceend.png"><br>
<br>
If all settings were correctly entered you should now be able to connect:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Transdroid%20-%20Control%20rTorrent%20-%20Deluge%20-%20Transmission%20From%20Your%20Android%20Phone/deluge/delugefinal.png"><br>
<br>
<h2>transmission</h2><br>
<strong>Name:</strong> Can be anything you want, such as <code>transmission</code><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Transdroid%20-%20Control%20rTorrent%20-%20Deluge%20-%20Transmission%20From%20Your%20Android%20Phone/transmission/name.png"><br>
<br>
<strong>Server type:</strong> <code>tranmission</code><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Transdroid%20-%20Control%20rTorrent%20-%20Deluge%20-%20Transmission%20From%20Your%20Android%20Phone/transmission/servertype.png"><br>
<br>
<strong>Set IP&#x2F;domain:</strong> <code>server.feralhosting.com</code> (where <code>server</code> is the name of the actual server that hosts the relevant slot)<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Transdroid%20-%20Control%20rTorrent%20-%20Deluge%20-%20Transmission%20From%20Your%20Android%20Phone/main/hostname.png"><br>
<br>
<strong>User Name:</strong> <code>username</code> where <code>username</code> is your Feral username.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Transdroid%20-%20Control%20rTorrent%20-%20Deluge%20-%20Transmission%20From%20Your%20Android%20Phone/transmission/username.png"><br>
<br>
<strong>Password:</strong> <code>*********</code>&nbsp; This password will be the password shown in your Slot Details page for the relevant slot.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/transmission.slotdetails.png"><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Transdroid%20-%20Control%20rTorrent%20-%20Deluge%20-%20Transmission%20From%20Your%20Android%20Phone/main/password.png"><br>
<br>
<strong>Port number</strong> <code>443</code><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Transdroid%20-%20Control%20rTorrent%20-%20Deluge%20-%20Transmission%20From%20Your%20Android%20Phone/main/port.png"><br>
<br>
<strong>Folder:</strong> <code>&#x2F;username&#x2F;transmission&#x2F;</code> (case sensitive and where username is your Feral username)<br>
<br>
 <strong>Important note:</strong> You need the leading <code>&#x2F;</code> at the beginning and the trailing <code>&#x2F;</code> at the end.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Transdroid%20-%20Control%20rTorrent%20-%20Deluge%20-%20Transmission%20From%20Your%20Android%20Phone/transmission/folderpath.png"><br>
<br>
<strong>Use SSL</strong> Make sure to tick this box<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Transdroid%20-%20Control%20rTorrent%20-%20Deluge%20-%20Transmission%20From%20Your%20Android%20Phone/main/ssl.png"><br>
<br>
<h3>Optional Settings</h3><br>
Click on <code>Optional Settings</code> now.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Transdroid%20-%20Control%20rTorrent%20-%20Deluge%20-%20Transmission%20From%20Your%20Android%20Phone/main/optionalsettings.png"><br>
<br>
<strong>Server OS:</strong> <code>Linux</code><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Transdroid%20-%20Control%20rTorrent%20-%20Deluge%20-%20Transmission%20From%20Your%20Android%20Phone/main/serveros.png"><br>
<br>
 <strong>Important note:</strong> You may need to close and restart Transdroid for it to actually connect. It can fail with an error until you force a restart.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Transdroid%20-%20Control%20rTorrent%20-%20Deluge%20-%20Transmission%20From%20Your%20Android%20Phone/main/forceend.png"><br>
<br>
If all settings were correctly entered you should now be able to connect:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Other%20software/Transdroid%20-%20Control%20rTorrent%20-%20Deluge%20-%20Transmission%20From%20Your%20Android%20Phone/transmission/transmissionfinal.png"><br>
<br>
