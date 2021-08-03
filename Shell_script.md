 ### Assignment 2
 - Create a CloudLab infrastructure consisting of two compute nodes with the following requirements:
 - The nodes are named webserver and observer.
 - The webserver node runs an Apache web server with a public IP address.
 - The observer node runs an NFS server without a public IP address.
 - Both nodes are connected to the same network.
 - On observer, create a new directory called webserver_monitor inside /var.
 - This directory will be NFS-mounted readable/writable on webserver as /var/webserver_log.
 ##### Question 1:
 - On webserver, Create a shell script called scan.sh that will scan the webserver's auth.log file for unauthorized/failed SSH access. You will need to figure out how to use grep to filter out the relevant information.
 - Based on the IP information, scan.sh should also identifies the country of origin of this IP address automatically. The resulting information should be appended to a file called unauthorized.log inside the NFS-mounted /var/webserver_log with the following format: IP_ADDRESS COUNTRY DATE.
 - Create a cron job that will execute this script every 5 minutes.

##### Sol:
cat scan.sh
if [ `hostname` == webserver]
then
  egrep 'unauthorized|failed' auth.log
else
  print ( "You need to run this script on webserver only" )
fi

 ##### Question 2:
 - On observer, create a new script called monitor.sh to monitor /var/webserver_monitor/unauthorized.log. If there are new entries, an email should be sent to the admin with the content of these new entries. Otherwise, the email simply says "No unauthorized access."
 - Create a cron job that runs monitor.sh every hour.
 - Once everything is setup, the CloudLab experiment should be left running for at least 12 hours. Make sure that you collect the necessary files from these nodes before the experiment expires. Hint: use scp to copy these files back to your local machine.
