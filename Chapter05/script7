#!/bin/sh
#
# 5/16/2017
#
echo "script7 - Linux Scripting Book"

trap catchCtrlC INT          # Initialize the trap

# Subroutines
catchCtrlC()
{
 echo "Entering catchCtrlC routine."
}

# Code starts here

echo "Press Ctrl-C to trigger the trap, 'Q' to exit."

loop=0
while [ $loop -eq 0 ]
do
 read -t 1 -n 1 str          # wait 1 second for input or for 1 char
 rc=$?

 if [ $rc -gt 128 ] ; then
  echo "Timeout exceeded."
 fi

 if [ "$str" = "Q" ] ; then
  echo "Exiting the script."
  loop=1
 fi

done

exit 0

