<h1>OpenVPN - start and connect everytime I log onto a Windows 7 system</h1>

        
How do I get OpenVPN to start and connect every time I log onto Windows 7 system? <br>
<br>
First you must setup OpenVPN correctly and according to this FAQ: <a href="https://www.feralhosting.com/faq/view?question=5">OpenVPN</a><br>
<br>
After you have set up OpenVPN GUI properly, start by navigating to the Task Scheduler under Start-&gt;All Programs-&gt;Accessories-&gt;System Tools and double clicking to open the Task Scheduler.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Installable%20software/OpenVPN%20-%20start%20and%20connect%20everytime%20I%20log%20onto%20a%20Windows%207%20system/1.jpg"><br>
<br>
Once the Task Scheduler launches, click on the Task Scheduler Library subheading on the left and click Create Task (not &#x27;Create Basic Task&#x27;) in the right window panel.<br>
<br>
Another windows will pop up with the tabs GENERAL, TRIGGERS, ACTIONS, CONDITIONS, SETTINGS. <br>
Under the GENERAL tab, type in a name for the task like &quot;OpenVPN&quot; or whatever you want. <br>
Also make sure that you check the &quot;Run with highest privileges&quot; dialog box and that the drop down menu below that says &quot;Configured for Windows Vista, Windows Server 2008&quot;<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Installable%20software/OpenVPN%20-%20start%20and%20connect%20everytime%20I%20log%20onto%20a%20Windows%207%20system/2.jpg"><br>
<br>
(note: if you change this last setting to configured for Windows 7 and Windows Server 2008 R2, you will not get a handy system tray icon when OpenVPN is connected)<br>
<br>
Now move on to the next tab TRIGGERS. Click &#x27;New&#x27; button to get another pop up window to configure.<br>
<br>
For the &quot;Begin the task&quot; drop down menu, select &#x27;At log on&#x27; and make sure the last dialog box for &#x27;enable&#x27; is checked and then click &#x27;OK&#x27;<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Installable%20software/OpenVPN%20-%20start%20and%20connect%20everytime%20I%20log%20onto%20a%20Windows%207%20system/3.jpg"><br>
<br>
(note: If you are on a system that you don&#x27;t need to log into, you may want to add multiple triggers to include &#x27;at startup&#x27;! More on this later.)<br>
<br>
Now goto the &#x27;ACTIONS&#x27; tab and click &#x27;New&#x27; button.<br>
<br>
For &#x27;Action&#x27; setting choose &#x27;Start a program&#x27; and then browse to where the &quot;openvpn-gui.exe&quot; was installed.<br>
(note: On Windows systems it is usually found here by default for:<br>
<br>
x86 version:<br>
<br>
<pre><code>C:\Program Files (x86)\OpenVPN\bin\openvpn-gui.exe</code></pre><br>
x64 version:<br>
<br>
<pre><code>C:\Program Files\OpenVPN\bin\openvpn-gui.exe</code></pre><br>
After This you have to add the following line into the box labeled &quot;Add arguments (optional):&quot;<br>
<br>
<pre><code>--connect client.ovpn --silent_connection 1</code></pre><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Installable%20software/OpenVPN%20-%20start%20and%20connect%20everytime%20I%20log%20onto%20a%20Windows%207%20system/4.jpg"><br>
<br>
(note: only the first argument is required, but the &#x27;--silent_connection 1&#x27; is nice because it keeps the GUI for OpenVPN from cluttering your screen while it runs its scripts)<br>
<br>
Then click &#x27;OK&#x27;<br>
<br>
Under CONDITIONS Tab the only setting you should have to change is to check the box for &quot;Start only if the following network connection is available:&quot; and make it for &#x27;Any connection&#x27;<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Installable%20software/OpenVPN%20-%20start%20and%20connect%20everytime%20I%20log%20onto%20a%20Windows%207%20system/5.jpg"><br>
<br>
For the all those who like to live dangerous and either have no logon screen, or have it automatically set to enter your credentials when you boot into windows, you must also take the following some further steps to ensure OpenVPN will run automatically.<br>
<br>
For all those who use a password protected logon screen that requires credentials to be entered, this is as far as you have to go.<br>
Just click &#x27;OK&#x27; to complete creating this task. Exit Task Scheduler, and log off and back into Windows to test it out. <br>
All should work like a charm.<br>
<br>
Now for the rest of you that do not use login... Navigate to the SETTINGS<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Installable%20software/OpenVPN%20-%20start%20and%20connect%20everytime%20I%20log%20onto%20a%20Windows%207%20system/6.jpg"><br>
<br>
Now make the following changes to these settings;<br>
<br>
--Check the box for &#x27;Allow task to be run on demand&#x27;<br>
--Check the box for &#x27;Run task as soon as possible after a scheduled start is missed&#x27;<br>
--Check the box for &#x27;If the task fails, restart every:&#x27; (set this to 1 minute)<br>
--Set the Attempt to restart up to: 3 times<br>
--(optional)-- you may uncheck &#x27;Stop the task if it runs longer than:&#x27; or change the lenghth.<br>
--Check the box for &#x27;If the running task does not end when requested, force it to stop&#x27;<br>
<br>
Leave the last box unchecked and do not change any other settings.<br>
<br>
Now navigate back over to the TRIGGERS tab and add another entry by clicking new. <br>
Make this new trigger so that the task will also start when the computer is booted up, by changing thwe event to &#x27;at startup&#x27;. (Those of you that use login do not need to worry about this)<br>
<br>
Click OK and all done. You can test by either rebooting or logging off. <br>
<br>
(note: Those of you that choose this second option of not using a login will have approximately a one minute delay before you will see OpenVPN starting up in your system tray)<br>
<br>

