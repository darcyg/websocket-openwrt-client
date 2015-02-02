CC = gcc
CFLAGS = -Wall
OBJS = websocket_client.o

all: websocket_client

%.o: %.c
	$(CC) $(CFLAGS) -c -o $@ $< $(LDFLAGS)

fbtest: $(OBJS)
	$(CC) -o $@ $(OBJS) $(LDFLAGS)

clean:
	rm -f rbcfg *.o
