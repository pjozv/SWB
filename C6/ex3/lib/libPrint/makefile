CC=g++
CFLAGS=-c -Wall
BINDIR:=bin
SRCDIR:=src
OBJDIR:=obj
DSTDIR:=..

all: build install

build: $(OBJDIR)/libPrint.o
	ar rvs $(BINDIR)/libPrint.a $<	

$(OBJDIR)/%.o: $(SRCDIR)/%.cpp %.h
	$(CC) $(CFLAGS) $< -o $@

install: $(DSTDIR)/libPrint.a 

$(DSTDIR)/libPrint.a: $(BINDIR)/libPrint.a
	cp $< $@

clean:
	rm -f obj/* bin/* ../*.a

