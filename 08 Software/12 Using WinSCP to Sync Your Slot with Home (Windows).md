<h1>Using WinSCP to Sync Your Slot with Home (Windows)</h1>

        
Easily sync your Server with your Windows PC<br>
<br>
Install WinSCP from the official site <br>
<a href="http://winscp.net/eng/index.php">http:&#x2F;&#x2F;winscp.net&#x2F;eng&#x2F;index.php</a><br>
<br>
The main install includes the Command Line Options which we will be using.<br>
<br>
Just click Next Next Finish on the WinSCP and install as standard.<br>
<br>
We will create a .bat file to copy from our Slot to our home computer, this will only copy new content that is not on our home machine already.<br>
<br>
Open a new Notepad in windows and copy the following into the Notepad window replacing elements in curly braces { } with your information.<br>
<br>
winscp.com &#x2F;command ^<br>
&nbsp; &nbsp; &quot;open s<a href="ftp://">ftp:&#x2F;&#x2F;</a>{username}:{password}@{slotname}.feralhosting.com&#x2F;&quot; ^<br>
&nbsp; &nbsp; &quot;get -neweronly &#x2F;{location on your slot}&#x2F;* {homecomputerlocation}&quot; ^<br>
&nbsp; &nbsp; &quot;exit&quot;<br>
<br>
<br>
<br>
here is my example with the username &amp; password removed.<br>
<br>
<br>
winscp.com &#x2F;command ^<br>
&nbsp; &nbsp; &quot;open s<a href="ftp://">ftp:&#x2F;&#x2F;</a>{username}:{password}@dione.feralhosting.com&#x2F;&quot; ^<br>
&nbsp; &nbsp; &quot;get -neweronly &#x2F;media&#x2F;sdn1&#x2F;home&#x2F;{username}&#x2F;.sickrage.tv.shows&#x2F;* D:\Media\TV\&quot; ^<br>
&nbsp; &nbsp; &quot;exit&quot;<br>
<br>
<br>
We then save our notepad as a .bat file inside the folder we installed WinSCP.<br>
<br>
Then you can easily set this bat file to run via a scheduled task.
<br>