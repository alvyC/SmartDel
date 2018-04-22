#!/bin/bash
# This module will restore specified file from recycle folder to currect directory.
# If multiple file with same name exits, it will prompt the user to choose the required file.
# it will delete the restored file from recycle.

# input: file to restore from recycle.

filename=$1
restoredfile=$2
echo $filename $restoredfile

files=`grep 'metadata' $filename`
filesNum=`grep 'metadata' $filename | wc -l`

echo "$filesNum Files with name: $filename was deleted"
echo $filesNum
echo
message=`echo "$files" | cut -d' ' -f2,4-11`

echo
if [ "$filesNum" -eq "1" ];then
		head -n $(awk 'END {print NR-1}' $filename) $filename > $restoredfile
		#fileContent=`paste tempFile`
		#move temp file and remove temp file from this location
		#echo $fileContent
		rm $filename
else
		echo "$message"
		read -p "Please select which one you want to restore: " rFileNum
		#echo $filesNum
		searchStr=`echo "choice$rFileNum:"`
		#echo $searchStr
		end=`grep "$searchStr" $filename | cut -d' ' -f12`
		start=`grep "$searchStr" $filename | cut -d' ' -f13` 
		#echo $start $end
		#fileContent=`head -$end $filename | tail -$start`
		head -$end $filename | tail -$start > $restoredfile
		#echo "Restored file content:"
		#echo "$fileContent"
		#echo "file shown"
		# Deleting files
		numLine=$start
		#echo $numLine
		#echo hello
		delEnd=`grep "$searchStr" -n $filename | cut -d: -f1`
		#echo $delEnd
		((delStart = $delEnd - $start))
		#echo $delEnd $delStart

		#exit

		#let delEnd=$end+1
		#echo $delStart
		if [ "$numLine" -eq "0" ];then
			sed  "$delEnd d" $filename > tempFile
			mv tempFile $filename
			#echo IF Line number:$numLine
			#echo 
		else 
		   #echo Else Line number:$numLine
		   sed  "$delStart, $delEnd d" $filename > tempFile
		   mv tempFile $filename
		fi 
		#echo "$fileContent" > restoredfile

fi