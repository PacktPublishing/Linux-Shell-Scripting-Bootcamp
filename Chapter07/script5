#!/bin/sh
#
# 6/1/2017
#
echo "Chapter 7 - Script 5"

if [ $# -ne 2 ] ; then
 echo "Usage: script5 infile outfile"
 echo " Copies text file infile to outfile."
 exit 255
fi

INFILE=$1
OUTFILE=$2

if [ ! -f $INFILE ] ; then
 echo "Error: File $INFILE does not exist."
 exit 100
fi

if [ $INFILE = $OUTFILE ] ; then
 echo "Error: Cannot copy to same file."
 exit 101
fi

rm $OUTFILE 2> /dev/null       # remove it
echo "Reading file $INFILE ..."

x=0
while IFS= read -r linevar     # loop using read to put line into linevar
do
  echo "$linevar" >> $OUTFILE  # append to file
  let x++
done < $INFILE                 # the file to use as input
echo "$x lines read."

diff $INFILE $OUTFILE          # use diff to check the output
rc=$?
if [ $rc -ne 0 ] ; then
 echo "Error, files do not match."
 exit 103
else
 echo "File $OUTFILE created."
fi

sum $INFILE $OUTFILE           # show the checksums

echo "End of script5"
exit $rc

