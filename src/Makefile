# Copyright (c) 1991 Bell Communications Research, Inc. (Bellcore)
# 
# Permission to use, copy, modify, and distribute this material 
# for any purpose and without fee is hereby granted, provided 
# that the above copyright notice and this permission notice 
# appear in all copies, and that the name of Bellcore not be 
# used in advertising or publicity pertaining to this 
# material without the specific, prior written permission 
# of an authorized representative of Bellcore.  BELLCORE 
# MAKES NO REPRESENTATIONS ABOUT THE ACCURACY OR SUITABILITY 
# OF THIS MATERIAL FOR ANY PURPOSE.  IT IS PROVIDED "AS IS", 
# WITHOUT ANY EXPRESS OR IMPLIED WARRANTIES.
#

CC = gcc

CFLAGS = -I.  -DMSDOS

LDLIBS =

CONFIGDIR = .

LOCALCFLAGS= -I${CONFIGDIR} ${CFLAGS}

.c.o:
	rm -f $@
	$(CC) -c  $(LOCALCFLAGS) $*.c

all: metamail.exe mmencode.exe mailto.exe splitmail.exe

codes.o:  codes.c config.h

mailto.o: mailto.c config.h

metamail.o: metamail.c config.h

shared.o:  shared.c config.h

splitmail.o:  shared.c config.h

mmencode.exe: mmencode.o codes.o
	rm -f mmencode.exe
	$(CC) $(LOCALCFLAGS) -o mmencode.exe  mmencode.o  codes.o $(LDLIBS)

mailto.exe: mailto.o codes.o shared.o
	rm -f mailto.exe
	$(CC) $(LOCALCFLAGS) -o mailto.exe  mailto.o  codes.o shared.o -ltermcap $(LDLIBS)

splitmail.exe: splitmail.o shared.o
	rm -f splitmail.exe
	$(CC) $(LOCALCFLAGS) -o splitmail.exe  splitmail.o shared.o $(LDLIBS)

metamail.exe:  metamail.o codes.o uue.o shared.o putenv.o
	rm -f metamail.exe
	$(CC) $(LOCALCFLAGS) -o metamail.exe  metamail.o  putenv.o codes.o uue.o shared.o $(LDLIBS)

clean:
	-rm -f metamail.exe mmencode.exe mailto.exe splitmail.exe *.o *.BAK
