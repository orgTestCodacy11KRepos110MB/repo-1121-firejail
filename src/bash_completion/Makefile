.PHONY: all
all: firejail.bash_completion

ROOT = ../..
-include $(ROOT)/config.mk

firejail.bash_completion: firejail.bash_completion.in $(ROOT)/config.mk
	gawk -f ../man/preproc.awk -- $(MANFLAGS) < $< > $@.tmp
	sed "s|_SYSCONFDIR_|$(sysconfdir)|" < $@.tmp > $@
	rm $@.tmp

.PHONY: clean
clean:
	rm -fr firejail.bash_completion

.PHONY: distclean
distclean: clean
