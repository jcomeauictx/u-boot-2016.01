CROSS_COMPILE := aarch64-linux-gnu-
ifeq ($(SHOWENV),)
 export CROSS_COMPILE
else
 export
endif
artik710: prerequisites .config
	$(MAKE) -f Makefile
.config:
	$(MAKE) -f Makefile artik710_raptor_defconfig
%:
	$(MAKE) -f Makefile $@
env:
ifeq ($(SHOWENV),)
	$(MAKE) SHOWENV=1 $@
else
	$@
endif
prerequisites:
	sudo apt update
	[ "$$(which dtc)" ] || sudo apt install device-tree-compiler
	[ "$$(which aarch64-linux-gnu-gcc)" ] || \
	 sudo apt install gcc-aarch64-linux-gnu
