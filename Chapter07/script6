#!/bin/sh
# 6/2/2017
# Chapter 7 - Script 6

trap catchCtrlC INT          # Initialize the trap

# Subroutines

catchCtrlC()
{
 move 13 0
 savefile

 movestr 23 0 "Script terminated by user."
 echo ""                     # carriage return

 exit 0
}

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
 echo -n "$3"                # quote it
}

checktermsize()
{
 rc1=0                       # default is no error
 if [[ $LINES -lt $1 || $COLUMNS -lt $2 ]] ; then
  rc1=1                      # set return code
 fi
 return $rc1
}

init()                       # set up the cursor position array
{
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
 cls                         # clear the screen
 movestr 0 25 "Chapter 7 - Script 6"

 movestr 2 1  "Name: ${array[0]}"
 movestr 4 1  "Address 1: ${array[1]}"
 movestr 6 1  "Address 2: ${array[2]}"
 movestr 8 1  "City: ${array[3]}"
 movestr 8 30 "State: ${array[4]}"
 movestr 8 42 "Zip code: ${array[5]}"
 movestr 10 1 "Email: ${array[6]}"
}

getdata()
{
 x=0                         # start at the first field
 while [ true ]
 do
  row=${srow[x]}; col=${scol[x]}
  move $row $col
  read var
  if [ -n "$var" ] ; then    # if not blank assign to array
    array[$x]=$var
  fi
  let x++
  if [ $x -eq $sizeofarray ] ; then
   x=0                       # go back to first field
  fi
 done

 return 0
}

savefile()
{
 rm $FN 2> /dev/null         # remove any existing file
 echo "Writing file $FN ..."
 y=0
 while [ $y -lt $sizeofarray ]
 do
  echo "$y - '${array[$y]}'"            # display to screen
  echo "${array[$y]}" >> "$FN"          # write to file
  let y++
 done
 echo "File written."
 return 0
}

getfile()
{
 x=0
 if [ -n "$FN" ] ; then      # check that file exists
  while IFS= read -r linevar # loop using read to put line into linevar
  do
   array[$x]="$linevar"
   let x++
  done < $FN                 # the file to use as input
 fi
 return 0
}

# Code starts here
if [ $# -ne 1 ] ; then
 echo "Usage: script6 file"
 echo " Reads existing file or creates new file and allows user to enter data"
 echo " into fields."
 exit 255
fi

FN=$1                        # filename (input and output)
sizeofarray=7                # number of array elements
checktermsize 25 80
rc=$?
if [ $rc -ne 0 ] ; then
 echo "Please size the terminal to 25x80 and try again."
 exit 1
fi

init                         # initialize the screen array
getfile                      # read in file if it exists
drawscreen                   # draw the screen
getdata                      # read in the data and put into the fields

exit 0

