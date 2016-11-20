<h1>What is multisegmented downloading - how does it help</h1>

        
One of the biggest complaints from seedbox users is not about the BitTorrent upload&#x2F;download speeds within the server itself; rather, the FTP speeds in which the files are transferred back to the home PC. <br>
<br>
<h3>Multiple Concurrent Transfers</h3> <br>
This allows for multiple transfers to occur during the same session (ie - you can download more than one file at the same time) but this doesnâ€™t necessarily imply that segmentation occurs. For example, most FTP clients support multiple simultaneous concurrent transfers (such as FileZilla). However, Filezilla doesnâ€™t support segmented downloading. Therefore if you can only get 100KB&#x2F;s per connection, and youâ€™re only retrieving one file, your speed will be limited to 100KB&#x2F;s.<br>
<br>
<h3>Multi-threading vs Segmented</h3><br>
A common misconception is that multithreading = segmented downloading. This is not the case. GoFTP is a client that claims to support multi-threading, but in truth doesnâ€™t offer segmented. Segmentation allows an FTP client to split a single large file into multiple parts and use multiple transfers to download those parts simultaneously (ie - separate segmented parallel FTP connections). These parts are then recombined into a single file upon completion. <br>
<br>
<h3>How Multisegment helps</h3><br>
To explain why FTP does not always max out your home connection we have to take a look at the way the transport layer FTP uses works. Like mentioned above FTP uses TCP as it&#x27;s transport layer. TCP is a great protocol, it has built in error detection, it numbers the packages so it can rebuild the file regardless of the way the packets arrive and it has native support for flow control. Flow control is responsible for deciding how fast the server sends the data to the client and is main factor that decides your download speed. When talking to a server the client requesting the data specifies a &quot;receive window&quot; it&#x27;s a value that decides how much data it is willing to receive before reporting back to the server that it received all the packages. If for instance it announces to the server it&#x27;s willing to buffer 256kb of data the server will send 256kb and then wait for the client to report that it received the 256kb in good order. It&#x27;s this mechanism that&#x27;s responsible for the loss of speed. If you are very close to the server (let&#x27;s say 12 ms) it&#x27;s not that much of a problem. The server will send 256kb and then pause for 12ms. This won&#x27;t really effect the speed. However if you live in the US and you are connecting to a server in Germany this trip might take 130ms. This means for every 256kb the server sends it waits 130ms to send the next 256kb. That&#x27;s why you can max out your download to one server but get a sucky 150kb&#x2F;s on a different one.<br>
<br>
The further away you are from the server you are trying to download from the slower your download will be. <br>
<br>
For more information on how to configure your clients, please see <a href="https://www.feralhosting.com/faq/view?question=28">What to do if FTP speeds are slow</a><br>
<br>
