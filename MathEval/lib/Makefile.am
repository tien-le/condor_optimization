# Copyright (C) 1999, 2002, 2003, 2004  Free Software Foundation, Inc.
#
# This file is part of GNU libmatheval
#
# GNU libmatheval is free software; you can redistribute it and/or
# modify it under the terms of the GNU General Public License as
# published by the Free Software Foundation; either version 2, or (at
# your option) any later version.
#
# GNU libmatheval is distributed in the hope that it will be useful, but
# WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU
# General Public License for more details.
#
# You should have received a copy of the GNU General Public License
# along with program; see the file COPYING. If not, write to the Free
# Software Foundation, Inc., 59 Temple Place - Suite 330, Boston, MA
# 02111-1307, USA.

MAINTAINERCLEANFILES = Makefile.in parser.c parser.h scanner.c

EXTRA_DIST = parser.h

INCLUDES = -I$(top_builddir) -I$(top_srcdir)

lib_LTLIBRARIES = libmatheval.la

libmatheval_la_SOURCES = parser.y scanner.l error.c matheval.c	\
g77_interface.c node.c symbol_table.c xmalloc.c xmath.c

libmatheval_la_LDFLAGS = -version-info 1:0:0
libmatheval_la_LIBADD = -lfl -lm

include_HEADERS = matheval.h
noinst_HEADERS = common.h error.h node.h symbol_table.h xmalloc.h	\
xmath.h

AM_YFLAGS = -d

.PHONY: beauty

beauty:
	-for file in $$(ls *.c *.h); do indent $$file; done
	-rm -f *~ *.BAK
