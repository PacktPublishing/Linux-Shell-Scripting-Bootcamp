#!/bin/sh
#   Jim's backup program
#   Runs standalone
#   Copies to /data/backups first, then to USB backup drive
VER="File backup by Jim Lewis 5/27/2017 A"
TDIR=/data/backups
RUNDIR=$LDIR/backup
DR=/wd1
echo $VER
cd $RUNDIR
# Insure backup drive is mounted
file $DR | grep broken
a=$?
if [ "$a" != "1" ] ; then
 echo "ERROR: USB drive $DR is not mounted!!!!!!!!!!!!!!"
 beep
 exit 255
fi
date >> datelog.txt
date
echo "Removing files from $TDIR"
cd "$TDIR"
rc=$?
if [ $rc -ne 0 ] ; then
 echo "backup1: Error cannot change to $TDIR!"
 exit 250
fi
rm *.gz
echo "Backing up files to $TDIR"
X=`date '+%Y%m%d'`
cd /
tar cvzf "$TDIR/lewis$X.gz"  lewis
tar cvzf "$TDIR/temp$X.gz"   temp
tar cvzf "$TDIR/root$X.gz"   root
cd /home
tar cvzf "$TDIR/guest$X.gz" --exclude=Cache --exclude=.cache --exclude=.evolution --exclude=vmware --exclude=.thumbnails  --exclude=.gconf --exclude=.kde --exclude=.adobe  --exclude=.mozilla  --exclude=.gconf  --exclude=thunderbird  --exclude=.local --exclude=.macromedia  --exclude=.config   guest1
cd $RUNDIR
T=`cat filenum1`
BACKDIR=$DR/backups/$T
rm $BACKDIR/*.gz
cd "$TDIR"
cp *.gz $BACKDIR
echo $VER
cd $BACKDIR
pwd
ls -lah
cd $RUNDIR
let T++
if [ $T -gt 7 ] ; then
 T=1
fi
echo $T > filenum1

