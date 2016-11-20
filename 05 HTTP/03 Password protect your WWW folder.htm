<h1>Password protect your WWW folder</h1>

        
In SSH do the commands described in this FAQ. If you do not know how to SSH into your slot use this FAQ: <a href="https://www.feralhosting.com/faq/view?question=12">SSH Guide - The Basics</a> <br>
<br>
 <strong>Important notes:</strong> Please see the end of the FAQ for nginx.<br>
<br>
<h2>Htpasswd toolkit Bash script</h2><br>
This bash script provides some easy options to perform some common tasks.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Password%20protect%20your%20WWW%20folder/bashscript.png"><br>
<br>
In SSH do the commands described in this FAQ. If you do not know how to SSH into your slot use this FAQ: <a href="https://www.feralhosting.com/faq/view?question=12">SSH Guide - The Basics</a><br>
<br>
<pre><code>wget -qO ~&#x2F;htpasswdtk.sh <a href="http://git.io/eJySww">http:&#x2F;&#x2F;git.io&#x2F;eJySww</a> &amp;&amp; bash ~&#x2F;htpasswdtk.sh</code></pre><br>
This script will also get the latest version and copy it to your <code>~&#x2F;bin</code> directory and make it executable.<br>
So after you have run it for the first time you can simply do:<br>
<br>
<pre><code>htpasswdtk</code></pre><br>
<h2>How it works:</h2><br>
<h3>Apache:</h3><br>
You create a file called a <code>.htaccess</code> inside a directory in your WWW folder. You then populate this file with special instructions that Apache will interpret and apply to the web-server.<br>
<br>
For password protecting a directory you must use the <code>.htaccess</code> in tandem with a <code>.htpasswd</code> file that stores the username and password information for created users.<br>
<br>
So the <code>.htaccess</code> stores the setup information for the authentication that will look to a special <code>.htpasswd</code> file for the required user credentials.<br>
<br>
<h3>Nginx:</h3><br>
nginx does not use <code>.htaccess</code> files therefore you must use <code>conf</code> files and reload the web-server for the changes to take effect.<br>
<br>
Configurations settings are stored in the <code>conf</code> files loaded by nginx from this location:<br>
<br>
<pre><code>~&#x2F;.nginx&#x2F;conf.d&#x2F;000-default-server.d</code></pre><br>
So the <code>conf</code> file stores the set-up information for the authentication using location based directives that will look to a special <code>.htpasswd</code> file for the required user credentials.<br>
<br>
<h2>Section 1: Apache - creating our .htaccess</h2><br>
<strong>Step 1:</strong> In SSH we must first navigate to the directory we want to protect and then create the <code>.htaccess</code>.<br>
<br>
<pre><code>cd ~&#x2F;www&#x2F;$(whoami).$(hostname -f)&#x2F;public_html&#x2F;</code></pre><br>
This will move us into the root of our <code>WWW</code> folder<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Password%20protect%20your%20WWW%20folder/htaccess_0.png"><br>
<br>
This command will either open an existing file or create the new file upon saving using a text editor called nano, so now type:<br>
<br>
<pre><code>nano -w .htaccess</code></pre><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Password%20protect%20your%20WWW%20folder/htaccess_1.png"><br>
<br>
It will look something like this if you are doing this for the first time.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Password%20protect%20your%20WWW%20folder/htaccess_2.png"><br>
<br>
Now below is the info we are going to fill this file with but it it not ready yet. Open a text editor such as <a href="http://notepad-plus-plus.org/">NotePad ++</a> and edit it to reflect your unique settings such as username and paths. This is information for ONE user, YOU. We will see how to add users later on in Section 3.<br>
<br>
<pre><code>AuthName &quot;Secure Area&quot;
AuthType Basic
AuthUserFile &#x2F;media&#x2F;DISKID&#x2F;home&#x2F;username&#x2F;private&#x2F;.htpasswd

require user username</code></pre><br>
 <strong>Important note:</strong> Your full path may be a little different (your disk ID will not be in capital letters and your path may not contain home):<br>
<br>
<pre><code>AuthUserFile &#x2F;media&#x2F;DiskID&#x2F;username&#x2F;private&#x2F;.htpasswd</code></pre><br>
Use this command in <a href="https://www.feralhosting.com/faq/view?question=12">SSH</a> to check your path:<br>
<br>
<pre><code>echo $HOME</code></pre><br>
For example, this command will give the full path to a particular directory<br>
<br>
<pre><code>ls -d ~&#x2F;private&#x2F;.htpasswd</code></pre><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Password%20protect%20your%20WWW%20folder/htaccess_3.png"><br>
<br>
Once you have done this copy the text to your clipboard, then back in the SSH window press press <code>SHIFT + INS</code> (or right mouse-click in PuTTy or KiTTy) to paste it into your nano window<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Password%20protect%20your%20WWW%20folder/htaccess_4.png"><br>
<br>
As you can see, we are telling <code>.htaccess</code> 2 things: <br>
<br>
<strong>1:</strong> Where to look for the file containing the password, in this case it is called <code>.htpasswd</code><br>
<br>
<strong>2:</strong> What user to authenticate with that password.<br>
<br>
We are done with creating our <code>.htaccess</code> file. Press and hold <code>CTRL</code> then press <code>x</code> to save and exit nano. It will ask: Save modified buffer? Press <code>Y</code> to save changes, and then <code>ENTER</code> to confirm.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Password%20protect%20your%20WWW%20folder/htaccess_5.png"><br>
<br>
Now press enter to save it with the correct filename.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Password%20protect%20your%20WWW%20folder/htaccess_6.png"><br>
<br>
We now need to change permissions on the file. Type:<br>
<br>
<pre><code>chmod 600 .htaccess</code></pre><br>
As long as you are still in this <code>public_html</code> directory<br>
<br>
The system will respond with a blank line.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Password%20protect%20your%20WWW%20folder/htaccess_7.png"><br>
<br>
That is it. You have successfully created you <code>.htaccess</code> file. Time to do the <code>.htpasswd</code><br>
<br>
<h3>Final Notes for Section 1:</h3><br>
I recommend you place the <code>.htaccess</code> file only INSIDE the folders you wish to protect, you can do this via FTP(SFTP). This will let you give free access to some folders in your <code>WWW</code> but hide any that contain this <code>.htaccess</code> we just created.This means anyone can access the <code>WWW</code> folder, but cannot access folders restricted by your <code>.htaccess</code><br>
<br>
 <strong>Important note:</strong> To allow users access to only some folders and not others please see <strong>Final Notes Section 3:</strong><br>
<br>
To change our own password or other users inside an existing <code>.htpasswd</code> see Section 2.1<br>
<br>
<h2>Section 2: Creating our .htpasswd file</h2><br>
 <strong>Important notes:</strong> Please use a good password where the at least the first 8 characters are not easily guessable. A combination of Letters, numbers and mixed case will be perfect, for example: <strong>dHr6wY7l</strong> and so on.<br>
<br>
<strong>Step 2:</strong> Let&#x27;s now create our <code>.htpasswd</code> file. First we navigate to the Directory where we want to store it (we configured it earlier in our <code>.htaccess</code> file):<br>
<br>
<pre><code>cd ~&#x2F;private</code></pre><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Password%20protect%20your%20WWW%20folder/htpasswd_0.png"><br>
<br>
Now type:<br>
<br>
<pre><code>htpasswd -cm .htpasswd username</code></pre><br>
Use the same username that you configured earlier in <code>.htaccess</code>. The system will ask you to type in your desired password:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Password%20protect%20your%20WWW%20folder/htpasswd_1.png"><br>
<br>
You can use your own password, ( remember the info at the start of the guide about password managers and Chrome).<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Password%20protect%20your%20WWW%20folder/htpasswd_2.png"><br>
<br>
Type it or Paste it but remember you will not see anything as you type or that you pasted, that is normal. Press <strong>enter</strong> You will be asked to re-type your password, after which <code>.htpasswd</code> will be created.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Password%20protect%20your%20WWW%20folder/htpasswd_3.png"><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Password%20protect%20your%20WWW%20folder/htpasswd_4.png"><br>
<br>
We now need to change permissions on this file, too. Type:<br>
<br>
<pre><code>chmod 600 .htpasswd</code></pre><br>
This will <code>chmod</code> a file by the name of <code>.htpasswd</code> to <code>600</code> in our current location, in this case that is <code>~&#x2F;private</code><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Password%20protect%20your%20WWW%20folder/htpasswd_5.png"><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Password%20protect%20your%20WWW%20folder/htpasswd_6.png"><br>
<br>
And this is it. You have passworded your WWW directory for a single user.<br>
<br>
<h3>Final Notes for Section 2:</h3><br>
I recommend you place the <code>.htaccess</code> file only INSIDE the folders you wish to protect, you can do this via FTP(SFTP). This will let you give free access to some folder in your WWW but hide any that contain this <code>.htaccess</code> we just created.This means anyone can access the WWW folder, but cannot access folders restricted by your <code>.htaccess</code><br>
<br>
To allow users access to only some folders and not others please see the <strong>Final Notes Section 3:</strong> section<br>
<br>
 <strong>Important notes:</strong> If you receive an <code>Internal Server Error</code> message when you try to access your page&#x2F;directory, check for typing errors in your <code>.htaccess</code> file.<br>
<br>
To un-protect a directory, delete the <code>.htaccess</code> and the <code>.htpasswd</code> files, or just rename the <code>.htaccess</code> file to <code>.htaccess_off</code><br>
<br>
<h2>Section 2.1 Adding users</h2><br>
This will be what your <code>.htaccess</code> looks like.<br>
<br>
<pre><code>AuthName &quot;Secure Area&quot;
AuthType Basic
AuthUserFile &#x2F;media&#x2F;sde1&#x2F;home&#x2F;exampleuser&#x2F;private&#x2F;.htpasswd

require user exampleuser</code></pre><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Password%20protect%20your%20WWW%20folder/htpasswd_adduser_0.png"><br>
<br>
What we need to dis is add a new authorised user to access this directory.<br>
<br>
<pre><code>AuthName &quot;Secure Area&quot;
AuthType Basic
AuthUserFile &#x2F;media&#x2F;sde1&#x2F;home&#x2F;exampleuser&#x2F;private&#x2F;.htpasswd

require user exampleuser
require user guestuser</code></pre><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Password%20protect%20your%20WWW%20folder/htpasswd_adduser_1.png"><br>
<br>
Alternatively you can allow all valid users to access the directory. This will allow any user present in the .<code>htpasswd</code> file to access the protected directory. This simplifies the process for multiple users but will all anyone in the <code>.htpasswd</code> to access the directory.<br>
<br>
<pre><code>AuthName &quot;Secure Area&quot;
AuthType Basic
AuthUserFile &#x2F;media&#x2F;sde1&#x2F;home&#x2F;exampleuser&#x2F;private&#x2F;.htpasswd

require valid-user</code></pre><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Password%20protect%20your%20WWW%20folder/htpasswd_adduser_2.png"><br>
<br>
To change your own password inside an existing <code>.htpasswd</code> you must use the <code>.htpasswd</code> command. Replace <code>exampleuser</code> in the below command for the name of the user you wish to change&#x2F;update the password for.<br>
<br>
<pre><code>htpasswd ~&#x2F;private&#x2F;.htpasswd exampleuser</code></pre><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Password%20protect%20your%20WWW%20folder/htpasswd_adduser_3.png"><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Password%20protect%20your%20WWW%20folder/htpasswd_adduser_4.png"><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Password%20protect%20your%20WWW%20folder/htpasswd_adduser_5.png"><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Password%20protect%20your%20WWW%20folder/htpasswd_adduser_6.png"><br>
<br>
<strong>Section 3: Password Protecting a Directory for Multiple Users</strong><br>
<br>
To give multiple users access to one or more directories we must do two things. Assuming you have followed the steps in this guide we will add a new user to our <code>.htaccess</code> and give them a password by editing the <code>.htpasswd</code>. <br>
<br>
<strong>Step 1:</strong> To add your own users please edit the <code>.htaccess</code> file and add your user as shown in section <code>2.1</code> first to allow your specific user or to all all valid users.<br>
<br>
<strong>Step 2:</strong> Then use this command to add the new user to the <code>.htpasswd</code>, where you change <code>guestuser</code> to the name of the user you wish to add:<br>
<br>
<pre><code>htpasswd ~&#x2F;private&#x2F;.htpasswd guestuser</code></pre><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Password%20protect%20your%20WWW%20folder/htpasswd_update_0.png"><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Password%20protect%20your%20WWW%20folder/htpasswd_update_1.png"><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Password%20protect%20your%20WWW%20folder/htpasswd_update_2.png"><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/HTTP/Password%20protect%20your%20WWW%20folder/htpasswd_update_3.png"><br>
<br>
<strong>Final Notes Section 3:</strong><br>
<br>
To deny a user access to a folder you do no have to delete them from the <code>.htpasswd</code>. All you have to do is remove their user name from the <code>.htaccess</code> in the folders you do not wish them access to, so for example.<br>
<br>
<pre><code>require user exampleuser</code></pre><br>
Only <code>exampleuser</code> will have access to this folder. other users will not even see it exists. When a user visits your <code>WWW</code> folder they will only see and access folders that have their username in the <code>.htaccess</code> using our configuration.<br>
<br>
<strong>Section 4: Rutorrent Specific Info</strong><br>
<br>
The guide tells you everything you need to know in detail on how to change&#x2F;create the settings&#x2F;files you need. This is just to tell you where the relevant files if you wish to use the existing Rutorrent <code>.htaccess</code> and <code>.htpasswd</code><br>
<br>
Apache:<br>
<br>
The <code>.htaccess</code> is located here:<br>
<br>
<pre><code>~&#x2F;www&#x2F;username.server.feralhosting.com&#x2F;public_html&#x2F;rutorrent&#x2F;.htaccess</code></pre><br>
The <code>.htpasswd</code> is located here.<br>
<br>
<pre><code>~&#x2F;www&#x2F;username.server.feralhosting.com&#x2F;public_html&#x2F;rutorrent&#x2F;.htpasswd</code></pre><br>
nginx:<br>
<br>
The <code>rutorrent.conf</code> is located here:<br>
<br>
<pre><code>~&#x2F;.nginx&#x2F;conf.d&#x2F;000-default-server.d&#x2F;rutorrent.conf</code></pre><br>
The <code>.htpasswd</code> is located here.<br>
<br>
<pre><code>~&#x2F;www&#x2F;username.server.feralhosting.com&#x2F;public_html&#x2F;rutorrent&#x2F;.htpasswd</code></pre><br>
<strong>Final Notes for Section 4:</strong><br>
<br>
 <strong>Important notes:</strong> The ruTorrent <code>.htaccess</code> makes use of <br>
<br>
You can change the rutorrent <code>.htaccess</code> to link to another <code>.htpasswd</code> of your choosing (one created in Section 2 for example) by editing the file as described in Section 1.<br>
<br>
In this case the <code>.htpasswd</code> is stored within the <code>WWW</code> realm and not outside it (like the <code>.htpasswd</code> from Section 2 is). Moving this to somewhere outside the <code>WWW</code> is a good idea.<br>
<br>
<h2>nginx</h2><br>
nginx does not use <code>.htaccess</code> files. All settings are done in the configuration files.<br>
<br>
All locations are relative to the WWW root which is always:<br>
<br>
<pre><code>~&#x2F;www&#x2F;username.server.feralhosting.com&#x2F;public_html&#x2F;</code></pre><br>
Or if you added a VHost:<br>
<br>
<pre><code>~&#x2F;www&#x2F;somesite.co.uk&#x2F;public_html&#x2F;</code></pre><br>
You nginx configuration files stored here:<br>
<br>
<pre><code>~&#x2F;.nginx&#x2F;conf.d&#x2F;000-default-server.d</code></pre><br>
Create a new conf file and enter this information, for example:<br>
<br>
<pre><code>nano -w ~&#x2F;.nginx&#x2F;conf.d&#x2F;000-default-server.d&#x2F;links.conf</code></pre><br>
Then copy this information into it:<br>
<br>
<pre><code>location &#x2F;links {
&nbsp; &nbsp; auth_basic &quot;Please log in&quot;;
&nbsp; &nbsp; auth_basic_user_file &#x2F;media&#x2F;DiskID&#x2F;username&#x2F;path&#x2F;to&#x2F;.htpasswd;
}</code></pre><br>
Where:<br>
<br>
<code>&#x2F;media&#x2F;DiskID&#x2F;username&#x2F;path&#x2F;to&#x2F;.htpasswd</code> reflects the actual full path to your <code>.htpasswd</code>. You can use the method described in the Apache section of this FAQ to generate and manage your <code>.htpasswd</code> files.<br>
<br>
The press and hold <code>CTRL</code> then press <code>x</code> to save. Press <code>y</code> to confirm.<br>
<br>
For example, to password protect your server root you would do this:<br>
<br>
<pre><code>location &#x2F; {
&nbsp; &nbsp; auth_basic &quot;Please log in&quot;;
&nbsp; &nbsp; auth_basic_user_file &#x2F;media&#x2F;DiskID&#x2F;username&#x2F;path&#x2F;to&#x2F;.htpasswd;
}</code></pre><br>
Where:<br>
<br>
<pre><code>location &#x2F;</code></pre><br>
Is specifying the server root and not a sub directory.<br>
<br>
Then save the edits to the <code>links.conf</code> and reload your nginx configuration for the settings to take effect.<br>
<br>
<pre><code>&#x2F;usr&#x2F;sbin&#x2F;nginx -s reload -c ~&#x2F;.nginx&#x2F;nginx.conf</code></pre><br>
<strong>Important note:</strong> Please note you may need to clear your browser cache for changes to reflected in your current browser session.<br>
<br>
<h2>Notes:</h2><br>
If you have an application, like Ampache, that has its own authentication you can disable basic auth for these location, if you have protected&nbsp; your entire WWW for example.<br>
<br>
<strong>Apache:</strong><br>
<br>
Add these two lines to a <code>.htaccess</code> inside the folder you wish to disable basic auth on. If the <code>.htaccess</code> does not exist in the desired location then create it.<br>
<br>
<pre><code>Satisfy Any
Allow from all</code></pre><br>
<strong>nginx:</strong><br>
<br>
Create a location based rule in any existing conf file located at: <code>~&#x2F;.nginx&#x2F;conf.d&#x2F;000-default-server.d&#x2F;</code> or create a new one there just for this, for example:<br>
<br>
<pre><code>~&#x2F;.nginx&#x2F;conf.d&#x2F;000-default-server.d&#x2F;ampache.conf</code></pre><br>
Then add this to the file then save.<br>
<br>
<pre><code>location &#x2F;ampache {
&nbsp; &nbsp; auth_basic&nbsp; off;
}</code></pre><br>
Then reload nginx using this command:<br>
<br>
<pre><code>&#x2F;usr&#x2F;sbin&#x2F;nginx -s reload -c ~&#x2F;.nginx&#x2F;nginx.conf</code></pre>
<br>