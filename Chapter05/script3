#!/bin/sh
#
# 5/16/2017
#
echo "script3 - Linux Scripting Book"

if [ "$1" = "--help" ] ; then
 echo "Usage: script3"
 echo " Queries the user for values and puts them into an array."
 echo " Entering 'q' will halt the script."
 echo " Running 'script3 --help' shows this Usage message."
 exit 255
fi

x=0                          # subscript into array
loop=0                       # loop control variable
while [ $loop -eq 0 ]
do
 echo -n "Enter a value or q to quit: "
 read value
 if [ "$value" = "q" ] ; then
  loop=1
 else
  array[$x]="$value"
  let x++
 fi
done

let size=x
x=0
while [ $x -lt $size ]
do
 echo "array $x: ${array[x]}"
 let x++
done

echo "End of script3"
exit 0

