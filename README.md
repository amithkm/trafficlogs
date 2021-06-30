# trafficlogs
How to analyse traffic logs from artifactory and Xray 


cat artifactory*.log  | awk -F '|' '{ sum += $7 }; END { print sum }
