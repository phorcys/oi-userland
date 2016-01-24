#
# This file and its contents are supplied under the terms of the
# Common Development and Distribution License ("CDDL"), version 1.0.
# You may only use this file in accordance with the terms of version
# 1.0 of the CDDL.
#
# A full copy of the text of the CDDL should have accompanied this
# source.  A copy of the CDDL is also available via the Internet at
# http://www.illumos.org/license/CDDL.
#

#
# Copyright 2016 phorcys@126.com.  All rights reserved.
#

include ../../../make-rules/shared-macros.mk

COMPONENT_NAME= kodi
COMPONENT_VERSION= 16.0
COMPONENT_FMRI = media/kodi
COMPONENT_CLASSIFICATION = Applications/Sound and Video
COMPONENT_SUMMARY= Kodi (formerly known as XBMC) is an award-winning free and open source (GPL) software media center for playing videos, music, pictures, games, and more. 
COMPONENT_SRC= xbmc-16.0rc1-Jarvis
COMPONENT_ARCHIVE= 16.0rc1-Jarvis.tar.gz
COMPONENT_ARCHIVE_HASH= \
  sha256:4edaec77b53da73762eb75d8e502df2cd2bba82d622d0a279cd7c0df1f7f7e18
COMPONENT_ARCHIVE_URL= \
  https://github.com/xbmc/xbmc/archive/16.0rc1-Jarvis.tar.gz
COMPONENT_PROJECT_URL = http://kodi.tv/
COMPONENT_LICENSE = GPLv2
COMPONENT_LICENSE_FILE = LICENSE.GPL 

include $(WS_TOP)/make-rules/encumbered.mk
include $(WS_TOP)/make-rules/prep.mk
include $(WS_TOP)/make-rules/configure.mk
include $(WS_TOP)/make-rules/ips.mk

CONFIGURE_ENV += PATH="/usr/gnu/bin:$(PATH):/usr/mariadb/5.5/bin" CFLAGS=" $(CFLAGS) -I/usr/sfw/include " LDFLAGS="$(LDFLAGS) -L/usr/lib -L/usr/sfw/lib  -luuid"
CONFIGURE_OPTIONS += --disable-ssh UUID_LIBS="-luuid" 

CONFIGURE_SCRIPT="$(@D)/configure"
COMPONENT_PREP_ACTION= \
	 (cd   $(@D) && \
	JSON_BUILDER=tools/depends/native/JsonSchemaBuilder/bin/JsonSchemaBuilder  CC=gcc Cxx=g++ MAKE=gmake bash bootstrap )
COMPONENT_PRE_CONFIGURE_ACTION= \
	($(RM) -r $(@D) && cp -a $(SOURCE_DIR) $(@D) ) 
COMPONENT_BUILD_ENV += MAKE=gmake PATH="/usr/gnu/bin:$(PATH):/usr/mariadb/5.5/bin" CFLAGS=" $(CFLAGS) -I/usr/sfw/include " LDFLAGS="$(LDFLAGS) -L/usr/lib -L/usr/sfw/lib -luuid"

COMPONENT_INSTALL_ENV +=  PATH="/usr/gnu/bin:$(PATH):/usr/mariadb/5.5/bin"

build: $(BUILD_32)

install: $(INSTALL_32)

test: $(NO_TESTS)

