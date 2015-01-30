CC = gcc
CFLAGS = -Wall
OBJS = websocket_test.o

all: websocket_test

%.o: %.c
	$(CC) $(CFLAGS) -c -o $@ $< $(LDFLAGS)

fbtest: $(OBJS)
	$(CC) -o $@ $(OBJS) $(LDFLAGS)

clean:
	rm -f rbcfg *.o
