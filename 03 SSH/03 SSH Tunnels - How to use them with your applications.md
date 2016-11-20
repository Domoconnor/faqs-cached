<h1>SSH Tunnels - How to use them with your applications</h1>

        
<br>
<h3>Using SSH Tunnels with your applications:</h3><br>
Once you have created and opened your tunnels in your SSH client you need to configure you applications to use them. This guide cannot possibly cover each and every program. Also your program needs to support proxying in some way. This will usually be in the settings or preferences somewhere under the title of <code>Proxy</code>&nbsp; &#x2F; <code>Network Settings</code> &#x2F; <code>Connection Settings</code>. Possibly as a subcategory of a section in the settings or options.<br>
<br>
With most programs you can either proxy directly using built in settings or with add-ons or plugins of some type like foxyproxy in Firefox and ProxyOmega in Chrome. We will look at the most common options that will be an applicable template to most other scenarios.<br>
<br>
<h3>FireFox&#x27;s Connection settings</h3><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/SSH%20Tunnels%20-%20How%20to%20use%20them%20with%20your%20applications/settings.png"><br>
<br>
<h3>Filezilla proxy settings</h3><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/SSH%20Tunnels%20-%20How%20to%20use%20them%20with%20your%20applications/filezilla.png"><br>
<br>
<h3>Firefox</h3><br>
<a href="https://addons.mozilla.org/en-US/firefox/addon/foxyproxy-standard/">Firefox Foxy Proxy</a><br>
<br>
This is the best method for firefox. A very customizable proxy addon. <br>
<br>
<strong>1:</strong> Make sure the Proxies tab is selected.<br>
<br>
<strong>2:</strong> Click on the Add New Proxy button.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/SSH%20Tunnels%20-%20How%20to%20use%20them%20with%20your%20applications/foxyproxy1.png"><br>
<br>
<strong>1:</strong> Make sure the Proxy Details tab is selected.<br>
<br>
<strong>2:</strong> Select <code>Manual Proxy Configuration</code><br>
<br>
<strong>3:</strong>&nbsp; Enter <code>127.0.0.1</code> as the Host or IP address.<br>
<br>
<strong>4:</strong> Select the port you configured when creating the SSH tunnel.<br>
<br>
<strong>5:</strong> Select the <code>SOCKS v5</code> option<br>
<br>
<strong>6:</strong> Click OK or optionally configure some settings in the other tabs described below.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/SSH%20Tunnels%20-%20How%20to%20use%20them%20with%20your%20applications/foxyproxy2.png"><br>
<br>
<strong>1:</strong> Select the <code>URLS patterns</code> tab.<br>
<br>
<strong>2:</strong> Check the box to not use this proxy on local connections.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/SSH%20Tunnels%20-%20How%20to%20use%20them%20with%20your%20applications/foxyproxy3.png"><br>
<br>
<strong>1:</strong> Select the <code>General</code> tab.<br>
<br>
<strong>2:</strong> Give your proxy a name.<br>
<br>
<strong>3:</strong> Optional: You can change the colour of the proxy profile here.<br>
<br>
<strong>4:</strong> Optional: Configure browser cache settings in relation to the proxy.<br>
<br>
<strong>5:</strong> Optional: Configure browser cookie settings in relation to the proxy.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/SSH%20Tunnels%20-%20How%20to%20use%20them%20with%20your%20applications/foxyproxy4.png"><br>
<br>
<h3>Chrome</h3><br>
<a href="https://chrome.google.com/webstore/detail/proxy-switchyomega/padekgcemlokbadohgkifijomclgjgif">Proxy SwitchyOmega</a><br>
<br>
Chrome does not give the user any useful built in network&#x2F;proxy options. The plugin below is the best choice to do this (it is a good plugin)<br>
<br>
Once you have installed the plugins, click on it&#x27;s icon and click on <code>Options</code> and create a new profile.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/SSH%20Tunnels%20-%20How%20to%20use%20them%20with%20your%20applications/proxyomega1.png"><br>
<br>
Now give create a new profile and select the&nbsp; Proxy profile.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/SSH%20Tunnels%20-%20How%20to%20use%20them%20with%20your%20applications/proxyomega2.png"><br>
<br>
After you have saved, you can click on the icon to select from any configured proxies.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/SSH%20Tunnels%20-%20How%20to%20use%20them%20with%20your%20applications/proxyomega3.png"><br>
<br>
Now:<br>
<br>
<strong>1:</strong> Select <code>SOCKS5</code><br>
<br>
<strong>2:</strong> Enter <code>127.0.0.1</code><br>
<br>
<strong>3:</strong> Select a port between the range of <code>10001</code> to <code>32001</code><br>
<br>
<strong>4:</strong> Apply the changes<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/SSH%20Tunnels%20-%20How%20to%20use%20them%20with%20your%20applications/proxyomega4.png"><br>
<br>
Once saved, you can select the icon again to see and select your new proxy connections.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/SSH/SSH%20Tunnels%20-%20How%20to%20use%20them%20with%20your%20applications/proxyomega5.png"><br>
<br>

