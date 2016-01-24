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

COMPONENT_NAME= libshairplay
COMPONENT_VERSION= 1.0.0
COMPONENT_FMRI = library/audio/libshairplay
COMPONENT_CLASSIFICATION = System/Multimedia Libraries
COMPONENT_SUMMARY= Free portable AirPlay server implementation similar to ShairPort.
COMPONENT_SRC= shairplay-ce80e005908f41d0e6fde1c4a21e9cb8ee54007b
COMPONENT_ARCHIVE= $(COMPONENT_SRC).tar.gz
COMPONENT_ARCHIVE_HASH= \
  sha256:49ac0e0470ec6367f720c7b79a09165138f57b60f5949a2d9c38be5823d13294
COMPONENT_ARCHIVE_URL= \
  https://github.com/juhovh/shairplay/archive/ce80e005908f41d0e6fde1c4a21e9cb8ee54007b.tar.gz
COMPONENT_PROJECT_URL = https://github.com/juhovh/shairplay
COMPONENT_LICENSE = MIT 
COMPONENT_LICENSE_FILE = LICENSE

include $(WS_TOP)/make-rules/encumbered.mk
include $(WS_TOP)/make-rules/prep.mk
include $(WS_TOP)/make-rules/configure.mk
include $(WS_TOP)/make-rules/ips.mk

CFLAGS += $($(COMPILER)_PIC)

COMPONENT_PRE_CONFIGURE_ACTION= \
            ( cd  $(COMPONENT_DIR)/$(COMPONENT_SRC) && \
		sh autogen.sh )
COMPONENT_POST_INSTALL_ACTION= \
	($(GSED) -e "s:%LIBDIR%:$(CONFIGURE_LIBDIR.$(BITS)):g" -e "s:%VERSION%:$(COMPONENT_VERSION):g" $(COMPONENT_DIR)/$(COMPONENT_SRC)/shairplay.pc > $(BUILD_DIR)/shairplay.pc.$(BITS)  )
build: $(BUILD_32_and_64)

install: $(INSTALL_32_and_64)

test: $(NO_TESTS)

