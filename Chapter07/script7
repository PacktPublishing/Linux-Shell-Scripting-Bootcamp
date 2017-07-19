#!/bin/sh
#
# 6/2/2017
#
echo "Chapter 7 - Script 7"

if [ $# -ne 3 ] ; then
 echo "Usage: script7 -e|-d infile outfile"
 echo " Uses openssl to encrypt files."
 echo " -e to encrypt"
 echo " -d to decrypt"
 exit 255
fi

PARM=$1
INFILE=$2
OUTFILE=$3

if [ ! -f $INFILE ] ; then
 echo "Input file $INFILE does not exist."
 exit 100
fi

if [ "$PARM" = "-e" ] ; then
 echo "Encrypting"
 openssl enc -aes-256-cbc -in $INFILE -out $OUTFILE
elif [ "$PARM" = "-d" ] ; then
 echo "Decrypting"
 openssl enc -aes-256-cbc -d -in $INFILE -out $OUTFILE
else
 echo "Please specify either -e or -d."
 exit 101
fi

ls -la $OUTFILE

echo "End of script7"
exit 0

