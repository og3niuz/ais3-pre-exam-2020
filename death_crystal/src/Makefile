CC		= gcc
CCFLAGS		= -Wl,-z,relro,-z,now -s

PROGS	= death_crystal
PREFIX	= AIS3

all: $(PROGS)

%: %.c
	$(CC) -o $(OUTDIR)$@ $(CCFLAGS) $<

.PHONY: clean sig

clean:
	rm -f *~ $(PROGS)

sig: $(PROGS)
	mv $(PROGS) $(PROGS)-`sha256sum $(PROGS) | awk '{print $$1}'`
