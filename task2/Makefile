CC = gcc
SRC = src1.o src2.o src3.o
MNE = main.c

main: $(MNE) $(SRC)
	$(CC) -o $@ $^

ifndef MAKE_OPTION  # use -> "unset MAKE_OPTION" to make with -f

src1.o: make1.mk src1.c
	make -f $<

src2.o: make2.mk src2.c
	make -f $<

src3.o: make3.mk src3.c
	make -f $<

endif

ifdef MAKE_OPTION # use -> "export MAKE_OPTION=1" to make with include

include make1.mk

include make2.mk

include make3.mk

endif

.PHONY: clean

clean:
	rm *.o main

