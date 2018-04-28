CFLAGS?=-Wall -g -D_GNU_SOURCE
LIBS=list.o process_iterator.o process_group.o

all: cpulimit 

cpulimit: cpulimit.c $(LIBS)
	$(CC) -o cpulimit cpulimit.c $(LIBS) $(CFLAGS)

process_iterator.o: process_iterator.c process_iterator.h
	$(CC) -c process_iterator.c $(CFLAGS)

list.o: list.c list.h
	$(CC) -c list.c $(CFLAGS)

process_group.o: process_group.c process_group.h process_iterator.o list.o
	$(CC) -c process_group.c $(CFLAGS)

.PHONY:
	clean all
clean:
	rm -f *~ *.o $(TARGETS)

