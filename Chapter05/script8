#!/bin/sh
#
# 5/16/2017
#
echo "script8 - Linux Scripting Book"

# Subroutines
cls()
{
 tput clear
}

move()                       # move cursor to row, col
{
 tput cup $1 $2
}

movestr()                    # move cursor to row, col, display string
{
 tput cup $1 $2
 echo -n $3
}

init()                       # set initial values
{
 minrow=1                    # terminal boundaries
 maxrow=24
 mincol=0
 maxcol=79
 startrow=1
 startcol=0
}

restart()                    # clears screen, sets initial cursor position
{
 cls
 movestr 0 0 "Arrow keys move cursor. 'x' to draw, 'd' to erase, '+' to restart, 'Q' to quit."
 row=$startrow
 col=$startcol

 draw=0                      # default is not drawing
 drawchar=" "
}

checktermsize2()             # must be the specified size
{
 rc1=0                       # default is no error
 if [[ $LINES -ne $1 || $COLUMNS -ne $2 ]] ; then
  rc1=1                      # set return code
 fi
 return $rc1
}

# Code starts here
if [ "$1" = "--help" ] ; then
 echo "Usage: script7 --help"
 echo " This script shows the basics on how to create a game in BASH."
 echo " Use the arrow keys to move the cursor."
 echo " Press c to restart and Q to quit."
 exit 255
fi

checktermsize2 25 80         # terminal must be this size
rc=$?
if [ $rc -ne 0 ] ; then
 echo "Please size the terminal to 25x80 and try again."
 exit 1
fi

init                         # initialize values
restart                      # set starting cursor pos and clear screen

loop=1
while [ $loop -eq 1 ]
do
 move $row $col              # position the cursor here
 read -n 1 -s ch

 case "$ch" in
  A) if [ $row -gt $minrow ] ; then
      let row--
     fi
     ;;
  B) if [ $row -lt $maxrow ] ; then
      let row++
     fi
     ;;
  C) if [ $col -lt $maxcol ] ; then
      let col++
     fi
     ;;
  D) if [ $col -gt $mincol ] ; then
      let col--
     fi
     ;;
  d) echo -n " "             # delete char
     ;;
  x) if [ $col -lt $maxcol ] ; then
      echo -n "X"            # put char
      let col++
     fi
     ;;
  +) restart ;;
  Q) loop=0 ;;
 esac
done

movestr 24 0 "Script completed normally."
echo ""                      # carriage return

exit 0

