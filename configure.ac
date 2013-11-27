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

AC_INIT([libcrystalhd], [0.0.1], [agx@sigxcpu.org], [], [])
AC_CONFIG_SRCDIR([src/libcrystalhd_if.h])
AC_CONFIG_AUX_DIR([build-aux])
AC_CONFIG_MACRO_DIR([m4])
AC_CONFIG_HEADERS([config.h])
dnl Make automake keep quiet about wildcards & other GNUmake-isms; also keep
dnl quiet about the fact that we intentionally cater to automake 1.9
AM_INIT_AUTOMAKE([-Wno-portability -Wno-obsolete tar-ustar subdir-objects])

LIBCRYSTALHD_MAJOR_VERSION=`echo $VERSION | awk -F. '{print $1}'`
LIBCRYSTALHD_MINOR_VERSION=`echo $VERSION | awk -F. '{print $2}'`
LIBCRYSTALHD_MICRO_VERSION=`echo $VERSION | awk -F. '{print $3}'`
LIBCRYSTALHD_VERSION=$LIBCRYSTALHD_MAJOR_VERSION.$LIBCRYSTALHD_MINOR_VERSION.$LIBCRYSTALHD_MICRO_VERSION$LIBCRYSTALHD_MICRO_VERSION_SUFFIX
LIBCRYSTALHD_VERSION_NUMBER=`expr $LIBCRYSTALHD_MAJOR_VERSION \* 1000000 + $LIBCRYSTALHD_MINOR_VERSION \* 1000 + $LIBCRYSTALHD_MICRO_VERSION`

# In libtool terminology we need to figure out:
#
# CURRENT
#     The most recent interface number that this library implements.
#
# REVISION
#     The implementation number of the CURRENT interface.
#
# AGE
#     The difference between the newest and oldest interfaces that this
#     library implements.
#
# In other words, the library implements all the interface numbers
# in the range from number `CURRENT - AGE' to `CURRENT'.
#
# Libtool assigns the soname version from `CURRENT - AGE', and we
# don't want that to ever change in libcrystalhd, unless we need
# to break ABI for some reason.
#
# The C++ versions used up to 6 so we bump the soname to 7 once.
#
# We would, however, like the libcrystalhd version number reflected
# in the so version'd symlinks, and this is based on AGE.REVISION
# eg  libcrystalhd.so.7.AGE.REVISION
#
# Assuming we do ever want to break soname version, this can
# toggled. But seriously, don't ever touch this.
LIBCRYSTALHD_SONUM=7
AGE=`expr $LIBCRYSTALHD_MAJOR_VERSION '*' 1000 + $LIBCRYSTALHD_MINOR_VERSION`
REVISION=$LIBCRYSTALHD_MICRO_VERSION
CURRENT=`expr $LIBCRYSTALHD_SONUM + $AGE`
LIBCRYSTALHD_VERSION_INFO=$CURRENT:$REVISION:$AGE
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
