# pttracker
A ProfitTrailer addon that uses PT data files to automatically track your daily and monthly profits in real time.

<a href="https://ibb.co/iYGJR6"><img src="https://preview.ibb.co/d1UuzR/Screenshot_2018_02_03_12_19_08.jpg" alt="Screenshot_2018_02_03_12_19_08" border="0"></a>

<h1>Installing PtTracker</h1>
1. Save files in your ProfitTrailer Folder. (Same folder as application.properties)<br>
2. Open PtTracker.json in a text editor, add your username, license key, details, and then save.
(Note: Your license key has single user access. If you give it to someone else, your tracker will no longer work.)<br>
3. (skip this step if you want to run your own local webserver) <a href="https://cesanta.com/binary.html">Download Mongoose (Windows)</a> and place the .exe file in the same folder.

<h1>Running PtTracker using Mongoose (Windows) </h1>

Open Mongoose (exe file) in your ProfitTrailer folder.<br>
(Mongoose is a standalone web server. Block port 8084 in your firewall for security)

<h1>Running PtTracker (Linux)</h1>

<h2>Python 2</h2>
If you have Python installed...

Change directory into the ProfitTrailer folder using the command cd /path/to/your/folder

Start up a Python web server using the command python -m SimpleHTTPServer

This will start a web server that hosts your entire directory, which will be made accessible through the following URL: http://localhost:8000 

This approach is built in to any Python installation.

Point your browser to: http://localhost:8000/PtTracker.html

<h2>Python 3</h2>
Do the same steps, but use the following command instead python3 -m http.server

<h2>Node.js</h2>
Alternatively, if you demand a more responsive setup and already use nodejs...

Install http-server by typing npm install -g http-server

Change into your Profit Trailer folder

Start your http server by issuing http-server -c-1

This spins up a Node.js httpd which serves the files in your directory as static files accessible from http://localhost:8080

<h2>Ruby</h2>
If your preferred language is Ruby ... the Ruby Gods say this works as well:

ruby -run -e httpd . -p 8000

Point your browser to: http://localhost:8000/PtTracker.html

<h2>PHP</h2>
Of course PHP also has its solution.

php -S localhost:8000

Point your browser to: http://localhost:8000/PtTracker.html

<h1>Running PtTracker using your own web server (Any OS)</h1>

Configure your webserver to serve your ProfitTrailer folder as webroot directory locally.<br>
Access with: http://localhost/PtTracker.html<br>
If you decide to serve it publicly to view PtTracker remotely, make sure you add an <a href="http://www.htaccesstools.com/htpasswd-generator/">htaccess file</a> for security.


<h1>Purchasing</h1>
1. Message me on Discord or Telegram. I will reply with the payment address.<br>
2. Send 0.003 BTC or 0.2 LTC (Send enough to cover your transfer fee)<br>
3. Once payment is confirmed, I will send your license key.

<h1>Contact</h1>
Discord: btayfla#0063<br>
Telegram: https://t.me/pt_tracker



<h1>Donate</h1>
And let me know on discord or telegram if you do so I can thank you!<br>
BTC/LTC: 13EUZ5juobs1XfZW6Ad3QTkbhvchsKbbJN<br>
ETH: 0xAcc1416387B7C3f9AF0E93A9583C95EB441dDD6
