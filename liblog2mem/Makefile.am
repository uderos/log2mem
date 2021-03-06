## Makefile.am -- Process this file with automake to produce Makefile.in
##
## This program is free software; you can redistribute it and/or modify
## it under the terms of the GNU General Public License as published by
## the Free Software Foundation; either version 2, or (at your option)
## any later version.
##
## This program is distributed in the hope that it will be useful,
## but WITHOUT ANY WARRANTY; without even the implied warranty of
## MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
## GNU General Public License for more details.
##
## You should have received a copy of the GNU General Public License
## along with this program; if not, write to the Free Software
## Foundation, Inc., 675 Mass Ave, Cambridge, MA 02139, USA.

# NOTE: AM_CPPFLAGS is ignored in preference to a per-executable (or
# per-library) _CPPFLAGS variable if it is defined
#
# NOTE: it is not good practice to add "-Wall" and "-03" etc here.  Those
# choices should be made by the user when they invoke the configure script.
#AM_CFLAGS =  -Wall -g3 -ggdb -O0


AM_LFLAGS=-pthread

# Primary defination of our shared library to be created.  Notice the
# _LTLIBRARIES key: automake is looking specifically for this pattern and then
# generating make rules which will invoke libtool.
#
# The "lib_" prefix indicates that the named products are to be installed in
# the $(libdir) directory. If we want to build a library that does not get
# installed, then we should use the prefix "noinst_".
lib_LTLIBRARIES = liblog2mem.la

# The "include_" prefix includes a list of headers to be installed.  The
# "nobase_" additional prefix means the directory names are copied too.
nobase_include_HEADERS = log2mem/log2mem.h

# List the sources for an individual library
liblog2mem_la_SOURCES = log2mem.c

# Include compile and link flags for an individual library.
#
# Note that to link against a static library which is part of this project, we
# should refers to them with relative paths inside the build directory, for
# example, "../common/libcommon.la"
#
# Note also, because we are using libtool, we should only refer to other
# libtool libraries (*.la)
#
# <library_LIBADD> : extras libtool objects to add to library
#
#libexio_la_CPPFLAGS =
#libexio_la_LIBADD = ../libcpp11/libcpp11.la

# Note: version info for shared libraries is three number system, where the
# numbers represent: CURRENT : REVISION : AGE
#
# - CURRENT:  library version. Only change if API has changed.
# - REVISION: revision of current version. Incr. base on internal changes.
# - AGE: indicates compatibilty with previous version of the shlib.
#
liblog2mem_la_LDFLAGS = -version-info 1:1:0