<h1>Batch Torrent Creation Directly on Your Feral Slot</h1>

        
<br>
The following set of commands will allow you to batch create .torrent files for all directories and&#x2F;or single files in a directory of your choice.<br>
<br>
<strong>Step 1:</strong><br>
<br>
<a href="https://www.feralhosting.com/faq/view?question=12">SSH to your Feral server</a>. Navigate to the directories containing the data you wish to batch create .torrents for:<br>
<br>
<pre><code>cd media&#x2F;DiskID&#x2F;home&#x2F;username&#x2F;private&#x2F;TEST_DIR</code></pre><br>
<strong>Step 2:</strong><br>
<br>
Copy and paste the following set of commands to batch create your .torrents. Modify the announce URL and other mktorrent parameters to suit your needs.<br>
<br>
This will process directories only:<br>
<br>
<pre><code>ls -F | grep &#x2F; | while read line; do mktorrent -a &quot;<a href="http://announce/url">http:&#x2F;&#x2F;announce&#x2F;url</a>&quot; -p &quot;$line&quot;; done</code></pre><br>
This will process both dirs and single files:<br>
<br>
<pre><code>ls -F | grep . | while read line; do mktorrent -a &quot;<a href="http://announce/url">http:&#x2F;&#x2F;announce&#x2F;url</a>&quot; -p &quot;$line&quot;; done</code></pre><br>
The command assumes the default piece size for your .torrents, which will work fine for music albums and other relatively small files. Use the following set of commands for batch creating .torrents for bigger files such as packs or video:<br>
<br>
<pre><code>ls -F | grep &#x2F; | while read line; do mktorrent -a &quot;<a href="http://announce/url">http:&#x2F;&#x2F;announce&#x2F;url</a>&quot; -p -l 21 &quot;$line&quot;; done</code></pre><br>
<br>
