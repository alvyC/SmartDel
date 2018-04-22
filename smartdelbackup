#!/bin/bash
# bash script for project
# Nurmohammed Patwary

option=$1
fileName1=$1
fileName2=$2
set +f

fileOrigin=`pwd`
recycleLocation=~/COMP6242/Project/smartdel_recycle/ 
case $option in
	-d) 
		if [ -f $recycleLocation$fileName2 ]; then
			newFile=$recycleLocation$fileName2
			newFileExt=copy1
			copyFile=$newFile$newFileExt	
			cp $fileName2 $copyFile 
			rm $fileName2
		else			
			mv $fileName2 $recycleLocation 
		fi
		;;
	-r) 
		if [ -f $fileName2 ]; then
			echo "File with name: '$fileName2' exist"
			echo "To overwrite existing file, press 1"
			echo "To save with a different name, press 2"
			read choice
				if [ $choice = 1 ]; then
					mv $recycleLocation$fileName2 `pwd`
					echo
					echo "File restored with overwriting the existing one."
				elif [ $choice = 2 ]; then
					echo					
					echo "Enter the new file name:"	
					echo						
					read newFilename
					currentDirectory=`pwd`
					forwardSlash=/			
					finalFileName=$currentDirectory$forwardSlash$newFilename
					echo 
					echo
				        mv $recycleLocation$fileName2 $finalFileName
					echo "File restored with the specified file name"
				else
					echo "Please enter the right choice"
				fi
		else
			mv $recycleLocation$fileName2 `pwd` 
		fi
		;;
	*)  
		if [ -f $recycleLocation$fileName1 ]; then
			newFile=$recycleLocation$fileName1
			newFileExt=copy1
			copyFile=$newFile$newFileExt	
			echo $copyFile
			cp $fileName1 $copyFile
			rm $fileName1
		else			
			mv $fileName1 $recycleLocation 
		fi
		;;
esac 

