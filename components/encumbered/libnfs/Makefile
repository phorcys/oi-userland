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

COMPONENT_NAME= libnfs
COMPONENT_VERSION= 1.9.8
COMPONENT_FMRI = library/libnfs
COMPONENT_CLASSIFICATION = System/Libraries
COMPONENT_SUMMARY= LIBNFS is a client library for accessing NFS shares over a network.
COMPONENT_SRC=  $(COMPONENT_NAME)-$(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE= $(COMPONENT_SRC).tar.gz
COMPONENT_ARCHIVE_HASH= \
  sha256:e95af693e763a504eee72dacf3dc6c1001d83e40b807e7e1d0be2eaf48af779c
COMPONENT_ARCHIVE_URL= \
  https://github.com/sahlberg/libnfs/archive/libnfs-1.9.8.tar.gz
COMPONENT_PROJECT_URL = https://github.com/sahlberg/libnfs/
COMPONENT_LICENSE = LGPLv2.1,BSD
COMPONENT_LICENSE_FILE = COPYING

CONFIGURE_OPTIONS += 


include $(WS_TOP)/make-rules/encumbered.mk
include $(WS_TOP)/make-rules/prep.mk
include $(WS_TOP)/make-rules/configure.mk
include $(WS_TOP)/make-rules/ips.mk

COMPONENT_PRE_CONFIGURE_ACTION= \
            ( cd  $(COMPONENT_DIR)/$(COMPONENT_SRC) && \
                NOCONFIGURE=true sh bootstrap  )


build: $(BUILD_32_and_64)

install: $(INSTALL_32_and_64)

test: $(NO_TESTS)

