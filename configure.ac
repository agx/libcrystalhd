dnl Process this file with autoconf to produce a configure script.

dnl Copyright (C) 2013 godiug.net
dnl
dnl This library is free software; you can redistribute it and/or
dnl modify it under the terms of the GNU Lesser General Public
dnl License as published by the Free Software Foundation; either
dnl version 2.1 of the License.
dnl
dnl This library is distributed in the hope that it will be useful,
dnl but WITHOUT ANY WARRANTY; without even the implied warranty of
dnl MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU
dnl Lesser General Public License for more details.
dnl
dnl You should have received a copy of the GNU Lesser General Public
dnl License along with this library.  If not, see
dnl <http://www.gnu.org/licenses/>.

AC_INIT([libcrystalhd], [0.0.0], [agx@sigxcpu.org], [], [])
AC_CONFIG_SRCDIR([src/libcrystalhd_if.h])
AC_CONFIG_AUX_DIR([build-aux])
AC_CONFIG_MACRO_DIR([m4])
AC_CONFIG_HEADERS([config.h])
dnl Make automake keep quiet about wildcards & other GNUmake-isms; also keep
dnl quiet about the fact that we intentionally cater to automake 1.9
AM_INIT_AUTOMAKE([-Wno-portability -Wno-obsolete tar-ustar subdir-objects])

LIBCRYSTALHD_VERSION_INFO="6:3:0"
AC_SUBST([LIBCRYSTALHD_VERSION_INFO])

dnl Checks for C compiler.
AC_PROG_CC
AC_PROG_INSTALL
AC_PROG_CPP

m4_ifndef([LT_INIT], [
  AM_PROG_LIBTOOL
], [
  LT_INIT([shared disable-static])
])
AM_PROG_CC_C_O
AM_PROG_LD

PKG_PROG_PKG_CONFIG

AC_CONFIG_FILES([Makefile
    src/Makefile
    include/Makefile
    include/link/Makefile
    libcrystalhd.pc])
AC_OUTPUT
