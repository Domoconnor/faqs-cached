<h1>ruTorrent - Plugins</h1>

        
ruTorrent&#x27;s features can be extended in many different ways through the use of plugins. Though some more common ones will be installed when installing ruTorrent itself there are lots more that can be added.<br>
<br>
<h2>Custom Plugins</h2>This section provides information on the most common custom plugins, how to install them and troubleshooting the most common problems that can arise. Please note though the plugins should work (if you follow the guide properly), Feral cannot provide much support for their use or help should anything go wrong. Please make sure you&#x27;ve read these FAQ pages fully as help on the problem may be covered already.<br>
<br>
This notice absolutely does not prevent you from raising a ticket should anything go wrong but please bear in mind staff may not be able to assist beyond basic troubleshooting (for example reinstalling, clarifying error messages and so on).<br>
<br>
<br>
<h3>Installing Custom Plugins - General Method</h3>Plugins can be added to ruTorrent simply by adding its directory to ruTorrent&#x27;s plugins directory. This is possible in a number of ways, but the easiest is SSH. If you&#x27;ve never used SSH commands the idea of using a terminal window may seem daunting. There is a guide on simply getting connected to your slot through SSH <a href="https://www.feralhosting.com/faq/view?question=12">here</a>.<br>
<br>
Unless contained in the list in the next section, execute the following commands to install a plugin, replacing <em>plugin_name</em> with the official name of the plugin:<br>
<br>
<pre><code>cd ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;rutorrent&#x2F;plugins&#x2F;
svn checkout <a href="https://github.com/Novik/ruTorrent/trunk/plugins/">https:&#x2F;&#x2F;github.com&#x2F;Novik&#x2F;ruTorrent&#x2F;trunk&#x2F;plugins&#x2F;</a><em>plugin_name</em>
</code></pre><br>
<br>
<h3>Installing Custom Plugins - Special Requirements</h3> Sometimes a plugin needs a different approach. This can be either because the download is located in a different place, another version is needed, the plugin depends on other software or because there are further steps needed to get the plugin up and running. Simply click through the following links to see the installation method and further help.<br>
<br>
<a href="https://www.feralhosting.com/faq/view?question=337">Unpack</a><br>
<a href="https://www.feralhosting.com/faq/view?question=142">Autodl-irssi</a><br>
<a href="https://www.feralhosting.com/faq/view?question=328">Screenshots</a><br>
<a href="https://www.feralhosting.com/faq/view?question=330">Filemanager</a><br>
<a href="https://www.feralhosting.com/faq/view?question=210">Fileshare</a><br>
<a href="https://www.feralhosting.com/faq/view?question=126">Feralstats</a> - linking your usage page to ruTorrent<br>
<a href="https://www.feralhosting.com/faq/view?question=184">Coloured Ratio Column</a><br>
<a href="https://www.feralhosting.com/faq/view?question=209">Mediastream</a><br>
<a href="https://www.feralhosting.com/faq/view?question=331">Fileupload</a> - using Plowshare to upload to service providers via ruTorrent<br>
<br>
<h2>Troubleshooting Default Plugins</h2><em>I&#x27;m experiencing issues with RSS feeds</em><br>
There are multiple known issues that can be seen with ruTorrent&#x27;s RSS plugin and it&#x27;s recommended that another method (for example <a href="https://www.feralhosting.com/faq/view?question=234">Flexget</a>) is used instead. If you want to try and troubleshoot the plugin instead, please see <a href="https://www.feralhosting.com/faq/view?question=162">this page</a>.<br>
<br>
<em>I get a message &quot;Ratio: Plugin failed to start&quot;</em><br>
This most often occurs when you&#x27;ve set too high a value in one of the fields. You&#x27;ll need to remove ratio.dat from your ruTorrent settings directory and refresh ruTorrent. The plugin should then be usable.<br>
<br>
The easiest way to remove ratio.dat is to execute this command via SSH:<br>
<pre><code>rm ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;rutorrent&#x2F;share&#x2F;users&#x2F;$(whoami)&#x2F;settings&#x2F;ratio.dat</code></pre><br>
As a rule of thumb you should leave the minimum percentage at 100% and use -1 (for unlimited) for any value you&#x27;re not looking to control. For example, if you want the ratio group to work based on time, set the maximum percentage to -1 rather than some massive percentage.<br>
<br>
