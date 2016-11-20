<h1>Generic Software Installation Guide</h1>

        
<br>
<h2>Generic Software Guide Introduction:</h2><br>
<strong>Important note:</strong> Just because you can do something does not automatically mean you should. For example, custom python installations tend to cause more problems than they solve.&nbsp; Also if you think the programs you want to install will interfere with other users or that Staff might not want you using them you should <a href="https://www.feralhosting.com/manager/tickets/new">open a ticket</a> and ask first. Please use some common sense with the programs you try to install and use.<br>
<br>
With your Feral slot you do not have <code>root</code> access to the server. Your account runs as user account in a Debian Linux environment. These are not dedicated servers which means you cannot use these commands on your slot:<br>
<br>
<pre><code>apt-get
su
sudo</code></pre><br>
This does not mean you cannot install software on your slot. It does means that you will have to attempt to install it to your <code>HOME</code> directory, or below, manually. <strong>There is no official support from Feral staff for users doing this</strong>. You can open a ticket to ask for any standard dependencies to be installed to your slot that you may require. Again this comes down to common sense when looking at the nature of the application and dependencies.<br>
<br>
For this guide we will look at the methods available to you to install software on your slot. The main methods for installing software are:<br>
<br>
<strong>1:</strong> Pre-compiled binaries or scripts created by the developers or similar. Examples of this include:<br>
<br>
- ffmpeg<br>
- java<br>
- Python programs like flexget<br>
<br>
<strong>2:</strong> Source-code to compile the binary on your slot. Examples of this include:<br>
<br>
- git<br>
- znc<br>
<br>
<strong>3:</strong> Some Debian packages via unpacking them to access the binary.<br>
<br>
- Spideroak<br>
-&nbsp; filebot<br>
<br>
It is important that you understand that no single one of these methods is a guaranteed thing. There are many factors that will contribute to the success or failure of the attempt. These could be dependencies on other applications, binaries, libraries or additional requirements that you have no way to fulfil. This is just something you will have to accept before attempting to install any software on your slot. In this linked examples you will see various methods and solutions to such issues.<br>
<br>
<h2>Installed Software locations:</h2><br>
Throughout the Feral FAQs you will see that all user installed programs are installed to a single location which is:<br>
<br>
<pre><code>$HOME</code></pre><br>
This is effectively your home directory and will mimic the conventional directory structure used by Unix type platforms for installing software, where applicable. Then you will see that this location is added to the <code>PATH</code> (this is done automatically at login if the folder exists):<br>
<br>
<pre><code>~&#x2F;bin</code></pre><br>
When we add a location to the <code>PATH</code> in Linux it basically tells the SSH terminal to include this location when it looks for the binaries to execute. If a location is not in the <code>PATH</code> you would be required to use a full path to that program in order to execute it in your terminal. This method is used for simplicity. All files are installed to the <code>~&#x2F;bin</code> folder and generally maintain a conventional directory structure.<br>
<br>
This FAQ will use the same directory structure for any examples used, though once you understand the process you can install applications where ever you want.<br>
<br>
You could then manage your installations and have more than one version of a program.<br>
<br>
<h2>CMAKE</h2><br>
Some applications do not use <code>configure</code> and instead require you use <code>cmake</code> to build them. You can use this guide to install and use <code>CMAKE</code>:<br>
<br>
<a href="https://www.feralhosting.com/faq/view?question=270">CMAKE - Basic Setup</a><br>
<br>
<h2>--prefix=$HOME</h2><br>
It is very common for source code application to come with an executable file called <code>configure</code>. When using this program to configure our source code for installation we can often pass it some arguments that tell it to do certain things or behave in a certain way. The most important of theses is the <code>--prefix</code> argument.<br>
<br>
 <strong>Important note:</strong> If the program does not come with a .configure file you may have to generate one yourself. Check the <code>README</code> or documentation. Sometimes it will be created by a file called <code>.autogen.sh</code>. The best way to know is to read the programs documentation.<br>
<br>
If you do not specify a <code>prefix</code> what happens is that <code>configure</code> will assume you want to use the standard file structure such as <code>&#x2F;etc</code> and <code>&#x2F;lib</code> for which you do not have permission to use. So what we do is specify a <code>--prefix</code> that tell <code>configure</code> where to install the application and subsequently where to find the files it needs to run.<br>
<br>
So when we pass this argument to <code>configure</code>:<br>
<br>
<pre><code>--prefix=$HOME</code></pre><br>
We are telling it to install the application to root of our slot using the variable <code>HOME</code>. For example, with the above <code>prefix</code> our application will use this as the root installation directory when configuring the application<br>
<br>
<pre><code>&#x2F;media&#x2F;12345&#x2F;home&#x2F;username</code></pre><br>
<strong>Important note:</strong> You can read the <code>configure</code> file with a text editor. In this file you will be able to find and see the available arguments you can use with this installation when you encounter some errors. the <code>configure</code> script is a text file you can open with a text editor. Open it and search for <code>--prefix</code> to find the rest of the options that may help solve the issue.<br>
<br>
In some cases <code>configure</code> does not exist or is not included with the files and you must refer to the developers documentation to see how the files are required to be processed. This may require you to run a <code>autogen</code> or <code>bootstrap</code> script first.<br>
<br>
<h2>Alternative Software locations:</h2><br>
Say you wanted multiple versions of a program installed. If you installed them all to <code>$HOME</code> you would just overwrite the previous version as it installed. To avoid this you would use a different <code>--prefix</code> when configuring, for example:<br>
<br>
<pre><code>--prefix=$HOME&#x2F;python27</code></pre><br>
<pre><code>--prefix=$HOME&#x2F;python30</code></pre><br>
Or if you wanted all custom software in a managed location:<br>
<br>
<pre><code>--prefix=$HOME&#x2F;applications&#x2F;python&#x2F;python27</code></pre><br>
<pre><code>--prefix=$HOME&#x2F;applications&#x2F;python&#x2F;python30</code></pre><br>
<h2>PATH explained:</h2><br>
<strong>Important note:</strong> The location <code>~&#x2F;bin</code> is automatically added to your system PATH if the folder exists, upon logging into your SSH session. This is done by loading a setting in the <code>~&#x2F;.profile</code> file on your slot when you log in via SSH. The examples used in the explanation below are for demonstration purposes only.<br>
<br>
The concept of the <code>PATH</code> for new users can be a difficult one to come to terms with so I will briefly explain it here.<br>
<br>
Your terminal makes use of all kinds of variables when processing information. <code>PATH</code> is one of these variables. <code>PATH</code> is basically just a list of locations, in order of preference from left to right, that the shell will look at when searching for a binary to execute. So when I use certain command in the terminal like <code>cp</code> or <code>mv</code> or <code>rm</code> I don&#x27;t have to use the full path to the binary each and every time. Being a variable is means we can modify those locations to suit our needs and this will in turn be reflected in the behaviour of our terminal. The command for doing this will be used and explained through the FAQ.<br>
<br>
One thing to consider when adding locations to the <code>PATH</code> variable is the order in which you wish the locations to be checked. Here is a standard entry to include a location to the <code>PATH</code> variable and I will explain this by breaking it down:<br>
<br>
<pre><code>PATH=~&#x2F;bin:$PATH</code></pre><br>
This is the variable we are modifying by saying <code>PATH</code> equals something. Like this:<br>
<br>
<pre><code>PATH=</code></pre><br>
This is the location we are including:<br>
<br>
<pre><code>~&#x2F;bin</code></pre><br>
This means that we want to come before, or on the left of the existing <code>PATH</code> locations<br>
<br>
<pre><code>:$PATH</code></pre><br>
To have it come after you would do this:<br>
<br>
<pre><code>PATH=$PATH:~&#x2F;bin</code></pre><br>
An example of this in use:<br>
<br>
Let us say when have installed the statically pre-compiled <code>ffmpeg</code> binary to our slot. How do we use this over the existing <code>ffmpeg</code> already installed on the slot?<br>
<br>
If we have installed it to <code>~&#x2F;bin</code> then we would use this <code>PATH</code> in our <code>~&#x2F;.bashrc</code>:<br>
<br>
<pre><code>PATH=~&#x2F;bin:$PATH</code></pre><br>
If we instead did this, it would find the existing, installed <code>ffmpeg</code> before find our own installation since it will look in the existing <code>PATH</code> locations first and it will find the default installation of <code>ffmpeg</code>:<br>
<br>
<pre><code>PATH=$PATH:~&#x2F;bin</code></pre><br>
<strong>Important note:</strong> This also means that the order in which you add paths to your <code>~&#x2F;.bashrc</code> can change the search result.<br>
<br>
For more information see this page - <a href="http://tldp.org/LDP/abs/html/internalvariables.html">internal variables.</a><br>
<br>
<h2>wget usage in this FAQ</h2><br>
In this FAQ and others you will see&nbsp; this command format used. I will briefly explain what it is and why it is used.<br>
<br>
<pre><code>wget -qO ~&#x2F;node.js.tar.gz <a href="http://somesite/somefile.tar.gz">http:&#x2F;&#x2F;somesite&#x2F;somefile.tar.gz</a></code></pre><br>
<code>wget</code> - is the command that we wish to use to download the file<br>
<code>-qO ~&#x2F;somefile.tar.gz</code> - are the argurments we pass to <code>wget</code> so it performs some specific behaviour.<br>
<code><a href="http://somesite/somefile.tar.gz">http:&#x2F;&#x2F;somesite&#x2F;somefile.tar.gz</a></code> - is the example URL to the pre-compiled file we want.<br>
<br>
<code>q</code> tells <code>wget</code> to be quiet about the download and not to show us in the terminal.<br>
<br>
<code>O ~&#x2F;somefile.tar.gz</code> tells <code>wget</code> to name this file <code>somefile.tar.gz</code> in the root of you slot. This is because I use <code>~&#x2F;</code> prefixed to the name of the file I have specified. <code>~</code> known as a <code>tilde</code> is basically shorthand for the full path to our <code>HOME</code> directory when used in a <code>BASH</code> shell. This shell is the default shell you will be using with your Feral slot.<br>
<br>
<pre><code>~</code></pre><br>
Is the same as the path to your HOME folder, which will look something like this:<br>
<br>
<pre><code>&#x2F;media&#x2F;12345&#x2F;username&#x2F;home</code></pre><br>
So this means that:<br>
<br>
<pre><code>~&#x2F;somefile.tar.gz</code></pre><br>
Is the same as:<br>
<br>
<pre><code>&#x2F;media&#x2F;12345&#x2F;username&#x2F;home&#x2F;somefile.tar.gz</code></pre><br>
This method is used to ensure the files we want are placed in a specific location that we can use to continue the installation.<br>
<br>
<strong>Important notes:</strong><br>
<br>
With some URLs you may need to quotes the URL when certain characters are used. For example, using single quotes:<br>
<br>
<pre><code>&#x27;<a href="http://somesite/somefile.tar.gz">http:&#x2F;&#x2F;somesite&#x2F;somefile.tar.gz</a>&#x27;</code></pre><br>
Some URLs do not return the file we actually want and in this case you can try to use this argument with <code>wget</code>:<br>
<br>
<pre><code>--content-disposition</code></pre><br>
<h2>1: Pre-compiled binaries</h2><br>
In this example we will look at two particular applications that both have existing FAQs here.<br>
<br>
<a href="https://www.feralhosting.com/faq/view?question=199">node.js - How to install</a><br>
<br>
<h3>node</h3><br>
The first thing to do is to create the <code>~&#x2F;bin</code> directory and reload the relevant files for the PATH setting to take effect using this command:<br>
<br>
<pre><code>mkdir -p ~&#x2F;bin &amp;&amp; bash</code></pre><br>
Now download the required files:<br>
<br>
<pre><code>wget -qO ~&#x2F;node.js.tar.gz <a href="http://nodejs.org/dist/v0.10.31/node-v0.10.31-linux-x64.tar.gz">http:&#x2F;&#x2F;nodejs.org&#x2F;dist&#x2F;v0.10.31&#x2F;node-v0.10.31-linux-x64.tar.gz</a></code></pre><br>
Now we have downloaded the archive to our <code>HOME</code> folder we can unpack it. In this case the archive is a tar archive to we will use <code>tar</code> to extract it.<br>
<br>
<pre><code>tar xf ~&#x2F;node.js.tar.gz</code></pre><br>
<strong>Important note:</strong> Effectively, once you have extracted the the contents of the archive, the program is ready to use by directly calling it via a full path in you terminal using <code>~&#x2F;node-v0.10.31-linux-x64&#x2F;bin&#x2F;node</code> . For the purposes of this FAQ will continue to move the files to a desired location and add that location to our <code>PATH</code>, if required, for easy use and so you become more familiar with the overall process.<br>
<br>
Now the contents of the archive has just been extracted to the <code>HOME</code> folder of our slot. It will generally be safe to assume the new folder name is the same as the archive&#x27;s minus the extension, but to make sure, we can type this command in our terminal:<br>
<br>
<pre><code>ls</code></pre><br>
As we can see the folder name is <code>node-v0.10.31-linux-x64</code><br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral Wiki/Software/Generic Software Installation Guide/lsnode.png"><br>
<br>
The directory structure of the pre-compiled programs will commonly resemble the standard Unix directory structure, though this is not always true so it is good to check first.<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral Wiki/Software/Generic Software Installation Guide/nodedirectory.png"><br>
<br>
So what we need to do is copy the contents of the folder to our desired location, being our server root (using the shorthand <code>~&#x2F;</code>)&nbsp; in this example:<br>
<br>
<pre><code>cp -rf ~&#x2F;node-v0.10.31-linux-x64&#x2F;. ~&#x2F;</code></pre><br>
Now installed <code>node</code> and it is ready for use by simple called <code>node</code> in the terminal.<br>
<br>
<pre><code>node -v</code></pre><br>
And that is how you can install and use software that has be pre compiled to run on the linux platform. Now to tidy up a bit.<br>
<br>
Use the <code>cd</code> command. Using just <code>cd</code> on its own will return you to the <code>HOME</code> directory.<br>
<br>
<pre><code>cd</code></pre><br>
Now you can delete the files and folders we no longer require.<br>
<br>
<pre><code>rm -rf node{-v0.10.31-linux-x64,.js.tar.gz}</code></pre><br>
We are using <a href="https://www.gnu.org/software/bash/manual/html_node/Brace-Expansion.html">bash brace expansion</a> to remove the files.<br>
<br>
<strong>Important note:</strong> Not every pre-compiled binary will conform to this FAQ and might have a unique directory structure that doe not quite fit in with what was described in this section. See the <code>filebot</code> example to see this.<br>
<br>
<h2>2: Compiling from source</h2><br>
The first thing to do is to create the <code>~&#x2F;bin</code> directory and reload the relevant files for the PATH setting to take effect using this command:<br>
<br>
<pre><code>mkdir -p ~&#x2F;bin &amp;&amp; bash</code></pre><br>
When compiling from source you will need to follow this outline, we will use <code>curl</code> as the installation example. First, we download the software to a file named <code>curl.tar.gz</code> in our <code>HOME</code> directory using this command:<br>
<br>
<pre><code>wget -qO ~&#x2F;curl.tar.gz <a href="http://curl.haxx.se/download/curl-7.37.1.tar.gz">http:&#x2F;&#x2F;curl.haxx.se&#x2F;download&#x2F;curl-7.37.1.tar.gz</a></code></pre><br>
Now we need to extract the archive<br>
<br>
<pre><code>tar xf ~&#x2F;curl.tar.gz</code></pre><br>
Now the contents of the archive has just been extracted to the <code>HOME</code> folder of our slot. It will generally be safe to assume the new folder name is the same as the archive&#x27;s minus the extension, but to make sure, we can type this command in our shell:<br>
<br>
<pre><code>ls</code></pre><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral Wiki/Software/Generic Software Installation Guide/lscurl.png"><br>
<br>
As we can see the folder name is <code>curl-7.37.1</code>. So now we move into this folder using the <code>cd</code> command:<br>
<br>
<pre><code>cd ~&#x2F;curl-7.37.1</code></pre><br>
Now we will configure <code>curl</code> to use our desired installation location, which is <code>$HOME</code>:<br>
<br>
<pre><code>.&#x2F;configure --prefix=$HOME</code></pre><br>
Once the configuration is complete you can <code>make</code> the file:<br>
<br>
<strong>Important note:</strong> This stage can take a very long time. The time taken varies from one application to the other.<br>
<br>
<pre><code>make</code></pre><br>
If this step completed successfully you can now <code>make install</code> the program to finish the process.<br>
<br>
<pre><code>make install </code></pre><br>
Once this command has completed you can leave the folder using the <code>cd</code> command. Using just <code>cd</code> on its own will return you to the <code>HOME</code> directory.<br>
<br>
<pre><code>cd</code></pre><br>
You can now remove the downloaded files. As you can see in this command there is one folder <code>curl-7.37.1</code> and one archive <code>curl.tar.gz</code> being removed. You can chain more than one file or folder to be removed this way.<br>
<br>
<pre><code>rm -rf&nbsp; curl{-7.37.1,.tar.gz}</code></pre><br>
We are using <a href="https://www.gnu.org/software/bash/manual/html_node/Brace-Expansion.html">bash brace expansion</a> to remove the files.<br>
<br>
Do this command to call <code>curl</code> and check it&#x27;s version.<br>
<br>
<pre><code>curl -V</code></pre><br>
<strong>Important note:</strong> Not every source-code package will conform to this FAQ and might have unique requirements or hard coded settings that cannot be tweaked to suit the Feral slot with the scope of this FAQ. See the <code>git</code> FAQ for an example of this.<br>
<br>
<h2>3: Debian packages</h2><br>
To explain is simply, a <code>deb</code> is an archive that contains folders and files using a standard directory structure. We can extract the <code>deb</code> and attempt to use the files.<br>
<br>
First download the <code>deb</code> that you want to extract:<br>
<br>
<pre><code>wget -qO ~&#x2F;some.deb &#x27;<a href="https://somesite/some.deb">https:&#x2F;&#x2F;somesite&#x2F;some.deb</a>&#x27;</code></pre><br>
Now we will extract the <code>deb</code> using the <code>dpkg-deb</code> command. We will tell it where we want the files to be extracted to. It will create this location if it does not exist. In our example this location is <code>desired-location</code>. So we are going to extract <code>some.deb</code> to <code>desired-location</code>.<br>
<br>
<pre><code>dpkg-deb -x ~&#x2F;some.deb ~&#x2F;desired-location</code></pre><br>
Now you will find that the contents of the <code>desired-location</code> contain a standard directory structure. This is because file would generally be extracted to the core system folders and not a subdirectory when installed using a <code>deb</code>. <br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral Wiki/Software/Generic Software Installation Guide/debdirectory.png"><br>
<br>
So to make it more user like we can do this:<br>
<br>
<pre><code>cp -rf ~&#x2F;desired-location&#x2F;usr&#x2F;bin&#x2F;. ~&#x2F;desired-location</code></pre><br>
<pre><code>cd</code></pre><br>
<pre><code>rm -rf some.deb desired-location&#x2F;{etc,usr}</code></pre><br>
<h2>Examples:</h2><br>
<h2>1: Pre-compiled examples</h2><br>
<a href="https://www.feralhosting.com/faq/view?question=199">node.js - How to install</a><br>
<a href="https://www.feralhosting.com/faq/view?question=183">Java 1.7</a><br>
<a href="https://www.feralhosting.com/faq/view?question=245">p7zip - basic installation</a><br>
<a href="https://www.feralhosting.com/faq/view?question=224">BitTorrent Sync btsync - basic setup</a><br>
<a href="https://www.feralhosting.com/faq/view?question=227">Mumble client and murmur server</a><br>
<a href="https://www.feralhosting.com/faq/view?question=268">ffmpeg</a><br>
<a href="https://www.feralhosting.com/faq/view?question=157">Plowshare - a download tool for file sharing websites - with auto captcha solving</a><br>
<a href="https://www.feralhosting.com/faq/view?question=218">CouchPotato - An automatic NZB and torrent downloader for Films</a><br>
<a href="https://www.feralhosting.com/faq/view?question=205">Dropbox - How to install</a><br>
<br>
<h2>2: Source-code examples</h2><br>
<a href="https://www.feralhosting.com/faq/view?question=155">Icecast - streaming media server</a><br>
<a href="https://www.feralhosting.com/faq/view?question=266">ImageMagick - Basic Setup</a><br>
<a href="https://www.feralhosting.com/faq/view?question=206">Git - How to Install</a><br>
<a href="https://www.feralhosting.com/faq/view?question=265">Ruby - Basic Setup</a><br>
<a href="https://www.feralhosting.com/faq/view?question=204">Python - How to install</a><br>
<a href="https://www.feralhosting.com/faq/view?question=264">ZNC - Basic Setup</a><br>
<a href="https://www.feralhosting.com/faq/view?question=267">Curl - Basic Setup</a><br>
<a href="https://www.feralhosting.com/faq/view?question=269">Mosh - Basic Setup</a><br>
<a href="https://www.feralhosting.com/faq/view?question=255">Duplicity - Basic Setup</a><br>
<br>
<h2>3: Debian packages examples</h2><br>
<a href="https://www.feralhosting.com/faq/view?question=203">SpiderOak</a><br>
<a href="https://www.feralhosting.com/faq/view?question=256">FileBot CLI - Basic Setup</a><br>
<br>
