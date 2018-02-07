# PtTracker - Profit Trailer Tracking Addon
PtTracker is a ProfitTrailer addon that uses the bot trading data to automatically track your daily and monthly profits in real time.

<a href="https://ibb.co/nLjtox"><img src="https://preview.ibb.co/b8R68x/Screenshot_2018_02_06_12_30_41.jpg" alt="Screenshot_2018_02_06_12_30_41" border="0"></a>

<h1>FAQ</h1>
<b>Will it work with the Feeder addon?</b> Yes, feeder is simply a tool that updates your pairs/config files based on current market conditions. PtTracker does not make any changes to your setup or files.
<br><br>
<b>Is it safe?</b> Yes, PtTracker is simply an html file and works by reading the ProfitTrailerData.json file created by ProfitTrailer. Since this file only contains bot trading data, PtTracker is safe, secure, and does not access or use any api keys or other sensitive information.
  
<h1>Purchasing</h1>
1. Send a message to btayfla#0063 on <a target="_blank" href="https://discordapp.com/">Discord</a> or to pt_tracker on <a target="_blank" href="https://t.me/pt_tracker">Telegram</a>. You will receive a reply with the payment address.<br>
2. Send 0.005 BTC or 0.3 LTC (Send enough to cover your transfer fee)<br>
3. Once payment is confirmed, you will receive a reply with your license key and install files.

<h1>Installing PtTracker</h1>
Extract the PtTracker.zip files into your ProfitTrailer Folder. (Same folder as application.properties)<br>
 
<h2>Configuring PtTracker.json</h2>

Open PtTracker.json in a text editor, add your username, license key, starting value, and then save.
(Note: Your license key has single user access. If you give it to someone else, your tracker will no longer work.)<br>

<b>StartingValue</b> is the balance you started with when you first purchased the bot and is needed to calculate your current balance. If you do not update this, your balance will not be accurate. PtTracker does not have access to your api keys that would be needed to get this data automatically.

<b>Deposits/Withdrawls</b> can be added by editing the transfers section in PtTracker.json. Simple add the date (mm/dd/yyyy format) and a positive or negative value. (Do not add a comma to the last item or PtTracker will not work.)

```
"Transfers": {
   "01/07/2018": "0.06",
   "02/02/2018": "-0.02",
   "02/14/2018": "0.8"
  }
```

<h1>Running PtTracker using Mongoose (Windows) </h1>
1. After installing PtTracker, <a href="https://cesanta.com/binary.html">Download Mongoose (Windows)</a> and place the .exe file in your ProfitTrailer Folder.<br>
2. Open Mongoose (Double click exe file)<br>
(Mongoose is a standalone web server. Block port 8084 in your firewall for security)

<h1>Running PtTracker (Linux)</h1>

1. Install Apache https://www.digitalocean.com/community/tutorials/how-to-install-the-apache-web-server-on-ubuntu-16-04

2. Move PtTracker.html and PtTracker.json to your web root (/var/www/html)

3. Create a shell script to copy your Profit Trailer data to web root: ```nano /var/scripts/myscript.sh```

Add the following lines
```
#!/bin/sh
rm /var/www/html/ProfitTrailerData.json
cd /home/profitTrailer
cp /home/profitTrailer/ProfitTrailerData.json /var/www/html/ProfitTrailerData.json
cd /var/www/html
chown www-data:www-data /var/www/html/ProfitTrailerData.json
```

4. Setup crontab to run script every three minutes.<br>
Give full permission: ```sudo chmod a+x /var/scripts/myscript.sh```<br>
Edit crontab: ```crontab -e command```<br>
Add a new line: ``` */3 * * * * /var/scripts/myscript.sh```<br>

5. Access PtTracker at http://{YourIp}/PtTracker.html

<h1>Running PtTracker (Raspberry Pi)</h1>
<h2>Python 2</h2>

Change directory into the ProfitTrailer folder using the command ```cd /path/to/your/ProfitTrailer```

Start up a Python web server using the command ```python -m SimpleHTTPServer 8084```

This will start a web server that hosts PtTracker, which will be made accessible through the following URL: http://localhost:8084/PtTracker.html OR http://{YourServerIp}:8084/PtTracker.html

This approach is built in to any Python installation.

<h2>Python 3</h2>
Do the same steps, but use the following command instead ```python3 -m http.server 8084```

<h2>Security</h2>
For extra security, you can block port 8084 in your firewall and add authentication using: https://github.com/tianhuil/SimpleHTTPAuthServer

<h1>Running PtTracker using your own web server (Any OS)</h1>

Configure your webserver to serve your ProfitTrailer folder as webroot directory locally.<br>
Access with: http://localhost/PtTracker.html<br>

<h1>Contact / Support</h1>
<a target="_blank" href="https://discordapp.com/">Discord:</a> btayfla#0063<br>
<a target="_blank" href="https://t.me/pt_tracker">Telegram:</a>  pt_tracker

<h1>Donate</h1>
And let me know on discord or telegram if you do so I can thank you!<br>
BTC: 13EUZ5juobs1XfZW6Ad3QTkbhvchsKbbJN<br>
LTC: LbmkWmVP1npYtcZtW44Xq1SSGJsRCFZNvC<br>
ETH: 0xAcc1416387B7C3f9AF0E93A9583C95EB441dDD6
