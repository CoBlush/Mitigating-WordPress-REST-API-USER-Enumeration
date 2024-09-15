# Mitigating-WordPress-REST-API-USER-Enumeration
<p> Usernames and userIDs on WordPress are by default exposed to the public via a REST API virtual endpoint.</p>
<p> Test this by using this curl command:</p>
<p> "curl http://test/wp-json/wp/v2/users"<br> </br>
"curl https://test.com/wp-json/wp/v2/users"</p>
