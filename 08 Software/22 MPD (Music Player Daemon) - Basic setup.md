<h1>MPD (Music Player Daemon) - Basic setup</h1>

        
        <h1>MPD Installation</h1><br>
<br>
<a href="http://www.musicpd.org/">MPD (Music Player Daemon)</a> is an extremelly liteweight music server with built-in music streaming and transcoding capabilities. There are no requirements for Java and no licenses you have to buy.<br>
<br>
1. `mkdir -p ~&#x2F;.mpd&#x2F;playlists`<br>
2. `touch ~&#x2F;.mpd&#x2F;{database,log,state}`<br>
3. Copy the configuration to `~&#x2F;.mpd&#x2F;mpd.conf`<br>
4. Start with `mpd ~&#x2F;.mpd&#x2F;mpd.conf`<br>
<pre><code>
music_directory&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &quot;~&#x2F;private&#x2F;rtorrent&#x2F;data&quot;
db_file&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &quot;~&#x2F;.mpd&#x2F;database&quot;
log_file&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  &quot;~&#x2F;.mpd&#x2F;log&quot;
pid_file&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  &quot;~&#x2F;.mpd&#x2F;pid&quot;
state_file&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  &quot;~&#x2F;.mpd&#x2F;state&quot;
playlist_directory&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  &quot;~&#x2F;.mpd&#x2F;playlists&quot;
#password&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &quot;password@read,add,control,admin&quot;
bind_to_address&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &quot;aphrodite.feralhosting.com&quot;
port&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  &quot;44000&quot;
gapless_mp3_playback&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  &quot;yes&quot;
auto_update&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &quot;yes&quot;

audio_output {
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  type&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  &quot;httpd&quot;
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  name&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  &quot;LAME&quot;
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  encoder&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &quot;lame&quot;
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  port&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  &quot;8001&quot;
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  bitrate&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &quot;320&quot;
}

replaygain&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  &quot;album&quot;
replaygain_preamp&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &quot;0&quot;
</code></pre><br>
<br>
5. Open the stream in VLC via &quot;Open Netowrk&quot; and input `<a href="http://aphrodite.feralhosting.com:8001">http:&#x2F;&#x2F;aphrodite.feralhosting.com:8001</a>`<br>
6. Fire up <a href="http://ncmpcpp.rybczak.net">ncmpcpp</a> or your favorite client and start playing some tunes.<br>
<br>
<br>
Shamelessly copied from <a href="https://gist.github.com/maletor/8153179">this gist</a>
<br>