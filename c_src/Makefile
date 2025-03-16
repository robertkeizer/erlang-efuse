all: efuse

efuse.o: efuse.c efuse_defs.h
	gcc -c -Wall -std=gnu99 -D_FILE_OFFSET_BITS=64 -I/usr/include -shared -g -Wall -fPIC -MMD  -I"/usr/local/lib/erlang26/lib/erl_interface-5.5.1/include" -I"/usr/local/lib/erlang26/erts-14.2.5.3/include" efuse.c -o efuse.o

efuse: efuse.o
	gcc efuse.o -L/usr/local/lib/erlang26/lib/erl_interface-5.5.1/lib -lei -pthread -lfuse -o efuse
	cp efuse ../priv/

clean:
	rm -f efuse.o efuse
