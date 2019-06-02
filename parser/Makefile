all: c99

CFLAGS=-g

c99.tab.c c99.tab.h:	c99.y
	bison -d c99.y

lex.yy.c: c99.l c99.tab.h
	flex c99.l

c99: lex.yy.c c99.tab.c c99.tab.h
	gcc $(CFLAGS) -o $@ c99.tab.c lex.yy.c

clean:
	rm -rf c99 c99.tab.c lex.yy.c c99.tab.h
