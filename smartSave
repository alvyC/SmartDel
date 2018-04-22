#!/bin/bash
# This module will remove the specified file from current 
# directory with METAFILE at the bottom of each file.

# if specified file does not exist, it will retun exit status 10
# METAFILE: ----file_info Stating_Line_Num Num_of_Lines
# -------------------------------------------------------------
source=$1
dest=$2
if [ -f $source ]; then
	souceInf=`ls -l $1 | cut -d' ' -f3-9`
	numLine=`cat $source | wc -l`
	cat $source >> $dest
	sourceDir=`pwd`
	destEnd=`cat $dest | wc -l`
	((startLine=destEnd))
	numOccrance=`grep 'metadata' $dest | wc -l`
	((numOccrance=$numOccrance+1))
	metaFile=`echo "choice$numOccrance: $numOccrance metadata $sourceDir $souceInf $startLine $numLine "`
	#echo "$metaFile"
	echo "$metaFile" >> $dest
	rm $source
else
	echo "File Does not exist" # this comment is to move to main program; checking exit status
	exit 10
fi