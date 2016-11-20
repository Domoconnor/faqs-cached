<h1>Air Video HD</h1>

        
Air Video HD is an iOS app that allows you to watch videos streamed instantly from your computer on your iPhone, iPad, iPod Touch or Apple TV. <br>
No need to worry about converting or transferring files.&nbsp; Even videos not natively supported by iOS will play fine and they can be downloaded to your device for watching later&#x2F;offline!<br>
<br>
It can be configured to stream videos from your Feral slot, instead of your local computer.<br>
<br>
Before proceeding, you must do two things:<br>
<br>
1) Raise a support ticket with Feral staff and ask them to install the VLC libraries on your slot<br>
2) Download the Air Video iOS app using the App Store on your device<br>
<br>
Having done 1 and 2 above, first of all, ssh into your slot using Terminal on your Mac (or Windows equivalent), using the following command:<br>
<br>
<code>ssh &lt;username&gt;@&lt;slot&gt;.feralhosting.com</code>, where <code>&lt;username&gt;</code> is your Feral username and <code>&lt;slot&gt;</code> is the name of your Feral slot.<br>
<br>
Once in an ssh session, use the mkdir command to create a directory for AirVideo:<br>
<br>
<pre><code>mkdir AirVideo</code></pre><br>
<br>
Now navigate to this new directory using the CD command:<br>
<br>
<pre><code>cd AirVideo</code></pre><br>
<br>
Now enter the following command to download Air Video HD Server:<br>
<br>
<pre><code>wget <a href="https://s3.amazonaws.com/AirVideoHD/Download/AirVideoServerHD-2.2.3.tar.bz2">https:&#x2F;&#x2F;s3.amazonaws.com&#x2F;AirVideoHD&#x2F;Download&#x2F;AirVideoServerHD-2.2.3.tar.bz2</a></code></pre><br>
<br>
Now unzip using the following command:<br>
<br>
<pre><code>bzip2 -d AirVideoServerHD-2.2.0.tar.bz2</code></pre><br>
<br>
Now run the following command to extract the tar file:<br>
<br>
<pre><code>tar -xvf AirVideoServerHD-2.2.0.tar</code></pre><br>
<br>
Now we need to edit the Server.properties file to add the path containing the videos we wish to share.&nbsp; The following command opens the file in a text editor, ready for editing:<br>
<br>
<pre><code>nano Server.properties</code></pre><br>
<br>
Scroll down to the Sharing settings section and set sharedFolders1.path (and sharedFolders2.path if you want to share a second folder) accordingly - set it to the path of a folder on your slot that contains videos you wish to make available in the Air Video app.<br>
<br>
You can look through this file and change any other settings you see fit by amending their entry.<br>
<br>
Once you’ve set the folder paths, press Ctrl + O (letter O, not number zero) to save the file, press Return to overwrite the existing settings, then press Ctrl + X to exit the text editor.<br>
<br>
Next we need to start the server, using:<br>
<br>
<pre><code>screen bash start.sh</code></pre><br>
<br>
Now, open Air Video on your iOS device.&nbsp; Click the + icon to add a server, then choose Specify Manually.<br>
<br>
Enter the host as:<br>
<br>
<code>&lt;username&gt;.&lt;slot&gt;.feralhosting.com</code> (where <code>&lt;username&gt;</code> is your Feral username and <code>&lt;slot&gt;</code> is the name of your Feral slot)<br>
<br>
For the port number, use the default <code>45633</code> (unless you changed it in the <code>Server.properties</code> file above).<br>
<br>
That&#x27;s it - all being well you should now be able to browse the folder(s) specified in Server.properties above and stream any video files in these folders directly to your iOS device, even if they are in a format not natively supported by iOS.&nbsp; You can even download the videos to your device for watching whilst offline!
<br>