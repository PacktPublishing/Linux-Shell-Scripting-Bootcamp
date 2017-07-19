#!/bin/sh
tput clear
echo runbackup1 5/23/2017 A
cd $LDIR/backup
DR=/wd1                      # symbolic link to external drive
# Insure backup drive is mounted
file $DR | grep broken
a=$?
if [ $a -ne 1  ] ; then
 echo "ERROR: USB drive $DR is not mounted!!!!!!!!!!!!!!"
 beep
 exit 255
fi
while [ true ]
do
 # Run at 3 am
 date | grep -q 03:00:
 rc=$?
 if [ $rc -eq 0 ] ; then
  echo Running backup1 ...
  backup1 | tee /temp/mainlogs/mainlog`date '+%Y%m%d'`.txt
 fi
 sleep 60
done

