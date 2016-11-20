<h1>Perl - Installing modules</h1>

        
In SSH do the commands described in this FAQ. If you do not know how to SSH into your slot use this FAQ: <a href="https://www.feralhosting.com/faq/view?question=12">SSH basics - Putty</a><br>
<br>
Your FTP &#x2F; SFTP &#x2F; SSH login information can be found on the Slot Details page for the relevant slot. Use this link in your Account Manager to access the relevant slot:<br>
<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/slot_detail_link.png"><br>
<br>
You login information for the relevant slot will be shown here:<br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/0%20Generic/slot_detail_ssh.png"><br>
<strong>Perl 5 is installed on all servers by default</strong><br>
Type to show the current version:<br>
<pre><code>perl -v</code></pre><br>
<h2>Installing modules:</h2><br>
The majority of perl modules are user installable, there is some setup required before hand.<br>
<strong>1. cpan config</strong><br>
Make the config directory<br>
<pre><code>mkdir -p ~&#x2F;.cpan&#x2F;CPAN</code></pre><br>
Add your config. You can either copy and paste the (really long) one-liner below into SSH or create the file <code>~&#x2F;.cpan&#x2F;CPAN&#x2F;MyConfig.pm</code> with the contents also listed below.<br>
<br>
One-liner:<br>
<pre><code>echo -e &quot;\$CPAN::Config = {\n&nbsp; &#x27;applypatch&#x27; =&gt; q[],\n&nbsp; &#x27;auto_commit&#x27; =&gt; q[0],\n&nbsp; &#x27;build_cache&#x27; =&gt; q[100],\n&nbsp; &#x27;build_dir&#x27; =&gt; q[$HOME&#x2F;.cpan&#x2F;build],\n&nbsp; &#x27;build_dir_reuse&#x27; =&gt; q[0],\n&nbsp; &#x27;build_requires_install_policy&#x27; =&gt; q[yes],\n&nbsp; &#x27;bzip2&#x27; =&gt; q[&#x2F;bin&#x2F;bzip2],\n&nbsp; &#x27;cache_metadata&#x27; =&gt; q[1],\n&nbsp; &#x27;check_sigs&#x27; =&gt; q[0],\n&nbsp; &#x27;colorize_output&#x27; =&gt; q[0],\n&nbsp; &#x27;commandnumber_in_prompt&#x27; =&gt; q[1],\n&nbsp; &#x27;connect_to_internet_ok&#x27; =&gt; q[1],\n&nbsp; &#x27;cpan_home&#x27; =&gt; q[$HOME&#x2F;.cpan],\n&nbsp; &#x27;ftp_passive&#x27; =&gt; q[1],\n&nbsp; &#x27;ftp_proxy&#x27; =&gt; q[],\n&nbsp; &#x27;getcwd&#x27; =&gt; q[cwd],\n&nbsp; &#x27;gpg&#x27; =&gt; q[&#x2F;usr&#x2F;bin&#x2F;gpg],\n&nbsp; &#x27;gzip&#x27; =&gt; q[&#x2F;bin&#x2F;gzip],\n&nbsp; &#x27;halt_on_failure&#x27; =&gt; q[0],\n&nbsp; &#x27;histfile&#x27; =&gt; q[$HOME&#x2F;.cpan&#x2F;histfile],\n&nbsp; &#x27;histsize&#x27; =&gt; q[100],\n&nbsp; &#x27;http_proxy&#x27; =&gt; q[],\n&nbsp; &#x27;inactivity_timeout&#x27; =&gt; q[0],\n&nbsp; &#x27;index_expire&#x27; =&gt; q[1],\n&nbsp; &#x27;inhibit_startup_message&#x27; =&gt; q[0],\n&nbsp; &#x27;keep_source_where&#x27; =&gt; q[$HOME&#x2F;.cpan&#x2F;sources],\n&nbsp; &#x27;load_module_verbosity&#x27; =&gt; q[none],\n&nbsp; &#x27;make&#x27; =&gt; q[&#x2F;usr&#x2F;bin&#x2F;make],\n&nbsp; &#x27;make_arg&#x27; =&gt; q[],\n&nbsp; &#x27;make_install_arg&#x27; =&gt; q[],\n&nbsp; &#x27;make_install_make_command&#x27; =&gt; q[&#x2F;usr&#x2F;bin&#x2F;make],\n&nbsp; &#x27;makepl_arg&#x27; =&gt; q[INSTALLDIRS=site],\n&nbsp; &#x27;mbuild_arg&#x27; =&gt; q[],\n&nbsp; &#x27;mbuild_install_arg&#x27; =&gt; q[],\n&nbsp; &#x27;mbuild_install_build_command&#x27; =&gt; q[.&#x2F;Build],\n&nbsp; &#x27;mbuildpl_arg&#x27; =&gt; q[--installdirs site],\n&nbsp; &#x27;no_proxy&#x27; =&gt; q[],\n&nbsp; &#x27;pager&#x27; =&gt; q[&#x2F;usr&#x2F;bin&#x2F;less],\n&nbsp; &#x27;patch&#x27; =&gt; q[&#x2F;usr&#x2F;bin&#x2F;patch],\n&nbsp; &#x27;perl5lib_verbosity&#x27; =&gt; q[none],\n&nbsp; &#x27;prefer_external_tar&#x27; =&gt; q[1],\n&nbsp; &#x27;prefer_installer&#x27; =&gt; q[MB],\n&nbsp; &#x27;prefs_dir&#x27; =&gt; q[$HOME&#x2F;.cpan&#x2F;prefs],\n&nbsp; &#x27;prerequisites_policy&#x27; =&gt; q[follow],\n&nbsp; &#x27;scan_cache&#x27; =&gt; q[atstart],\n&nbsp; &#x27;shell&#x27; =&gt; q[&#x2F;bin&#x2F;bash],\n&nbsp; &#x27;show_unparsable_versions&#x27; =&gt; q[0],\n&nbsp; &#x27;show_upload_date&#x27; =&gt; q[0],\n&nbsp; &#x27;show_zero_versions&#x27; =&gt; q[0],\n&nbsp; &#x27;tar&#x27; =&gt; q[&#x2F;bin&#x2F;tar],\n&nbsp; &#x27;tar_verbosity&#x27; =&gt; q[none],\n&nbsp; &#x27;term_is_latin&#x27; =&gt; q[1],\n&nbsp; &#x27;term_ornaments&#x27; =&gt; q[1],\n&nbsp; &#x27;test_report&#x27; =&gt; q[0],\n&nbsp; &#x27;trust_test_report_history&#x27; =&gt; q[0],\n&nbsp; &#x27;unzip&#x27; =&gt; q[&#x2F;usr&#x2F;bin&#x2F;unzip],\n&nbsp; &#x27;urllist&#x27; =&gt; [q[<a href="http://cpan.mirror.anlx.net/&#x5D;">http:&#x2F;&#x2F;cpan.mirror.anlx.net&#x2F;]</a>, q[<a href="http://ftp.ticklers.org/pub/CPAN/&#x5D;">http:&#x2F;&#x2F;ftp.ticklers.org&#x2F;pub&#x2F;CPAN&#x2F;]</a>, q[<a href="http://mir2.ovh.net/ftp.cpan.org/&#x5D;">http:&#x2F;&#x2F;mir2.ovh.net&#x2F;ftp.cpan.org&#x2F;]</a>],\n&nbsp; &#x27;use_sqlite&#x27; =&gt; q[0],\n&nbsp; &#x27;version_timeout&#x27; =&gt; q[15],\n&nbsp; &#x27;wget&#x27; =&gt; q[&#x2F;usr&#x2F;bin&#x2F;wget],\n&nbsp; &#x27;yaml_load_code&#x27; =&gt; q[0],\n&nbsp; &#x27;yaml_module&#x27; =&gt; q[YAML],\n};\n1;\n__END__&quot; &gt; ~&#x2F;.cpan&#x2F;CPAN&#x2F;MyConfig.pm</code></pre><br>
Config to copy and paste. You will need to edit everywhere instance of USERHOME with the full path to your home directory. You can find this by typing <code>$HOME</code> in SSH<br>
<pre><code>$CPAN::Config = {
&nbsp; &#x27;applypatch&#x27; =&gt; q[],
&nbsp; &#x27;auto_commit&#x27; =&gt; q[0],
&nbsp; &#x27;build_cache&#x27; =&gt; q[100],
&nbsp; &#x27;build_dir&#x27; =&gt; q[USERHOME&#x2F;.cpan&#x2F;build],
&nbsp; &#x27;build_dir_reuse&#x27; =&gt; q[0],
&nbsp; &#x27;build_requires_install_policy&#x27; =&gt; q[yes],
&nbsp; &#x27;bzip2&#x27; =&gt; q[&#x2F;bin&#x2F;bzip2],
&nbsp; &#x27;cache_metadata&#x27; =&gt; q[1],
&nbsp; &#x27;check_sigs&#x27; =&gt; q[0],
&nbsp; &#x27;colorize_output&#x27; =&gt; q[0],
&nbsp; &#x27;commandnumber_in_prompt&#x27; =&gt; q[1],
&nbsp; &#x27;connect_to_internet_ok&#x27; =&gt; q[1],
&nbsp; &#x27;cpan_home&#x27; =&gt; q[USERHOME&#x2F;.cpan],
&nbsp; &#x27;ftp_passive&#x27; =&gt; q[1],
&nbsp; &#x27;ftp_proxy&#x27; =&gt; q[],
&nbsp; &#x27;getcwd&#x27; =&gt; q[cwd],
&nbsp; &#x27;gpg&#x27; =&gt; q[&#x2F;usr&#x2F;bin&#x2F;gpg],
&nbsp; &#x27;gzip&#x27; =&gt; q[&#x2F;bin&#x2F;gzip],
&nbsp; &#x27;halt_on_failure&#x27; =&gt; q[0],
&nbsp; &#x27;histfile&#x27; =&gt; q[USERHOME&#x2F;.cpan&#x2F;histfile],
&nbsp; &#x27;histsize&#x27; =&gt; q[100],
&nbsp; &#x27;http_proxy&#x27; =&gt; q[],
&nbsp; &#x27;inactivity_timeout&#x27; =&gt; q[0],
&nbsp; &#x27;index_expire&#x27; =&gt; q[1],
&nbsp; &#x27;inhibit_startup_message&#x27; =&gt; q[0],
&nbsp; &#x27;keep_source_where&#x27; =&gt; q[USERHOME&#x2F;.cpan&#x2F;sources],
&nbsp; &#x27;load_module_verbosity&#x27; =&gt; q[none],
&nbsp; &#x27;make&#x27; =&gt; q[&#x2F;usr&#x2F;bin&#x2F;make],
&nbsp; &#x27;make_arg&#x27; =&gt; q[],
&nbsp; &#x27;make_install_arg&#x27; =&gt; q[],
&nbsp; &#x27;make_install_make_command&#x27; =&gt; q[&#x2F;usr&#x2F;bin&#x2F;make],
&nbsp; &#x27;makepl_arg&#x27; =&gt; q[INSTALLDIRS=site],
&nbsp; &#x27;mbuild_arg&#x27; =&gt; q[],
&nbsp; &#x27;mbuild_install_arg&#x27; =&gt; q[],
&nbsp; &#x27;mbuild_install_build_command&#x27; =&gt; q[.&#x2F;Build],
&nbsp; &#x27;mbuildpl_arg&#x27; =&gt; q[--installdirs site],
&nbsp; &#x27;no_proxy&#x27; =&gt; q[],
&nbsp; &#x27;pager&#x27; =&gt; q[&#x2F;usr&#x2F;bin&#x2F;less],
&nbsp; &#x27;patch&#x27; =&gt; q[&#x2F;usr&#x2F;bin&#x2F;patch],
&nbsp; &#x27;perl5lib_verbosity&#x27; =&gt; q[none],
&nbsp; &#x27;prefer_external_tar&#x27; =&gt; q[1],
&nbsp; &#x27;prefer_installer&#x27; =&gt; q[MB],
&nbsp; &#x27;prefs_dir&#x27; =&gt; q[USERHOME&#x2F;.cpan&#x2F;prefs],
&nbsp; &#x27;prerequisites_policy&#x27; =&gt; q[follow],
&nbsp; &#x27;scan_cache&#x27; =&gt; q[atstart],
&nbsp; &#x27;shell&#x27; =&gt; q[&#x2F;bin&#x2F;bash],
&nbsp; &#x27;show_unparsable_versions&#x27; =&gt; q[0],
&nbsp; &#x27;show_upload_date&#x27; =&gt; q[0],
&nbsp; &#x27;show_zero_versions&#x27; =&gt; q[0],
&nbsp; &#x27;tar&#x27; =&gt; q[&#x2F;bin&#x2F;tar],
&nbsp; &#x27;tar_verbosity&#x27; =&gt; q[none],
&nbsp; &#x27;term_is_latin&#x27; =&gt; q[1],
&nbsp; &#x27;term_ornaments&#x27; =&gt; q[1],
&nbsp; &#x27;test_report&#x27; =&gt; q[0],
&nbsp; &#x27;trust_test_report_history&#x27; =&gt; q[0],
&nbsp; &#x27;unzip&#x27; =&gt; q[&#x2F;usr&#x2F;bin&#x2F;unzip],
&nbsp; &#x27;urllist&#x27; =&gt; [q[<a href="http://cpan.mirror.anlx.net/&#x5D;">http:&#x2F;&#x2F;cpan.mirror.anlx.net&#x2F;]</a>, q[<a href="http://ftp.ticklers.org/pub/CPAN/&#x5D;">http:&#x2F;&#x2F;ftp.ticklers.org&#x2F;pub&#x2F;CPAN&#x2F;]</a>, q[<a href="http://mir2.ovh.net/ftp.cpan.org/&#x5D;">http:&#x2F;&#x2F;mir2.ovh.net&#x2F;ftp.cpan.org&#x2F;]</a>],
&nbsp; &#x27;use_sqlite&#x27; =&gt; q[0],
&nbsp; &#x27;version_timeout&#x27; =&gt; q[15],
&nbsp; &#x27;wget&#x27; =&gt; q[&#x2F;usr&#x2F;bin&#x2F;wget],
&nbsp; &#x27;yaml_load_code&#x27; =&gt; q[0],
&nbsp; &#x27;yaml_module&#x27; =&gt; q[YAML],
};
1;
__END__</code></pre><br>
<br>
<strong>2. Bash setup</strong><br>
Add the below to your ~&#x2F;.bashrc<br>
<pre><code>
PATH=$HOME&#x2F;perl5&#x2F;bin:$HOME&#x2F;bin:$HOME&#x2F;.local&#x2F;bin:&#x2F;user&#x2F;local&#x2F;bin:&#x2F;usr&#x2F;local&#x2F;bin:$HOME&#x2F;bin:&#x2F;usr&#x2F;local&#x2F;bin:&#x2F;usr&#x2F;bin:&#x2F;bin:&#x2F;usr&#x2F;local&#x2F;games:&#x2F;usr&#x2F;games
PERL5LIB=$HOME&#x2F;perl5&#x2F;lib&#x2F;perl5:
PERL_MB_OPT=--install_base $HOME&#x2F;perl5
PERL_LOCAL_LIB_ROOT=:$HOME&#x2F;perl5
PERL_MM_OPT=INSTALL_BASE=$HOME&#x2F;perl5
</code></pre><br>
And source your bashrc<br>
<pre><code>source ~&#x2F;.bashrc</code></pre><br>
<strong>3. Install some Perl mods</strong><br>
<pre><code> cpan Module::Name</code></pre><br>
For example:<br>
<pre><code>cpan Bencode
Reading &#x27;&#x2F;media&#x2F;md0&#x2F;bobtentpeg&#x2F;.cpan&#x2F;Metadata&#x27;
&nbsp; Database was generated on Wed, 13 Jul 2016 16:53:44 GMT
Running install for module &#x27;Bencode&#x27;
Fetching with LWP:
<a href="http://cpan.mirror.anlx.net/authors/id/A/AR/ARISTOTLE/Bencode-1.402.tar.gz">http:&#x2F;&#x2F;cpan.mirror.anlx.net&#x2F;authors&#x2F;id&#x2F;A&#x2F;AR&#x2F;ARISTOTLE&#x2F;Bencode-1.402.tar.gz</a>
Fetching with LWP:
<a href="http://cpan.mirror.anlx.net/authors/id/A/AR/ARISTOTLE/CHECKSUMS">http:&#x2F;&#x2F;cpan.mirror.anlx.net&#x2F;authors&#x2F;id&#x2F;A&#x2F;AR&#x2F;ARISTOTLE&#x2F;CHECKSUMS</a>
Checksum for &#x2F;media&#x2F;md0&#x2F;bobtentpeg&#x2F;.cpan&#x2F;sources&#x2F;authors&#x2F;id&#x2F;A&#x2F;AR&#x2F;ARISTOTLE&#x2F;Bencode-1.402.tar.gz ok
&lt;SNIP&gt;
Files=3, Tests=76,&nbsp; 0 wallclock secs ( 0.03 usr&nbsp; 0.00 sys +&nbsp; 0.12 cusr&nbsp; 0.00 csys =&nbsp; 0.15 CPU)
Result: PASS
&nbsp; ARISTOTLE&#x2F;Bencode-1.402.tar.gz
&nbsp; &#x2F;usr&#x2F;bin&#x2F;make test -- OK
Running make install
Manifying 1 pod document
Installing &#x2F;media&#x2F;md0&#x2F;bobtentpeg&#x2F;perl5&#x2F;lib&#x2F;perl5&#x2F;Bencode.pm
Installing &#x2F;media&#x2F;md0&#x2F;bobtentpeg&#x2F;perl5&#x2F;man&#x2F;man3&#x2F;Bencode.3pm
Appending installation info to &#x2F;media&#x2F;md0&#x2F;bobtentpeg&#x2F;perl5&#x2F;lib&#x2F;perl5&#x2F;x86_64-linux-gnu-thread-multi&#x2F;perllocal.pod
&nbsp; ARISTOTLE&#x2F;Bencode-1.402.tar.gz
&nbsp; &#x2F;usr&#x2F;bin&#x2F;make install&nbsp; -- OK</code></pre><br>
<br>
