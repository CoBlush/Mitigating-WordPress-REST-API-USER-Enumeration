# Mitigating-WordPress-REST-API-USER-Enumeration
<p> Usernames and userIDs on WordPress are by default exposed to the public via a REST API virtual endpoint.</p>
<p> Test this by using this curl command:</p>
<p> "curl http://test/wp-json/wp/v2/users"<br> </br>
"curl https://test.com/wp-json/wp/v2/users"</p>
<p> After Executing the curl command above you should be met with a json file listing various users, in my experience most users are listed but not always 100%</p>
<p> The Virtual endpoint has non authenticated access configured for the public. <br> To resolve this traverse to your .htacess file</p>

<p> <IfModule mod_rewrite.c> </p>
 <P>RewriteEngine On</P>   
   <P> RewriteCond %{REQUEST_URI} ^/wp-json/wp/v2/users [OR]</P> 
    <P> RewriteCond %{REQUEST_URI} ^/wp-json/oembed/1.0/embed </P>
    <P> RewriteRule .* - [F,L] </P>
<P></IfModule> </P>
