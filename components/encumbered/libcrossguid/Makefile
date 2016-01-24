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
COMPONENT_NAME= libcrossguid
COMPONENT_VERSION= 1.0.0
COMPONENT_FMRI = library/libcrossguid
COMPONENT_CLASSIFICATION = System/Libraries
COMPONENT_SUMMARY= CrossGuid is a minimal, cross platform, C++ GUID library.
COMPONENT_SRC= crossguid-8f399e8bd4
COMPONENT_ARCHIVE= crossguid-8f399e8bd4.tar.gz
COMPONENT_ARCHIVE_HASH= \
  sha256:3d77d09a5df0de510aeeb940df4cb534787ddff3bb1828779753f5dfa1229d10
COMPONENT_ARCHIVE_URL= \
  http://ftp.heanet.ie/mirrors/xbmc/build-deps/sources/crossguid-8f399e8bd4.tar.gz
COMPONENT_PROJECT_URL = https://github.com/graeme-hill/crossguid/
COMPONENT_LICENSE = MIT
COMPONENT_LICENSE_FILE = LICENSE


include $(WS_TOP)/make-rules/encumbered.mk
include $(WS_TOP)/make-rules/prep.mk
include $(WS_TOP)/make-rules/configure.mk
include $(WS_TOP)/make-rules/ips.mk

COMPONENT_BUILD_ENV  += CFLAGS+=" $(CFLAGS) -DGUID_LIBUUID "

COMPONENT_PRE_CONFIGURE_ACTION= \
            ( cd  $(COMPONENT_DIR)/$(COMPONENT_SRC) && \
		$(TOUCH)  INSTALL NEWS README AUTHORS ChangeLog && \
		libtoolize && aclocal && autoconf && automake --add-missing )
COMPONENT_POST_INSTALL_ACTION= \
        ($(GSED) -e "s:%LIBDIR%:$(CONFIGURE_LIBDIR.$(BITS)):g" -e "s:%VERSION%:$(COMPONENT_VERSION):g" $(COMPONENT_DIR)/$(COMPONENT_SRC)/crossguid.pc > $(BUILD_DIR)/crossguid.pc.$(BITS)  )

build: $(BUILD_32_and_64)

install: $(INSTALL_32_and_64)

test: $(NO_TESTS)

