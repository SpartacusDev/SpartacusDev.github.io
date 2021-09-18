# Found this Makefile in Litten's server, sent by Bingner (not to me, but I saw it), so thanks Bingner

OBJS:=Packages Packages.bz2 Packages.xz

.PHONY: clean objs all

all: objs

clean:
	rm -f $(OBJS)

objs: $(OBJS)

Packages: $(wildcard debs/*.deb)
	dpkg-scanpackages -h sha1,sha256 -m debs /dev/null > Packages 2>/dev/null

%.bz2: %
	bzip2 < $^ > $@

%.xz: %
	xz < $^ > $@