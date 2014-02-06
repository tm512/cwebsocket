AUTOMAKE_OPTIONS = foreign

bin_PROGRAMS = websocket-client
websocket_client_SOURCES = src/utf8.h src/utf8.c src/cwebsocket.h src/cwebsocket.c src/main.c

#LDFLAGS = -L/usr/local/lib -lcrypto

if DEBUG
  AM_CFLAGS = -Wall -g3
else
  AM_CFLAGS = -Wall -03
endif

if THREADED
  AM_CFLAGS += -pthread -DTHREADED
  LDFLAGS += -lpthread
endif

if USESSL
  AM_CFLAGS += -DUSESSL
  LDFLAGS += -lssl
endif

clean:
	rm -rf autoscan.log config.h.in config.h config.cache configure install-sh aclocal.m4 autom4te.cache/ config.log config.status Debug/ depcomp .deps/ m4/ Makefile Makefile.in missing stamp-h1 *.o src/*.o *~ client server