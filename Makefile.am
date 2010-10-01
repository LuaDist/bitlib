## Process this file with automake to produce Makefile.in

ACLOCAL_AMFLAGS = -I m4

AM_CPPFLAGS = $(LUA_INCLUDE)
LDADD = $(LUA_LIB)

lualib_LTLIBRARIES = bit.la

bit_la_SOURCES = lbitlib.c bit_limits.h
bit_la_LDFLAGS = -module

EXTRA_DIST = test.lua find_limits.lua

BUILT_SOURCES = bit_limits.h

CLEAN_FILES = $(BUILT_SOURCES)

bit_limits.h: find_limits.lua
	LUA_INIT= $(LUA) $(top_srcdir)/find_limits.lua > $(top_srcdir)/bit_limits.h

check-local:
	LUA_INIT= libtool --mode=execute -dlopen bit.la shake $(top_srcdir)/test.lua

release: distcheck
	cvs diff && \
	cvs tag rel-${REL} && \
	woger lua-l bitlib bitlib "release ${REL}" "library for bitwise operations" release-notes-${REL}
