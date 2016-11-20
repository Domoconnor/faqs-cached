<h1>CMAKE - Basic Setup</h1>

        
CMake is an open-source, cross-platform family of tools designed to build, test and package software. CMake is used to control the software compilation process using simple platform and compiler independent configuration files, and generate native makefiles and workspaces that can be used in the compiler environment of your choice.<br>
<br>
In SSH do the commands described in this FAQ. If you do not know how to SSH into your slot use this FAQ: <a href="https://www.feralhosting.com/faq/view?question=12">SSH basics - Putty</a><br>
<br>
Your FTP &#x2F; SFTP &#x2F; SSH login information can be found on the Slot Details page for the relevant slot. Use this link in your Account Manager to access the relevant slot:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/slot_detail_link.png"><br>
<br>
You login information for the relevant slot will be shown here:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/slot_detail_ssh.png"><br>
<br>
<h2>CMAKE installation</h2><br>
Use these first two commands to create to do some pre requisite tasks:<br>
<br>
<pre><code>mkdir -p ~&#x2F;bin &amp;&amp; bash</code></pre><br>
 <strong>Important note</strong> You can check here for the current version - <a href="http://www.cmake.org/download/">http:&#x2F;&#x2F;www.cmake.org&#x2F;download&#x2F;</a><br>
<br>
<h3>Binary Distribution Installation (Fast).</h3><br>
<pre><code>wget -qO ~&#x2F;cmake.tar.gz <a href="http://www.cmake.org/files/v3.2/cmake-3.2.2-Linux-x86_64.tar.gz">http:&#x2F;&#x2F;www.cmake.org&#x2F;files&#x2F;v3.2&#x2F;cmake-3.2.2-Linux-x86_64.tar.gz</a>
tar xf ~&#x2F;cmake.tar.gz --strip-components=1 -C ~&#x2F;</code></pre><br>
Then test it works:<br>
<br>
<pre><code>cmake --version</code></pre><br>
<h3>Compile from Source Code</h3><br>
Install the program from source using these commands:<br>
<br>
<pre><code>wget -qO ~&#x2F;cmake.tar.gz <a href="http://www.cmake.org/files/v3.2/cmake-3.2.2.tar.gz">http:&#x2F;&#x2F;www.cmake.org&#x2F;files&#x2F;v3.2&#x2F;cmake-3.2.2.tar.gz</a>
tar xf ~&#x2F;cmake.tar.gz &amp;&amp; cd ~&#x2F;cmake-3.2.2
.&#x2F;configure --prefix=$HOME
make &amp;&amp; make install
cd &amp;&amp; rm -rf cmake{-3.2.2,.tar.gz}</code></pre><br>
Then test it works:<br>
<br>
<pre><code>cmake --version</code></pre><br>
<h2>Usage:</h2><br>
You can use this prefix to specify the directory you wish to install the program to.<br>
<br>
<pre><code>cmake -DPREFIX=$HOME</code></pre><br>
<h2>Issues with CURL:</h2><br>
When installing <code>weechat</code> for example, the curl location is not default so we must specify it. To do this though we must make sure it is not going to skip an important setting.<br>
<br>
Inside the directory of the application you wish to install there should be a file called <code>CMakeLists.txt</code>. Open this file and check for the line:<br>
<br>
<pre><code>SET(CMAKE_SKIP_RPATH ON</code></pre><br>
If this line exists then remove it.<br>
<br>
This example is how <code>weechat</code> is installed on the slot when the script is used.<br>
<br>
<pre><code>cmake -DCMAKE_INSTALL_RPATH=&#x2F;opt&#x2F;curl&#x2F;current&#x2F;lib -DPREFIX=$HOME -DCURL_LIBRARY=&#x2F;opt&#x2F;curl&#x2F;current&#x2F;lib&#x2F;libcurl.so -DCURL_INCLUDE_DIR=&#x2F;opt&#x2F;curl&#x2F;current&#x2F;include</code></pre><br>
<br>
