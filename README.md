# netstat_dc

NetStat Data Collection script

A simple utility that will create 2 files based on netstat output.

File 1 contains output based on the following
  1. Run netstat
  2. Get all endpoints that are ESTABLISHED status (i.e. the ip address of the endpoint)
  3. Ping the endpoint 3 times
  4. Record to a csv file the ping statistics

File 2 contains output based on the following rules
  1. Run netstat
  2. Get all endpoints that are in 'ESTABLISHED', 'TIME_WAIT', 'CLOSE_WAIT' or 'SYN_SENT' status
  3. Record the output to a csv file  

Set the script as executable then you can run this file as-is or execute it via cron every 15 minutes.

`# ./dc_netstat.sh`

For Solaris boxen:
Set the script as executable then you can run this file as-is or execute it via cron every 15 minutes.

`# ./solaris_dc_netstat_v2.sh`

With these files you can use Splunk or the like to process them and find common communication between servers and latency of these connections.