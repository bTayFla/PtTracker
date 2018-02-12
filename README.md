# PtTracker - Profit Trailer Tracking Addon
PtTracker is a ProfitTrailer addon that uses the bot trading data to automatically track your daily and monthly profits in real time.
Website: <a href="http://PtTracker.net" target="_blank">http://PtTracker.net</a>
  
<a href="https://ibb.co/nLjtox"><img src="https://preview.ibb.co/b8R68x/Screenshot_2018_02_06_12_30_41.jpg" alt="Screenshot_2018_02_06_12_30_41" border="0"></a>

<h1>FAQ</h1>
<b>Is my setup supported?</b> Yes, PtTracker will work on any ProfitTrailer-supported operating system in any environment including VPS, Standalone, and Raspberry Pi.
<br><br>
<b>Will it work with the Feeder addon?</b> Yes, feeder is a tool that updates your pairs/config files based on current market conditions. PtTracker does not make any changes to your setup or files.
<br><br>
<b>Is ETH and USDT supported? What other currencies are supported?</b> Yes, You can set PtTracker to use any currency of your choice. All trading currencies that are supported by Profit Trailer are also supported by PtTracker. 
<br><br>
<b>What exchanges are supported?</b> Since PtTracker only reads trading data from the bot itself and does not access any exchange data, all exchanges that are supported by Profit Trailer are also supported by PtTracker.
<br><br>
<b>Is my data safe?</b> Yes, PtTracker is simply an html file and works by reading the ProfitTrailerData.json file created by ProfitTrailer. Since this file only contains bot trading data, PtTracker is safe, secure, and does not access or use any api keys or other sensitive information.
<br><br>
<b>Can I use PtTracker on more than one bot/exchange?</b> Your PtTracker license key will work for as many bots as you want as long as they are on the same server/vps/pc. If you use bots on different machines, a license key will need to be purchased for each machine. 
<br><br>
<b>Is PtTracker officially endorsed by ProfitTrailer?</b>
Not yet! However, we hope to make this happen soon. Hint hint @ProfitTrailer ;)


<h1 id="#purchasing">Purchasing</h1>
Purchase at: http://ptTracker.net

<h1>Installing PtTracker</h1>
Change trading.logHistory in the application.properties file in your ProfitTrailer folder to prevent data removal:

 ```trading.logHistory = 99999999```  

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

<h1>Running PtTracker (Windows / Mac) </h1>
1. After installing PtTracker, <a href="https://cesanta.com/binary.html">Download Mongoose (Windows / Mac)</a> and place the executable file in your ProfitTrailer Folder.<br>
2. Open Mongoose (Double click executable file)<br>

<h2>Security</h2>
Mongoose is a standalone web server. It is reccomended to block port 8084 in your firewall for security

<h1>Running PtTracker (Linux)</h1>

1. Install Apache https://www.digitalocean.com/community/tutorials/how-to-install-the-apache-web-server-on-ubuntu-16-04

2. Copy the PtTracker.html and PtTracker.json files to your web root (/var/www/html)

3. Copy the ProfitTrailerData.json file from PT folder to your webroot ```cp /home/profitTrailer/ProfitTrailerData.json /var/www/html/ProfitTrailerData.json```

4. Create a shell script to automatically copy your Profit Trailer data to web root: ```nano /var/scripts/getPtTrackerData.sh```

Add the following lines
```
#!/bin/sh
rm /var/www/html/ProfitTrailerData.json
cd /home/profitTrailer
cp /home/profitTrailer/ProfitTrailerData.json /var/www/html/ProfitTrailerData.json
cd /var/www/html
chown www-data:www-data /var/www/html/ProfitTrailerData.json
```

5. Setup crontab to run script every three minutes.<br>
Give full permission: ```sudo chmod a+x /var/scripts/getPtTrackerData.sh```<br>
Edit crontab: ```crontab -e command```<br>
Add a new line: ``` */3 * * * * /var/scripts/getPtTrackerData.sh```<br>

6. Access PtTracker at http://{YourIp}/PtTracker.html

<h2>Security</h2>
It is reccomended to add htaccess and htpassword for extra security. http://www.htaccesstools.com/articles/password-protection/

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
<a target="_blank" href="https://t.me/pt_tracker">Telegram:</a>  pt_tracker<br>
<a href="http://PtTracker.net" target="_blank">Website:</a> http://PtTracker.net

<h1>Donate</h1>
And let me know on discord or telegram if you do so I can thank you!<br>
BTC: 13EUZ5juobs1XfZW6Ad3QTkbhvchsKbbJN<br>
LTC: LbmkWmVP1npYtcZtW44Xq1SSGJsRCFZNvC<br>
ETH: 0xAcc1416387B7C3f9AF0E93A9583C95EB441dDD6
