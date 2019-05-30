# Main makefile
CC=g++
CFLAGS=-c -Wall
SRCDIR=src/
OBJDIR=obj/
OBJECTS=cw7_dom1.cpp.o sortowanie.o min.o max.o avg.o
MACROS=src/macros.h

main: $(OBJECTS)
	$(CC) $(OBJDIR)cw7_dom1.cpp.o $(OBJDIR)sortowanie.o $(OBJDIR)min.o $(OBJDIR)max.o $(OBJDIR)avg.o -o $@

cw7_dom1.cpp.o: $(SRCDIR)cw7_dom1.cpp
	$(CC) $(CFLAGS) $< -o $(OBJDIR)$@

sortowanie.o:  $(SRCDIR)sortowanie.cpp  $(SRCDIR)sortowanie.h $(MACROS)
	$(CC) $(CFLAGS) $< -o $(OBJDIR)$@

min.o: $(SRCDIR)min.cpp $(SRCDIR)min.h $(MACROS)
	$(CC) $(CFLAGS) $< -o $(OBJDIR)$@

max.o: $(SRCDIR)max.cpp $(SRCDIR)max.h $(MACROS)
	$(CC) $(CFLAGS) $< -o $(OBJDIR)$@

avg.o: $(SRCDIR)avg.cpp $(SRCDIR)avg.h $(MACROS)
	$(CC) $(CFLAGS) $< -o $(OBJDIR)$@


.PHONY: clean
clean:
	rm -f main
	rm -f obj/*
