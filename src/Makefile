
EXEC=rastertotpcl
CFLAGS=/usr/lib/libcups.2.dylib /usr/lib/libcupsimage.2.dylib
PPDPATH=/private/etc/cups/ppd
EXECPATH=/usr/libexec/cups/filter
 
all: rastertotpcl ppd

.PHONY: ppd clean install uninstall

$(EXEC): rastertotpcl.c

ppd:
	ppdc tectpcl2.drv

install:
	if test ! -d $(PPDPATH)/$(EXEC); then mkdir $(PPDPATH)/$(EXEC); fi
	cp ppd/* $(PPDPATH)/$(EXEC)
	cp $(EXEC) $(EXECPATH)/
	

uninstall:
	rm -rf $(PPDPATH)/$(EXEC)
	rm -f $(EXECPATH)/$(EXEC)


clean:
	rm -f rastertotpcl
	rm -rf ppd
