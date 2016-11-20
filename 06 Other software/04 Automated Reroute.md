<h1>Automated Reroute</h1>

        
If you find yourself regularly visiting the <a href="https://network.feral.io/reroute">reroute page</a> to make route changes, or you just want an easy way to accurately test speed from Feral servers to your home network, run the auto-reroute script on your computer at home. The script downloads test files from each of Feral&#x27;s routes, determines the fastest route, then sets that route for you. Results are logged to ~&#x2F;.auto-reroute&#x2F;auto-reroute.log<br>
<br>
<h2>Linux &amp; OSX</h2><br>
<br>
Open up a terminal and paste in, and run the following command:<br>
<br>
<pre><code>curl -s -L -o ~&#x2F;auto-reroute.sh <a href="http://git.io/hsFb">http:&#x2F;&#x2F;git.io&#x2F;hsFb</a> &amp;&amp; bash ~&#x2F;auto-reroute.sh</code></pre><br>
<br>
<h2>Windows (Using Cygwin)</h2><br>
<br>
Need help installing Cygwin? Check out <a href="https://www.feralhosting.com/faq/view?question=235">this FAQ page.</a><br>
<br>
If you don&#x27;t already have them installed, re-run the cygwin installer, and install <code>curl</code> (under &quot;Net&quot;) and <code>bc</code> (under &quot;Math&quot;).<br>
Once installed, open up a Cygwin terminal, paste in, and run the following command:<br>
<br>
<pre><code>curl -s -L -o ~&#x2F;auto-reroute.sh <a href="http://git.io/hsFb">http:&#x2F;&#x2F;git.io&#x2F;hsFb</a> &amp;&amp; bash ~&#x2F;auto-reroute.sh</code></pre><br>
<br>
<br>
<h2>Sample Run</h2><br>
The following is a real time example of what the script should look like when run. <br>
<br>
<img src="http://i.imgur.com/6AkGI7d.gif"><br>
<br>
