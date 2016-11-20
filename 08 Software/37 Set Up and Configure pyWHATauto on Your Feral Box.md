<h1>Set Up and Configure pyWHATauto on Your Feral Box</h1>

        
<br>
<strong>1:</strong> Download <a href="https://github.com/jimrollenhagen/pywhatauto/archive/master.zip">pyWHATauto</a>.<br>
<br>
<strong>2:</strong> Extract it to any folder you want, let&#x27;s say &#x2F;pyWHATauto&#x2F;. It can be anywhere, really.<br>
<br>
<strong>3:</strong> Edit the setup.conf file. There are examples there commented out by &#x27;;&#x27;. Fill out your information and save it.<br>
<br>
<strong>4:</strong> Edit the credentials.conf file. Currently only whatcd and broadcasthenet are fully functional. Each option should be self-explanatory, but just in case:<br>
<br>
4.1: enabled: is this site enabled?<br>
4.2: nickowner: what is the ident of the owner of the bot? For example, on what.cd mine is set to: 34038@johnnyfive.member.what.cd<br>
4.3: chanfilter: What channels on this network should I join on connect? Multiple entries can be separated by commas.<br>
4.4: username: The username on the website you use.<br>
4.5: password: The password on the website you use.<br>
4.6: botNick: The nickname of the bot which will join the IRC network.<br>
4.7: irckey: The IRCkey set at the website.<br>
4.8: nickServPass: The registration password for the botNick to authorize to nickserv.<br>
4.9: watch: This is the only tricky one. This watch folder will only by used for manual downloads on this network.<br>
<br>
<strong>5:</strong> Edit the filters.conf file. Woohooo here&#x27;s where the fun begins!<br>
<br>
5.1: At the top of each example filter is a list of the allowed filter options for that site.<br>
5.2: Each tag&#x2F;filter option can have multiple values, separated either by commas or newline+tab.<br>
5.3: &quot;site&quot; and &quot;filtertype&quot; are important! Look at the examples to see how they are used.<br>
5.4: &quot;enabled&quot; will toggle whether the filter is on or off.<br>
<br>
<strong>6:</strong> From there, depending on your OS, you can start the program. On linux navigate to the folder that holds WHATauto.py, and type &quot;python WHATauto.py&quot;. That&#x27;s it! If you want to screen it, just do &quot;screen python WHATauto.py&quot;.<br>
<br>
<strong>7:</strong> It should be running, and connected to some networks.<br>
<br>
<strong>8:</strong> Connect to said networks with your favorite IRC program. Make sure you are ident&#x27;d with Nickserv and the network bot.<br>
<br>
<strong>9:</strong> Type %help in the #whatbot channel. See if it responds. If all went well, you should receive a reply in the channel.<br>
<br>
<br>
---<br>
an alternative guide is available on what.cd: <a href="https://ssl.what.cd/forums.php?action=viewthread&#x26;threadid=88314">https:&#x2F;&#x2F;ssl.what.cd&#x2F;forums</a><br>
<br>
