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

COMPONENT_NAME= libdcadec
COMPONENT_VERSION= 0.2.0
COMPONENT_FMRI = library/audio/libdcadec
COMPONENT_CLASSIFICATION = System/Multimedia Libraries
COMPONENT_SUMMARY= dcadec is a free DTS Coherent Acoustics decoder with support for HD extensions.
COMPONENT_SRC= dcadec-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE= $(COMPONENT_SRC).tar.gz
COMPONENT_ARCHIVE_HASH= \
  sha256:ed9d207fde3e8d576f3af8b0d1235b3371e315175757173689104efcaebf0d44
COMPONENT_ARCHIVE_URL= \
  https://github.com/foo86/dcadec/archive/v$(COMPONENT_VERSION).tar.gz
COMPONENT_PROJECT_URL = https://github.com/foo86/dcadec
COMPONENT_LICENSE = LGPLv2.1
COMPONENT_LICENSE_FILE = COPYING.LGPLv2.1

include $(WS_TOP)/make-rules/encumbered.mk
include $(WS_TOP)/make-rules/prep.mk
include $(WS_TOP)/make-rules/configure.mk
include $(WS_TOP)/make-rules/ips.mk

COMPONENT_BUILD_ENV= PREFIX=/usr CC=gcc CXX=g++
COMPONENT_PRE_CONFIGURE_ACTION= \
	( touch $(SOURCE_DIR)/configure && chmod +x $(SOURCE_DIR)/configure \
	&& cp -rf $(SOURCE_DIR)/* $(@D) )
COMPONENT_BUILD_OPTIONS= -DCONFIG_SHARED
build: $(BUILD_32)

install: $(INSTALL_32)

test: $(NO_TESTS)

