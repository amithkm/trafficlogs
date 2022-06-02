# trafficlogs
How to analyse traffic logs from artifactory and Xray 

**What is the total data usage as per the traffic logs located in current directory
**


cat artifactory*.log  | awk -F '|' '{ sum += $7 }; END { print sum }'

**To get most downloaded files,in the output left will be the no of downloads and the right most will be the size of the file.**

grep 'DOWNLOAD|' * | awk -F '|' '{ print $6 "|" $7}' | sort | uniq -c | sort -nr | head -n 20

The traffic log analyser can be run in Mac for the traffic log files using a regular expression ending with *.log, you can change it accordingly based on your requirement

find . -name "*.log" | while read f ; do ./trafficloganalyser.py $f ; done
