CC=gcc
CFLAGS=-O2 -Wall -Wextra -pedantic

all: wav2c

wav2c: main.o wavdata.o
	$(CC) main.o wavdata.o -o wav2c

wav2c.o: main.c wavdata.h
	$(CC) -c main.c $(CFLAGS)

wavdata.o: wavdata.c wavdata.h
	$(CC) -c wavdata.c $(CFLAGS)

clean:
	@rm -f *.o wav2c
