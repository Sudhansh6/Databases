CC=cc
CFLAGS = -g
OBJS=tbl.o codec.o util.o ../pflayer/pflayer.a ../amlayer/amlayer.a

all: loaddb dumpdb

loaddb : loaddb.o $(OBJS) 
	$(CC) $(CFLAGS) -o loaddb loaddb.o $(OBJS)

dumpdb : dumpdb.o $(OBJS) 
	$(CC) $(CFLAGS) -o dumpdb dumpdb.o $(OBJS)

loaddb.o : loaddb.c tbl.h codec.h util.h
	$(CC) -c $(CFLAGS) loaddb.c

tbl.o : tbl.c tbl.h
	$(CC) -c $(CFLAGS) tbl.c

codec.o: codec.h codec.c
	$(CC) -c $(CFLAGS) codec.c

util.o: util.h util.c tbl.h
	$(CC) -c $(CFLAGS) util.c

clean:
	rm  -rf *.o *.a a.out* *~ data.db* *db
