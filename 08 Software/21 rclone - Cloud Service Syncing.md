<h1>rclone - Cloud Service Syncing</h1>

        
        <h1>How to Install and Use rclone to Sync Files With Cloud Services</h1><br>
You can use rclone with many cloud services for uploading, downloading, and syncing your files. <br>
<br>
Rclone supports the following cloud services:<br>
- Amazon Cloud Drive (ACD)<br>
- Google Drive<br>
- Amazon S3 (Not ACD)<br>
- Openstack Swift &#x2F; Rackspace cloud files &#x2F; Memset Memstore<br>
- Dropbox<br>
- Google Cloud Storage (Differnt then Google Drive)<br>
- Microsoft One Drive<br>
- Hubic<br>
- Backblaze B2<br>
- Yandex Disk<br>
- The local filesystem<br>
<br>
<h2>Installation</h2><br>
<br>
First download <a href="http://rclone.org/downloads/">rclone</a>:<br>
<br>
<pre><code>wget <a href="http://downloads.rclone.org/rclone-current-linux-amd64.zip">http:&#x2F;&#x2F;downloads.rclone.org&#x2F;rclone-current-linux-amd64.zip</a> -O .&#x2F;bin&#x2F;rclone.zip</code></pre><br>
<br>
Unzip rclone<br>
<br>
<pre><code>unzip .&#x2F;bin&#x2F;rclone.zip</code></pre> <br>
<br>
Now move the rclone file<br>
<br>
<pre><code>mv .&#x2F;rclone-v1.29-linux-amd64&#x2F;rclone .&#x2F;bin&#x2F;</code></pre><br>
<br>
Delete the old files<br>
<br>
<pre><code>rm -rf .&#x2F;rclone-v1.29-linux-amd64&#x2F;</code></pre><br>
<pre><code>rm .&#x2F;bin&#x2F;rclone.zip</code></pre><br>
<br>
You&#x27;re done installing. Go ahead and setup your cloud service:<br>
<br>
[h2]Amazon Cloud Drive (ACD)[h2]<br>
<br>
Configure rclone<br>
<br>
<pre><code>rclone config</code></pre><br>
<br>
Now add your remote<br>
<br>
<pre><code>n</code></pre><br>
<br>
Enter Your Desired Name, for Amazon Cloud Drive, I suggest just putting acd<br>
<br>
<pre><code>acd</code></pre><br>
<br>
Storage:<br>
<br>
<pre><code>1</code></pre><br>
<br>
For client\_id and client\_secret, leave blank (just press enter)<br>
<br>
Now since were working on a headless machine say no<br>
<br>
<pre><code>n</code></pre><br>
<br>
Now for Amazon Cloud Drive setup, you need to install rclone on your local machine <br>
<br>
<h2>Windows</h2><br>
<br>
On Windows, download the windows file here: <a href="http://downloads.rclone.org/rclone-current-windows-amd64.zip">http:&#x2F;&#x2F;downloads.rclone.org&#x2F;rclone-current-windows-amd64.zip</a><br>
<br>
Unzip the files to your desired location, then open cmd and navigate to that location<br>
<br>
<pre><code>cd &#x2F;&lt;path&gt;&#x2F;rclone-v1.29-windows-amd64&#x2F;</code></pre><br>
<br>
Now authorize ACD<br>
<br>
<pre><code>rclone.exe authorize &quot;amazon cloud drive&quot;</code></pre><br>
<br>
The authorization page will open in your defualt web browser, login with your amazon account and return to the cmd window. <br>
<br>
Now, copy the code between &quot;Paste the following code into your remote machione ---&gt;&quot; and &quot;&lt;---End Paste&quot;<br>
<br>
If you are having issues coping the code, right click and click &quot;Select all&quot;. Then go to pastebin.com and paste it. Now copy the code between &quot;Paste the following code into your remote machione ---&gt;&quot; and &quot;&lt;---End Paste&quot;. You can close the pastebin tab. <br>
<br>
Paste the code in your server&#x27;s window<br>
<br>
Save the remote <br>
<br>
<pre><code>y</code></pre><br>
<pre><code>q</code></pre><br>
<br>
<h2>Linux</h2><br>
<br>
Download the appropriate files from the rclone download page: <a href="http://rclone.org/downloads/">http:&#x2F;&#x2F;rclone.org&#x2F;downloads&#x2F;</a><br>
<br>
Now enter these commands with your info where it should go<br>
<br>
<pre><code>
unzip rclone-v1.17-linux-amd64.zip
cd rclone-v1.17-linux-amd64
sudo cp rclone &#x2F;usr&#x2F;sbin&#x2F;
sudo chown root:root &#x2F;usr&#x2F;sbin&#x2F;rclone
sudo chmod 755 &#x2F;usr&#x2F;sbin&#x2F;rclone
sudo mkdir -p &#x2F;usr&#x2F;local&#x2F;share&#x2F;man&#x2F;man1
sudo cp rclone.1 &#x2F;usr&#x2F;local&#x2F;share&#x2F;man&#x2F;man1&#x2F;
sudo mandb 
</code></pre><br>
<br>
Now setup your Remote<br>
<br>
<pre><code>rclone authorize &quot;amazon cloud drive&quot;</code></pre><br>
<br>
The authorization page will open in your defualt web browser, login with your amazon account and return to the cmd window. <br>
<br>
Now, copy the code between &quot;Paste the following code into your remote machine ---&gt;&quot; and &quot;&lt;---End Paste&quot;<br>
<br>
If you are having issues coping the code, right click and click &quot;Select all&quot;. Then go to pastebin.com and paste it. Now copy the code between &quot;Paste the following code into your remote machine ---&gt;&quot; and &quot;&lt;---End Paste&quot;. You can close the pastebin tab. <br>
<br>
Paste the code in your server&#x27;s window<br>
<br>
Save the remote <br>
<br>
<pre><code>y</code></pre><br>
<pre><code>q</code></pre><br>
<br>
Your all done! See below for rclone useage<br>
<br>
<h2>Google Drive</h2><br>
<br>
Configure rclone<br>
<br>
<pre><code>rclone config</code></pre><br>
<br>
Now add your remote<br>
<br>
<pre><code>n</code></pre><br>
<br>
Enter Your Desired Name, for Google Drive, I suggest just putting gdrive<br>
<br>
<pre><code>gdrive</code></pre><br>
<br>
Storage:<br>
<br>
<pre><code>6</code></pre><br>
<br>
For client\_id and client\_secret, leave blank (just press enter)<br>
<br>
Now since were working on a headless machine say no<br>
<br>
<pre><code>n</code></pre><br>
<br>
Now copy the link your given by rclone and go to it in your browser, login to your Google account, click &quot;Allow&quot;<br>
<br>
You will key a textbox with a key, copy the key and paste it into rclone<br>
<br>
Now save the remote<br>
<br>
<pre><code>y</code></pre><br>
<pre><code>q</code></pre><br>
<br>
Your all done, see below for usage<br>
<br>
<h2>Usage</h2><br>
<br>
To Upload by Copying<br>
<br>
<pre><code>rclone copy &#x2F;path&#x2F;to&#x2F;file &lt;remote name&gt;:&lt;remote path&gt;</code></pre><br>
<br>
To Upload by Moving<br>
<br>
<pre><code>rclone moving &#x2F;path&#x2F;to&#x2F;file &lt;remote name&gt;:&lt;remote path&gt;</code></pre><br>
<br>
To Upload by Sync (Won&#x27;t upload already uploaded files)<br>
<br>
<pre><code>rclone sync &#x2F;path&#x2F;to&#x2F;file&#x2F; &lt;remote name&gt;:&lt;remote path&gt;</code></pre><br>
<br>
To ls your cloud service<br>
<br>
<pre><code>
ls &lt;remote name&gt;:&lt;remote path&gt;
lsd &lt;remote name&gt;:&lt;remote path&gt;
lsl &lt;remote name&gt;:&lt;remote path&gt;
</code></pre><br>
<br>
To delete <br>
<br>
<pre><code>rclone delete &lt;remote name&gt;:&lt;remote path&gt;</code></pre><br>
<br>
For more commands and help<br>
<br>
<pre><code>rclone help</code></pre>
<br>