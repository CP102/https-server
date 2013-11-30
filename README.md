https-server
============
<html>
<body>
<h2>Basic https server that hosts a simple html page.</h2>
<h2>
Server:</h2>
<pre class="prettyprint lang-js">
var https = require('https');
var fs = require('fs');

var options = {
  key: fs.readFileSync('key.pem'),
  cert: fs.readFileSync('cert.pem')
};
var a = https.createServer(options, function (req, response) {
  response.writeHead(200, {"Content-Type": "text/html"});
  response.write(&quot;&amp;lt;html&amp;gt;&quot;);
  response.write('&amp;lt;body&amp;gt;');
  response.write('&lt;h1&gt;');
  response.write('Server is working');
  response.write('&lt;/h1&gt;');
  response.write('&amp;lt;/body&amp;gt;');
  response.write('&amp;lt;/html&amp;gt;');
  response.write('login.html');
  response.end();
}).listen(8000);

console.log("Server running at http://127.0.0.1:8000/");
</pre>
</body>
</html>
