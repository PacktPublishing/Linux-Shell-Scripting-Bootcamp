#!/bin/sh
# 6/8/2017
# Chapter 9 - Script 9
#
TTY=/dev/pts/35              # debug terminal

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

checktermsize()
{
 p1 "Entering routine checktermsize."

 rc1=0                       # default is no error
 if [[ $LINES -lt $1 || $COLUMNS -lt $2 ]] ; then
  rc1=1                      # set return code
 fi
 return $rc1
}

init()                       # set up the cursor position array
{
 p1 "Entering routine init."

 srow[0]=2;  scol[0]=7       # name
 srow[1]=4;  scol[1]=12      # address 1
 srow[2]=6;  scol[2]=12      # address 2
 srow[3]=8;  scol[3]=7       # city
 srow[4]=8;  scol[4]=37      # state
 srow[5]=8;  scol[5]=52      # zip code
 srow[6]=10; scol[6]=8       # email
}

drawscreen()                 # main screen draw routine
{
 p1 "Entering routine drawscreen."

 cls                         # clear the screen
 movestr 0 25 "Chapter 9 - Script 9"
 movestr 2 1 "Name:"
 movestr 4 1 "Address 1:"
 movestr 6 1 "Address 2:"
 movestr 8 1 "City:"
 movestr 8 30 "State:"
 movestr 8 42 "Zip code:"
 movestr 10 1 "Email:"
}

getdata()
{
 p1 "Entering routine getdata."

 x=0                         # array subscript
 rc1=0                       # loop control variable
 while [ $rc1 -eq 0 ]
 do
  row=${srow[x]}; col=${scol[x]}

  p1 "row: $row  col: $col"

  move $row $col
  read array[x]
  let x++
  if [ $x -eq $sizeofarray ] ; then
   rc1=1
  fi
 done
 return 0
}

showdata()
{
 p1 "Entering routine showdata."

 fn=0
 echo ""
 read -p "Enter filename, or just Enter to skip: " filename
 if [ -n "$filename" ] ; then       # if not blank
  echo "Writing to '$filename'"
  fn=1                       # a filename was given
 fi
 echo ""                     # skip 1 line
 echo "Data array contents: "
 y=0
 while [ $y -lt $sizeofarray ]
 do
  echo "$y - ${array[$y]}"
  if [ $fn -eq 1 ] ; then
   echo "$y - ${array[$y]}" >> "$filename"
  fi
  let y++
 done
 return 0
}

p1()                         # display to TTY
{
 rc1=0                       # default is no error
 if [ $# -ne 1 ] ; then
  rc1=2                      # missing parameter
 else
  echo "$1" > $TTY
  rc1=$?                     # set error status of echo command
 fi

 return $rc1
}

# Code starts here

p1 " "                       # carriage return
p1 "Starting debug of script9"

sizeofarray=7                # number of array elements

if [ "$1" = "--help" ] ; then
 p1 "In Usage clause."

 echo "Usage: script9 --help"
 echo " This script shows how to create an interactive screen program"
 echo " and how to use another terminal for debugging."
 exit 255
fi

checktermsize 25 80
rc=$?
if [ $rc -ne 0 ] ; then
 echo "Please size the terminal to 25x80 and try again."
 exit 1
fi

init                         # initialize the screen array
drawscreen                   # draw the screen
getdata                      # cursor movement and data input routine
showdata                     # display the data

p1 "At exit."
exit 0

