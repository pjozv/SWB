# Main makefile

all: double_free_gdb double_free_lite.o strip double_free_lite clean.o

double_free_gdb: double_free.c
	g++ -g double_free.c -o double_free_gdb

double_free_lite: double_free_lite.o
	g++ double_free_lite.o -o double_free_lite

double_free_lite.o: double_free.c
	g++ -c double_free.c -o double_free_lite.o

strip: double_free_lite.o
	strip -g double_free_lite.o

clean.o:
	rm -f *.o

clean:
	rm -f double_free_lite double_free_gdb core
