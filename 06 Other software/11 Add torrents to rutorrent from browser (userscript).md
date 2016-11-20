<h1>Add torrents to rutorrent from browser (userscript)</h1>

        
<br>
This is a userscript that will allow you to add torrents to your uTorrent through any browser that supports userscripts (commonly Chrome via Tampermonkey and FireFox via Greasemonkey). This also works<br>
<br>
Supports sites: What, PTP, BTN, SCC, BIB, AB, bB, TPB, Demonoid, D-Addicts (and would probably work on others, especially gazelle based trackers, if you edit them into the include portion of your script (explained here: <a href="http://wiki.greasespot.net/Include_and_exclude_rules">Include_and_exclude_rules</a>)<br>
<br>
It looks like this: <br>
<br>
<img src="https://raw.github.com/SaberSalv/saber-addtorrent/master/snapshot.jpg"><br>
<br>
<strong>1:</strong> Go and get the <a href="http://userscripts.org/scripts/show/150375">saber-addtorrent Grease Monkey Script</a><br>
<br>
<strong>2:</strong> Press install.<br>
<br>
<strong>3:</strong> After installation, go to one of the supported sites (I&#x27;m going to use PtP in my example).<br>
<br>
<strong>4:</strong> Go to a torrent page. This will be the movie&#x2F;album&#x2F;season page, not the artist or series page. Scroll to the bottom, and find the button highlighted in the image below (though, the CSS on what.cd seems to be messed up, and the config button shows up below the header, so if you can&#x27;t find it, look around the page some).<br>
<br>
<img src="http://i.imgur.com/Gtg5cyz.png"><br>
<br>
<strong>5:</strong> Click that link, and the box you see will pop up. Put in the details for your rutorrent. You can easily get these by going to <a href="https://www.feralhosting.com/manager/">manager&#x2F;slot&#x2F;server</a> and scrolling down to your rutorrent info under Installed Software. I recommend HTTPS, always.<br>
<br>
<strong>Main settings</strong><br>
<br>
This isn&#x27;t exactly intuitive. The first box will set the number of download link images you will see. The second box will change what label the corresponding download link will apply to that torrent in rutorrent. I just set mine to 1 and a general sort tag, but you could add as many as you want for advanced labelling. <br>
<br>
Example:<br>
<br>
<img src="http://i.imgur.com/oSEqqX1.png"><br>
<br>
The bottom boxes are for setting images, so you could use something like favicons for each link, or just leave it how it is for the defaults.. And it changes to the second image after you&#x27;ve downloaded it.<br>
<br>
