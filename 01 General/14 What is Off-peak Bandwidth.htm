<h1>What is Off-peak Bandwidth?</h1>

        
In its simplest terms, off-peak bandwidth is when an external network connection is not near its maximum rate for the previous month.<br>
<br>
So if we bought a 25 Gbit&#x2F;s off another ISP, then that connection would be considered off-peak while it&#x27;s doing less than 20-25 Gbit&#x2F;s. Anything above 20-25 Gbit&#x2F;s would be on-peak.<br>
<br>
<h3>Can you provide a concrete example?</h3><br>
Feral runs its own ISP which means we buy traffic from more than one ISP. One of those ISPs is called GTT where we have 40 Gbit&#x2F;s of capacity to and from. We&#x27;re constantly monitoring the rate of this traffic and over the course of a month we can see that it might use 20 Gbit&#x2F;s at the busiest times. When this connection gets close to the 20 Gbit&#x2F;s our system considers the connection to be on-peak traffic and starts switching off any bandwidth that&#x27;s considered off-peak.<br>
<br>
<h2>When are connections considered off-peak?</h2><br>
There is no specific cross-over point when connections are considered off-peak as it varies depending on what else is happening on the network and the connection itself. For example, we may purchase extra bandwidth with one provider to encourage growth meaning that it&#x27;s considered off-peak for much longer than normal.<br>
<br>
You should also bear in mind that the off-peak bandwidth is assessed per connection. So while GTT might be considered on-peak, connections via AMS-IX will probably still be off-peak.<br>
<br>
Our peak hour is typically Saturday evening in Europe for 2-3 hours. This small timeframe is when you&#x27;re likely to see connections move to on-peak only.<br>
<br>
<h3>Which connections are likely to be off-peak?</h3><br>
The answer to this depends heavily on the connection. We are eager to promote traffic to ISPs with open peering policies as it lowers the costs for everyone involved. This means that connections flowing over exchanges such as AMS-IX, NL-IX, LINX, and so forth are all likely to be considered permanently off-peak.<br>
<br>
Access to exchanges through third-parties such as via IX Reach and Open Peering are also likely to remain off-peak for much longer.<br>
<br>
The majority of IPv6 traffic currently flows via AMS-IX which means that it is likely to always be considered off-peak.<br>
<br>
<h3>What is the current status of traffic?</h3><br>
Our status page reports network statistics in real-time and gives an indication of whether a connection is off-peak: <a href="http://status.feral.io/">http:&#x2F;&#x2F;status.feral.io&#x2F;</a><br>
<br>
<h2>What will happen when a connection moves from off to on-peak?</h2><br>
If your slot has off-peak bandwidth then traffic flowing over that connection will instantly stop. You will see immediate failures when trying to make the connection with something along the lines of &quot;no route to host&quot; or &quot;connection failed&quot;.<br>
<br>
When the connection moves back to off-peak, you will be able to make new connections to the IP.<br>
<br>
<h3>What if my IP was using an on-peak connection?</h3><br>
If this is the case your server will not accept connections from your IP. However, we allow you to change the connection your IP uses so you can bypass this restriction easily.<br>
<br>
Please use the reroute tool to bypass this: <a href="https://network.feral.io/reroute">https:&#x2F;&#x2F;network.feral.io&#x2F;reroute</a><br>
<br>
<h2>Technically, how is it enforced?</h2><br>
When a connection moves to on-peak, off-peak only servers will begin dropping packets. This typically happens within the minute.<br>
<br>
If you login to your server via SSH you can check the connections that are definitely on-peak with the following command: ip rule<br>
<br>
When no connections are on-peak it will produce a result such as:<br>
<br>
<pre><code>[lion ~] ip rule
0:	from all lookup local 
10000:	from all lookup protected 
32766:	from all lookup main 
32767:	from all lookup default</code></pre><br>
<br>
When a connection moves to on-peak, you will see an extra entry:<br>
<br>
<pre><code>[lion ~] ip rule
0:	from all lookup local 
10000:	from all lookup protected 
<strong>10107:&nbsp; from all lookup gtt</strong>
32766:	from all lookup main 
32767:	from all lookup default</code></pre><br>
<br>
The highlighted entry shows that GTT has moved to on-peak traffic and is dropping connections.<br>
<br>
<h2>Summary</h2><br>
In conclusion, you should see all connections as off-peak 90-95% of the time. When it&#x27;s not, you can bypass them via <a href="https://network.feral.io/reroute&#xD;&#xA;">using the reroute page</a>.
<br>