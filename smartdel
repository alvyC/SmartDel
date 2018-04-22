#!/bin/bash
# bash script for project
# Nurmohammed Patwary

set -f
export fileOrigin=`pwd`
export recycleLocation=~/Desktop/UnixProject/smartdel_recycle/
numArgument="$#"  # $# = number of argument
#echo $numArgument

if [ "$numArgument" -eq 0 ]; then
		echo "error: please specify the file name"
		exit 100
elif [ "$numArgument" -eq 1 ]; then
     option=-d
     filename=$1
elif [ "$numArgument" -eq 2 ]; then
	 option=$1
     filename=$2
else
		echo "Please give the right argument"
		exit 100
fi

exitStatus=`echo $?`  # get the exit status of the last executed command
echo $exitStatus
if [ "$exitStatus" -ne 100 ]; then
	#echo $option $filename
	fileName=$(./retrieveFilename $option $filename)
	fileNames=($fileName)

	for files in ${fileNames[@]} ; do
		#echo $files
		./deleteRestore $option $files 
	done
else
	exit
fi
set +f