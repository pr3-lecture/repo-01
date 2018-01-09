CC = gcc
ENCRYPT_NAME = encrypt
DECRYPT_NAME = decrypt
TEST_NAME = test
CCFLAGS = -Wall -Werror -pedantic -O3
CFILES = run.c crypto.c
HFILES = run.h crypto.h
CTESTFILES = crypto.c testCrypto.c

.PHONY: all clean debug test

prog: testCrypto.o
		gcc -o prog testCrypto.o

testCrypto.o: testCrypto.c
		gcc -c testCrypto.c

all: encryption decryption
debug: CCFLAGS += -g
debug: encryption decryption

clean:
	rm -f *.o *.exe

test: $(CTESTFILES)
	$(CC) -o $(TEST_NAME) $^

encryption: $(CFILES)
	$(CC) -o $(ENCRYPT_NAME) $(CCFLAGS) $^

decryption: $(CFILES)
	$(CC) -o $(DECRYPT_NAME) $(CCFLAGS) $^
