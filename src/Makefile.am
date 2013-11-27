LIBCRYSTALHD_VERSION_INFO = @LIBCRYSTALHD_VERSION_INFO@

EXTRA_DIST = libcrystalhd.sym

AM_CPPFLAGS = \
	-I$(top_srcdir)/include \
	-I$(top_srcdir)/include/link \
	-O2 -Wall -fstrict-aliasing -msse2

lib_LTLIBRARIES = libcrystalhd.la
libcrystalhd_la_LDFLAGS = \
	-Wl,--version-script=$(srcdir)/libcrystalhd.sym \
	-version-info $(LIBCRYSTALHD_VERSION_INFO)
	-pthread

libcrystalhd_la_SOURCES = \
	libcrystalhd_fwcmds.c \
	libcrystalhd_fwdiag_if.c \
	libcrystalhd_fwload_if.c \
	libcrystalhd_if.c \
	libcrystalhd_int_if.c \
	libcrystalhd_parser.c \
	libcrystalhd_priv.c \
	$(NULL)

libcrystalhdincludedir=$(includedir)/libcrystalhd
libcrystalhdinclude_HEADERS = \
	libcrystalhd_if.h \
	$(top_srcdir)/include/bc_dts_defs.h \
	$(top_srcdir)/include/bc_dts_types.h \
	$(top_srcdir)/include/libcrystalhd_version.h \
	$(NULL)

noinst_HEADERS = \
	libcrystalhd_fwcmds.h \
	libcrystalhd_fwdiag_if.h \
	libcrystalhd_fwload_if.h \
	libcrystalhd_int_if.h \
	libcrystalhd_parser.h \
	libcrystalhd_priv.h \
	$(NULL)

libcrystalhd_la_CPPFLAGS = $(AM_CPPFLAGS)
