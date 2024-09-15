# Mitigating-WordPress-REST-API-USER-Enumeration
<p> Usernames and userIDs on WordPress are by default exposed to the public via a REST API virtual endpoint.</p>
<p> Test this by using this curl command:</p>
<p> "curl http://test/wp-json/wp/v2/users"<br> </br>
"curl https://test.com/wp-json/wp/v2/users"</p>
<p> After Executing the curl command above you should be met with a json file listing various users, in my experience most users are listed but not always 100%</p>
<p> The Virtual endpoint has non authenticated access configured for the public. <br> To resolve this traverse to your .htacess file</p>

<pre><code>
&lt;IfModule mod_rewrite.c&gt;
    RewriteEngine On
    RewriteCond %{REQUEST_URI} ^/wp-json/wp/v2/users [OR]
    RewriteCond %{REQUEST_URI} ^/wp-json/oembed/1.0/embed
    RewriteRule .* - [F,L]
&lt;/IfModule&gt;
</code></pre>

<P> See <a href= "https://github.com/CoBlush/Mitigating-WordPress-REST-API-USER-Enumeration/blob/main/Explanation%20.pdf"> "Eplanation.pdf"</a>  for configuration breakdown</P>

