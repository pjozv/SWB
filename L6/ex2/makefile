# Main makefile
CC=g++
CFLAGS=-c -Wall
ODIR=obj/
BDIR=bin/

main: main.o dbgPrint.o
	$(CC) $(ODIR)main.o $(ODIR)dbgPrint.o -o $(BDIR)$@

main.o: main.cpp main.h
	$(CC) $(CFLAGS) $< -o $(ODIR)$@

dbgPrint.o: dbgPrint.cpp dbgPrint.h
	$(CC) $(CFLAGS) $< -o $(ODIR)$@

.PHONY: clean
clean:
	rm -f *.o main
	rm -f obj/*
	rm -f bin/*
