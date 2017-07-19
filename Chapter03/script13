#!/bin/sh
#
echo cbS by Lewis 5/4/2017

if [ $# -eq 0 ] ; then
 echo "Usage: cbS filename(s) "
 echo " Will make a numbered backup of the files(s) given."
 echo " Files must be in the current directory."
 exit 255
fi

rc=0                         # return code, default is no error
for fn in $*                 # for each filename given on the command line
do
 if [ ! -f $fn ] ; then      # if not found
  echo "File $fn not found."
  rc=1                       # one or more files were not found
 else
  cnt=1                      # file counter
  loop1=0                    # loop flag
  while [ $loop1 -eq 0 ]
  do
   tmp=bak-$cnt.$fn
   if [ ! -f $tmp ] ; then
     cp $fn $tmp
     echo "File "$tmp" created."
     loop1=1                 # end the inner loop
   else
     let cnt++               # try the next one
   fi
  done
 fi
done

exit $rc                     # exit with return code

