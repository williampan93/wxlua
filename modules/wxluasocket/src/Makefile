# File:		Makefile
# Author:	John Labenski, J Winwood
# Created:	2002
# Updated:
# Copyright: (c) 2002 Lomtick Software. All rights reserved.
#
# Makefile for wxLua library using gmake

# ----------------------------------------------------------------------------
# Set path to root of wxLua
WXLUA_DIR = ../../..

# ----------------------------------------------------------------------------
# Include wxLua settings using wx-config for wxWidgets parameters

include $(WXLUA_DIR)/build/Makefile_wx-config.in

# ----------------------------------------------------------------------------

WXLUA_TARGET_LIBNAME = lib$(WXLUASOCKET_LIB)

# ----------------------------------------------------------------------------

HEADERS = \
	../include/wxldserv.h \
	../include/wxldtarg.h \
	../include/wxlsock.h \
	../include/wxluasocket.h

SOURCES = \
	wxldserv.cpp \
	wxldtarg.cpp \
	wxlsock.cpp \
	wxluasocket_bind.cpp

OBJECTS=$(SOURCES:.cpp=.o)
DEPFILES=$(OBJECTS:.o=.d)

# ----------------------------------------------------------------------------

.cpp.o:
	$(CXX) -c $(CXXFLAGS) $(APPEXTRADEFS) -o $@ $<

all: $(WXLUA_TARGET_LIB_STATIC) $(WXLUA_TARGET_LIB_SHARED)

clean: cleanlib

# ----------------------------------------------------------------------------
# Include wxLua targets using wx-config for wxWidgets parameters

include $(WXLUA_DIR)/build/Makefile_wx-config_targets.in

-include $(DEPFILES)
