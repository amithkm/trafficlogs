# trafficlogs
How to analyse traffic logs from artifactory and Xray 

**What is the data usage as per the traffic logs located in current directory
**
cat artifactory*.log  | awk -F '|' '{ sum += $7 }; END { print sum }
