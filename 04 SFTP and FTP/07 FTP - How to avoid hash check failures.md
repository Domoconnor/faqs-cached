<h1>FTP - How to avoid hash check failures</h1>

        
<h3>Background</h3><br>
<br>
FTP and SFTP are good ways to transfer data between a seedbox and a personal computer, but there is a problem: Many FTP&#x2F;SFTP clients use &quot;ASCII mode&quot; to transfer .CUE, .LOG, and .M3U files, and this can modify the files and cause hash check failures. That can cost you precious ratio, if you don&#x27;t notice it in time.<br>
<br>
<h3>Why this happens</h3><br>
<br>
FTP can transfer files in either of two &quot;modes&quot;:<br>
<br>
â€” binary mode transfers an exact copy, byte for byte.<br>
<br>
â€” ASCII mode modifies the file. Most often, this means that the way a new line is encoded is changed. On Windows PCs, new lines are demarcated by the bytes \x0D\x0A. On Mac OS X and Linux, new lines are demarcated by \x0A. You might think, &quot;this won&#x27;t be a problem for me, I use the same operating system on my seedbox and my laptop,&quot; but it is still a problem because you may not be using the same operating system as the person who created the torrent. If Alice creates a torrent on a PC which includes \x0D\x0A, and then Bob downloads it onto his Mac seedbox, the download will still be PC-formatted. He can seed it without hash check failures. If Bob then FTPs this file over to his other Mac using &quot;ASCII mode&quot;, it will &quot;translate&quot; that \x0D\x0A into \x0A. If Bob then tries to seed it, there will be a hash check failure because the file has changed.<br>
<br>
<h3>How to fix it</h3><br>
<br>
Set your FTP client to ALWAYS use binary mode. Note: This is not possible in some FTP clients. In that case, you need to find a different FTP client.<br>
<br>
<strong>Specific advice for Mac users:</strong><br>
<br>
1. Install Fetch.<br>
<br>
2. Go to the Fetch menu and select &quot;Preferences&quot;, then go to the &quot;Download&quot; tab.<br>
<br>
3. Set &quot;Default download mode&quot; to &quot;Binary&quot;.<br>
<br>
4. Uncheck the box for &quot;Decoding and expansion&quot; â€” leaving this box checked can lead to hash check failures, because it will unzip .ZIP files, etc.<br>
<br>
5. Go to the &quot;Upload&quot; tab, and set &quot;Default upload format&quot; to &quot;Binary (raw data)&quot;.<br>
<br>
6. Go to the &quot;Obscure&quot; tab, and under &quot;Editing text files&quot; uncheck the box for &quot;Use text mode transfers&quot;. For some stupid reason, this actually matters even if you aren&#x27;t editing text files. This may be a bug.<br>
<br>
7. Quit Fetch and then restart.<br>
<br>
---<br>
The guide was originally <a href="https://ssl.what.cd/forums.php?action=viewthread&#x26;threadid=99575">posted on what.cd</a> by user bollweevil.
<br>