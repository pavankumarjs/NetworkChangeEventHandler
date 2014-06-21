NetworkChangeEventHandler
=========================

Detects the change in wifi network and triggers the required set of commands.

###Requirements
* Runs only on Macbooks with airport utility installed.

###Installation Steps
* Checkout the package and open the "networkchangehandler" file.
* Replace the NETWORKNAME with the actual network name for which the change event needs to be triggered.
* Add the shell commands under changeEventHandler() function. They will be triggered upon connect event to the NETWORKNAME.
* Similarly, add shell commands under changeEventReverter() function, which will triggered upon NETWORKNAME disconnect.
* Save the file and move it to /usr/local/bin/
* Open crontab as sudo (compulsory!). Command: "sudo crontab -e"
* Add the following text and save: "* * * * * /usr/local/bin/networkchangehandler"

###Explanation
* The script runs as a cron job every minute.
* It checks for the current network/wifi name to trigger the changeEventHandler and changeEventReverter for connect and disconenct respectively.
* Logs can be found at /var/log/networkchangehandler/output.log
