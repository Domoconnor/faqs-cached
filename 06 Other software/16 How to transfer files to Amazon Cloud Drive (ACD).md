<h1>How to transfer files to Amazon Cloud Drive (ACD)</h1>

        
To upload and download files to you Amazon Cloud Drive solution utilizing <a href="https://acd-cli.readthedocs.org/en/latest/">adc_cli</a> a lightweight command-line client for Amazon Cloud Drive (ACD), allowing you to access ACD storage from the command line.<br>
<a href="https://www.feralhosting.com/faq/view?question=12">Login to slot via ssh</a><br>
Below are detailed instruction and command that need to be run. Installation requires custom install of python with linked sql.<br>
Run this commands one by one and be patient it takes time<br>
<br>
<pre><code>wget <a href="http://www.sqlite.org/2016/sqlite-autoconf-3130000.tar.gz">http:&#x2F;&#x2F;www.sqlite.org&#x2F;2016&#x2F;sqlite-autoconf-3130000.tar.gz</a>
tar xf sqlite-autoconf-3130000.tar.gz &amp;&amp; rm sqlite-autoconf-3130000.tar.gz
cd sqlite-autoconf-3130000&#x2F;
LDFLAGS=&quot;-L${HOME}&#x2F;opt&#x2F;lib&quot; CFLAGS=&quot;-L${HOME}&#x2F;opt&#x2F;include&quot; .&#x2F;configure --prefix=$HOME&#x2F;opt
make &amp;&amp; make install &amp;&amp; cd
mkdir -p ~&#x2F;python&#x2F;python3
wget -qO ~&#x2F;python.tar.xz&nbsp; <a href="https://www.python.org/ftp/python/3.5.0/Python-3.5.0.tar.xz">https:&#x2F;&#x2F;www.python.org&#x2F;ftp&#x2F;python&#x2F;3.5.0&#x2F;Python-3.5.0.tar.xz</a>
tar xf ~&#x2F;python.tar.xz &amp;&amp; cd ~&#x2F;Python-3.5.0
LD_RUN_PATH=$HOME&#x2F;opt&#x2F;lib .&#x2F;configure --prefix=$HOME&#x2F;python&#x2F;python3 LDFLAGS=&quot;-L$HOME&#x2F;opt&#x2F;lib&quot; CPPFLAGS=&quot;-I$HOME&#x2F;opt&#x2F;include&quot;
LD_RUN_PATH=$HOME&#x2F;opt&#x2F;lib make
make install
cd &amp;&amp; rm -rf ~&#x2F;python{-3.5.0,.tar.xz}
~&#x2F;python&#x2F;python3&#x2F;bin&#x2F;pip3 install --user --upgrade git+<a href="https://github.com/yadayada/acd_cli.git">https:&#x2F;&#x2F;github.com&#x2F;yadayada&#x2F;acd_cli.git</a></code></pre><br>
<br>
One time authentication setup and database sync.<br>
<br>
Before using acd_cli, you need to go through one-time authentication, where you authorize acd_cli to access your Amazon Cloud Drive account via OAuth.<br>
<br>
<pre><code>.local&#x2F;bin&#x2F;acd_cli init</code></pre><br>
<br>
You have two options: <br>
Login to <a href="https://tensile-runway-92512.appspot.com">https:&#x2F;&#x2F;tensile-runway-92512.appspot.com</a> with Amazon credentials, follow prompts, at the end you will be presented with download &quot;oauth_data&quot; file. Save on your local hard drive and the ftp upload to your_user_directory .cache&#x2F;acd_cli<br>
Second option:<br>
Follow prompts, fill out your amazon information, checkmark &quot;always&quot;. Navigate using arrow key. After all information filled go up to login and press enter or right arrow you will be presented with your token, csave the plaintext response data into a file called &quot;oauth_data&quot; in the directory &quot;.cache&#x2F;acd_cli&#x2F;&quot;<br>
Now end amazon session by pressing &quot;q&quot;.<br>
<br>
Before running any command with acd_cli, you need to sync its local cache with your Amazon Cloud Drive account. Run<br>
<pre><code>.local&#x2F;bin&#x2F;acd_cli sync</code></pre><br>
<br>
This completes setup.<br>
<br>
Using it. To see your Amazon Cloud Drive directory and usage:<br>
<pre><code>.local&#x2F;bin&#x2F;acd_cli usage</code></pre><br>
Result will be like that<br>
<em>Documents:&nbsp; &nbsp;  966,&nbsp; &nbsp; 1.2 GiB<br>
Other:&nbsp; &nbsp; &nbsp;  10030,&nbsp; &nbsp; 6.8 TiB<br>
Photos:&nbsp; &nbsp; &nbsp;  5651,&nbsp;  30.4 GiB<br>
Videos:&nbsp; &nbsp; &nbsp;  3502,&nbsp; &nbsp; 1.2 TiB<br>
Total:&nbsp; &nbsp; &nbsp;  20149,&nbsp; &nbsp; 8.1 TiB</em><br>
<br>
To list files in a folder:<br>
<pre><code>.local&#x2F;bin&#x2F;acd_cli ls &#x2F;Videos</code></pre><br>
<br>
To upload folder to ACD<br>
<pre><code>.local&#x2F;bin&#x2F;acd_cli upload -x 2 -r 4 --deduplicate ~&#x2F;folder_to_upload&#x2F; &#x2F;amazon_folder_destination&#x2F;</code></pre><br>
-x MAX_CONNECTIONS, -r MAX_RETRIES<br>
--deduplicate exclude duplicate files from upload, useful in case of errors. Only files with different checksum will be replaced.<br>
<br>
For downloading files to feralhosting use &quot;download&quot; command instead of &quot;upload&quot; and reverse directories for file location.<br>
<br>
<h2>Troubleshooting</h2><br>
If you see this error when trying to upload or download:<br>
<br>
<pre><code>UnicodeEncodeError: &#x27;utf-8&#x27; codec can&#x27;t encode character &#x27;\udcc3&#x27; in position 7: surrogates not allowed
16-05-03 21:58:36.154 [ERROR] [acd_cli] - Please set your locale or use the &quot;--utf&quot; flag.</code></pre> <br>
Please try exporting the locale and then running the command as follows:<br>
<br>
<pre><code>export LC_ALL=&quot;en_US.UTF-8&quot; &amp;&amp; ~.local&#x2F;bin&#x2F;acd_cli upload</code></pre> 
<br>