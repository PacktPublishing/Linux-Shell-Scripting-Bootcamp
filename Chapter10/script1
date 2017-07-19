#!/bin/sh
#
# 6/11/2017
# Chapter 10 - Script 1
#

# Subroutines
trap catchCtrlC INT          # Initialize the trap

# Subroutines
catchCtrlC()
{
 loop=0                      # end the loop
}

cls()
{
 tput clear
}

movestr()                    # move cursor to row, col, display string
{
 tput cup $1 $2
 echo -n "$3"
}

# Code
if [ "$1" = "--help" ] ; then
 echo "Usage: script1 or script1 --help "
 echo " Shows the low and high count of the Bash RANDOM variable."
 echo " Press Ctrl-C to end."
 exit 255
fi

sym[0]='|'
sym[1]='/'
sym[2]='-'
sym[3]='\'

low=99999999
high=-1

cls
echo "Chapter 10 - Script 1"
echo "Calculating RANDOM low and high ..."
loop=1
count=0
x=0
while [ $loop -eq 1 ]
do
 r=$RANDOM
 if [ $r -lt $low ] ; then
  low=$r
 elif [ $r -gt $high ] ; then
  high=$r
 fi

# Activity indicator
 movestr 2 1 "${sym[x]}"     # row 2 col 1
 let x++
 if [ $x -gt 3 ] ; then
  x=0
 fi

 let count++
done

echo " "                     # carriage return
echo "Number of loops: $count"
echo "low: $low  high: $high"

echo "End of script1"
exit 0

