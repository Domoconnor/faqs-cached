<h1>How do I connect to MySQL in PHP</h1>

        
Connecting to MySQL using PHP can be a tad tricky as MySQL is configured on Feral to only allow connections via socket.<br>
<br>
To make it work use the following line to connect:<br>
<br>
<pre><code>$db = MySQLi_connect(&quot;localhost&quot;,&quot;root&quot;,&#x27;password&#x27;, &#x27;&#x27;, 0, &#x27;&#x2F;path&#x2F;to&#x2F;your&#x2F;mysql&#x2F;socket&#x27;);</code></pre><br>
or<br>
<br>
<pre><code>mysql_connect(&quot;:SOCKETNAME&quot;, &quot;root&quot;, &quot;PASSWORD&quot;) or die(mysql_error()); mysql_select_db(&quot;DATABASE_NAME&quot;) or die(mysql_error());</code></pre><br>
It&#x27;s one full line and the variables are in uppercase:<br>
<br>
<strong>SOCKETNAME</strong>: found in your <strong>my.conf</strong> file <br>
<br>
<pre><code>~&#x2F;private&#x2F;mysql&#x2F;my.conf</code></pre><br>
<strong>PASSWORD</strong>: your MySQL password<br>
<br>
<strong>DATABASE_NAME</strong>: the database you created in mysql<br>
<br>
<br>
With PDO, it&#x27;s special !<br>
<br>
In php many PDo connections will use a similar layout:<br>
<br>
<pre><code>&lt;?php

$dsn = &#x27;mysql:dbname=testdb;host=localhost&#x27;;
$user = &#x27;dbuser&#x27;;
$password = &#x27;dbpass&#x27;;

try {
&nbsp; &nbsp; $dbh = new PDO($dsn, $user, $password);
} catch (PDOException $e) {
&nbsp; &nbsp; echo &#x27;Connexion Ã©chouÃ©e : &#x27; . $e-&gt;getMessage();
}

?&gt;</code></pre><br>
On feralhosting PDO can use a socket, but you cannot have <em>host</em> and <em>unix_socket=</em> simultaneously for a connection.<br>
The default Feral set up is for local connections only. So you would need to replace <em>host</em> with <em>unix_socket=</em><br>
<br>
In this example the socket has been hard coded. If the php app provides a variable for the hostame, for use with a web based installer for example, you could use that.<br>
<br>
example :<br>
<br>
<pre><code>&lt;?php

$dsn = &#x27;mysql:dbname=testdb;unix_socket=&#x2F;media&#x2F;path&#x2F;to&#x2F;mysql&#x2F;socket&#x27;;
$user = &#x27;dbuser&#x27;;
$password = &#x27;dbpass&#x27;;

try {
&nbsp; &nbsp; $dbh = new PDO($dsn, $user, $password);
} catch (PDOException $e) {
&nbsp; &nbsp; echo &#x27;Connexion Ã©chouÃ©e : &#x27; . $e-&gt;getMessage();
}

?&gt;</code></pre><br>
<br>
