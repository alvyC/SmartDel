#!/bin/bash
# bash script for project
# Nurmohammed Patwary

#fileOrigin=`pwd`
#recycleLocation=~/COMP6242/Project/smartdel_recycle/ 

set -f
option=$1
fileName=$2
#echo $option $fileName
set +f
case $option in
	-d) 
          files=`ls $fileName`
          echo $files 
           			
		;;
	-r) 
		cd $recycleLocation
 		echo `ls $fileName`
 		cd $fileOrigin
		;;
	*)  
			echo "Unknown option"
			
		;;
esac