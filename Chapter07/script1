#!/bin/sh
#
# 6/1/2017
#
echo "Chapter 7 - Script 1"
FN=file1.txt
rm $FN 2> /dev/null          # remove it silently if it exists
x=1
while [ $x -le 10 ]          # 10 lines
do
 echo "x: $x"
 echo "Line $x" >> $FN       # append to file
 let x++
done
echo "End of script1"
exit 0

