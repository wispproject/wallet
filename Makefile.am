ACLOCAL_AMFLAGS = -I m4

if OS_WINDOWS_CROSSCOMPILE
# for leveldb
AM_MAKEFLAGS = TARGET_OS=OS_WINDOWS_CROSSCOMPILE
endif

export CC CXX AR LD
SUBDIRS = tor db4.8/build_unix leveldb src

Wisp.app: all-am
	mkdir -p Wisp.app/Contents/{MacOS,Resources}
	cp Info.plist Wisp.app/Contents
	cp wisp.icns Wisp.app/Contents/Resources
	cp src/wisp Wisp.app/Contents/MacOS/Wisp
	echo "APPL????" > Wisp.app/Contents/PkgInfo
	@MACDEPLOYQT@ Wisp.app @MACDEPLOYQT_LIBPATH@

.PHONY: Wisp.app
