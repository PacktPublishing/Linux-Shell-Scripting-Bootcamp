#!/bin/sh
#
# 6/1/2017
#
echo "Chapter 7 - Script 4"

FN=file1.txt                 # filename
if [ ! -f $FN ] ; then
 echo "File $FN does not exist."
 exit 100
fi

while IFS= read -r linevar   # loop using read to put line into linevar
do
  echo "$linevar"            # display contents of linevar
done < $FN                   # the file to use as input

echo "End of script4"
exit 0

