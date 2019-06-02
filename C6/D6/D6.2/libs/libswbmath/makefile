CC=g++
CFLAGS=-c -Wall
SRCDIR:=src/
OBJDIR:=obj/
MACROS=macros.h
DSTDIR:=../
OBJ := $(patsubst $(SRCDIR)%.cpp,$(OBJDIR)%.o,$(wildcard $(SRCDIR)*.cpp))

all: build install

build: swbmath.a

swbmath.a: $(OBJ)
	ar rcs $@ $^
#$(CC) -c -Wall  $^ -o $@

$(OBJDIR)%.o: $(SRCDIR)%.cpp  $(SRCDIR)%.h $(SRCDIR)$(MACROS) | $(OBJDIR)
	$(CC) $(CFLAGS) $< -o $@

install: $(DSTDIR)swbmath.a

$(DSTDIR)swbmath.a: swbmath.a
	cp -p $< $@

$(OBJDIR):
	mkdir -p $(OBJDIR)

.PHONY: clean
clean:
	rm -f -r obj/
	rm -f *.a ../*.a

