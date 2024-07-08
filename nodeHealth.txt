#!/bin/bash
#############################################################################
#Author : Mahadev Hugar
#Date : 03/07/2024
#Purpose :  This script is excecutes output of the node health
#Version : v1
############################################################################
#
#
#
#

set -x
set -e
set -o pipefail
# printing disc space
df -h


# printing the menory
free -g

#printing the resource of cpu
nproc

#printing running proecess
ps -ef | grep "amazon" | awk -F " " '{print $2}'

# geting log file
#curl "https://github.com/logpai/loghub/blob/master/Apache/Apache_2k.log"

#getting logs with error using grep
curl "https://github.com/logpai/loghub/blob/master/Apache/Apache_2k.log" | grep [error]

#To downlad file
wget "https://github.com/logpai/loghub/blob/master/Apache/Apache_2k.log"

