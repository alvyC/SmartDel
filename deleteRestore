#!/bin/bash
# bash script for project
# Nurmohammed Patwary

#fileOrigin=`pwd`
#recycleLocation=~/COMP6242/Project/smartdel_recycle/ 
#numArgument="$#"
#echo "num arg: $numArgument"

option=$1
fileName=$2
#echo $option $fileName

case $option in
	-d) 

				originalfile=`echo "$fileOrigin/$fileName"`
				recycleFile=$recycleLocation$fileName 
				./smartSave $originalfile $recycleFile
			
		;;
	-r) 
		fileToRestore=$recycleLocation$fileName
		restoredFileName=$fileName
		if [ -f $fileName ]; then
			echo "File with name: '$fileName' exist"
			echo "To overwrite existing file, press 1"
			echo "To save with a different name, press 2"
			read choice
				if [ $choice = 1 ]; then
					./smartRes $recycleLocation$fileName $restoredFileName
					echo
					echo "File restored with overwriting the existing one."
				elif [ $choice = 2 ]; then
					echo					
				    read -p "Enter the new file name: " newFilename
					currentDirectory=`pwd`
					forwardSlash=/			
					restoredFileName=$currentDirectory$forwardSlash$newFilename
					echo 
					echo
					./smartRes $recycleLocation$fileName $restoredFileName
					echo "File restored with the specified file name"
				else
					echo "Please enter the right choice"
				fi
		else
				./smartRes $recycleLocation$fileName $restoredFileName
 		fi
 		
		;;
	*)
			echo "Unknown option"
		;;
esac

