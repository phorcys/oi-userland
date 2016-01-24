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

COMPONENT_NAME= mDNSResponder
COMPONENT_VERSION= 379.37
COMPONENT_FMRI = library/mDNSResponder
COMPONENT_CLASSIFICATION = System/Libraries
COMPONENT_SUMMARY= The mDNSResponder project is a component of Bonjour, Apple's ease-of-use IP networking initiative.
COMPONENT_SRC= $(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE= $(COMPONENT_SRC).tar.gz
COMPONENT_ARCHIVE_HASH= \
  sha256:befcf6d6c27dcfd683d34f1ee7a4f79c93110bc56c6c0ab50f18869f877935e0
COMPONENT_ARCHIVE_URL= \
  http://mirrors.kodi.tv/build-deps/sources/mDNSResponder-379.37.tar.gz
COMPONENT_PROJECT_URL = https://opensource.apple.com/tarballs/mDNSResponder/
COMPONENT_LICENSE = Apache 2.0 license
COMPONENT_LICENSE_FILE = LICENSE

include $(WS_TOP)/make-rules/encumbered.mk
include $(WS_TOP)/make-rules/prep.mk
include $(WS_TOP)/make-rules/configure.mk
include $(WS_TOP)/make-rules/ips.mk

COMPONENT_BUILD_ENV = CC=gcc C++=g++ CFLAGS+=" $(CFLAGS) -DGUID_LIBUUID " CXXFLAGS+=" $(CXXFLAGS) -DGUID_LIBUUID "
COMPONENT_PRE_CONFIGURE_ACTION= \
	($(RM) -rf $(@D) ;$(TOUCH) $(SOURCE_DIR)/configure; $(CP) -a $(SOURCE_DIR) $(@D); $(CP) $(COMPONENT_DIR)/files/Makefile $(@D) ) 


build: $(BUILD_32)

install: $(INSTALL_32)

test: $(NO_TESTS)

