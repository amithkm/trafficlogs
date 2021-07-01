# trafficlogs
How to analyse traffic logs from artifactory and Xray 

**What is the data usage as per the traffic logs located in current directory
**
cat artifactory*.log  | awk -F '|' '{ sum += $7 }; END { print sum }



The traffic log analyser can be run in Mac for the traffic log files using a regular expression ending with *.log, you can change it accordingly according to your requirement

find . -name "*.log" | while read f ; do ./trafficloganalyser.py $f ; done
