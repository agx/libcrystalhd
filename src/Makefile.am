AM_CPPFLAGS = \
	-I$(top_srcdir)/include \
	-I$(top_srcdir)/include/link \
	-O2 -Wall -fstrict-aliasing -msse2

lib_LTLIBRARIES = libcrystalhd.la
libcrystalhd_la_LDFLAGS = \
        -version-info 9:6:3 \
	-pthread

libcrystalhd_la_SOURCES = \
	libcrystalhd_fwcmds.cpp \
	libcrystalhd_fwdiag_if.cpp \
	libcrystalhd_fwload_if.cpp \
	libcrystalhd_if.cpp \
	libcrystalhd_int_if.cpp \
	libcrystalhd_parser.cpp \
	libcrystalhd_priv.cpp \
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
	$(top_srcdir)/include/7411d.h \
	$(top_srcdir)/include/bc_decoder_regs.h \
	$(top_srcdir)/include/bc_dts_glob_lnx.h \
	$(top_srcdir)/include/vdec_info.h \
	$(top_srcdir)/include/link/bc_defines.h \
	$(top_srcdir)/include/link/bcm_70012_regs.h \
	$(NULL)

libcrystalhd_la_CPPFLAGS = $(AM_CPPFLAGS)
