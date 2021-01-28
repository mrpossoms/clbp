include ../vars.mk
INC+=-I../inc
LIB+=-L../lib/$(TARGET)
LINK+=-l$(PROJECT)

TESTS=$(patsubst %.c,bin/%,$(wildcard *.c))

bin:
	mkdir bin

bin/%: %.c bin
	$(CC) $(CFLAGS) $(LIB) $(INC) $(LIBS) $< -o $@ $(LINK)

.PHONY: test clean 
test: $(TESTS)
	@./.test-runner.py

clean:
	rm -rf bin/

../lib/$(TARGET)/lib$(PROJECT).a:
	$(MAKE) -C .. static

