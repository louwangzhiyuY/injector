INJECTOR_OBJS = cpudep.o elf.o injector.o ptrace.o util.o
CFLAGS = -Wall -fPIC

all: libinjector.so libinjector.a

libinjector.so: $(INJECTOR_OBJS)
	$(CC) -shared -o libinjector.so $(INJECTOR_OBJS)

libinjector.a: $(INJECTOR_OBJS)
	$(AR) rcs libinjector.a $(INJECTOR_OBJS)

cpudep.o: cpudep.c injector_internal.h ../include/injector.h
elf.o: elf.c injector_internal.h ../include/injector.h
injector.o: injector.c injector_internal.h ../include/injector.h
ptrace.o: ptrace.c injector_internal.h ../include/injector.h
util.o: util.c injector_internal.h ../include/injector.h

clean:
	$(RM) libinjector.so libinjector.a $(INJECTOR_OBJS)
