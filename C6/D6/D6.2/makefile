# Main makefile
CC:=g++
CFLAGS:=-c -Wall
OBJDIR:=obj
BINDIR:=bin
SRCDIR:=src
OUTDIR:=out

LIBBASEDIR:=lib
# Thanks to the structure of this makefile, we just need to add lib names in the line below; All the rest will be handled by subsequent makefiles and scripts.
LIBDIRS:=swbmath
LIBS:= $(addprefix $(LIBBASEDIR)/, $(LIBDIRS))
LIBS:= $(addsuffix .a, $(LIBS))

#LIBS=lib/swbmath.a

all: build install

install: $(OUTDIR)/main

$(OUTDIR)/main: $(OBJDIR)/main.o |$(OUTDIR)
	$(CC) $(FLAGS) -d$(LIBS) $< -o $@

#Definicje dla preprocesora ustawiane są zazwyczaj za pomocą flagi -Dnazwa_definicji, przekazanej do kompilatora; w ten sposób włącz makra z pliku libPrint.h??

build: $(BINDIR)/cw7_dom1

$(BINDIR)/cw7_dom1: $(OBJDIR)/cw7_dom1.o $(LIBS) |$(BINDIR)
	$(CC) $^ -o $@

#Before creating any objects (| - order-only prequisities - items on the right of | will be checked before items on the left), be sure that dirs are created.
$(OBJDIR)/%.o: $(SRCDIR)/%.cpp | $(OBJDIR) $(BINDIR)
	$(CC) $(CFLAGS) $< -o $@

$(BINDIR):
	mkdir -p $(BINDIR)

$(OBJDIR):
	mkdir -p $(OBJDIR)

$(OUTDIR):
	mkdir -p $(OUTDIR)

$(LIBBASEDIR)/%.a:	
	@$(MAKE) -C $(LIBBASEDIR)/$*/

.PHONY:clean

clean:
	rm -f -r obj/ out/ bin/
#Run clean for every makefile in subdirectories. && is needed to interpret multiple commands in one line, true - to end the command with "&& true".
	@$(foreach path,$(LIBDIRS), $(MAKE) clean -C $(LIBBASEDIR)/$(path) &&) true 
