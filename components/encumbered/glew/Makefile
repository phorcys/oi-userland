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

COMPONENT_NAME= glew
COMPONENT_VERSION= 1.13.0
COMPONENT_FMRI = library/video/glew
COMPONENT_CLASSIFICATION = System/Multimedia Libraries
COMPONENT_SUMMARY= The OpenGL Extension Wrangler Library is a simple tool that helps C/C++ developers initialize extensions and write portable applications.
COMPONENT_SRC= $(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE= $(COMPONENT_SRC).tar.gz
COMPONENT_ARCHIVE_HASH= \
  sha256:aa25dc48ed84b0b64b8d41cdd42c8f40f149c37fa2ffa39cd97f42c78d128bc7
COMPONENT_ARCHIVE_URL= \
  http://downloads.sourceforge.net/project/glew/glew/$(COMPONENT_VERSION)/$(COMPONENT_NAME)-$(COMPONENT_VERSION).tgz
COMPONENT_PROJECT_URL = http://sourceforge.net/projects/glew/
COMPONENT_LICENSE = BSD,MIT
COMPONENT_LICENSE_FILE = LICENSE.txt

include $(WS_TOP)/make-rules/encumbered.mk
include $(WS_TOP)/make-rules/prep.mk
include $(WS_TOP)/make-rules/configure.mk
include $(WS_TOP)/make-rules/ips.mk
include $(WS_TOP)/make-rules/cmake.mk

COMPONENT_PRE_CONFIGURE_ACTION =        (cp -a $(SOURCE_DIR)/* $(@D))

CMAKE_OPTIONS = -DSTATIC_BUILD=NO
# Don't depend on host default pg_config
CMAKE_OPTIONS+= -DINSTALL_LAYOUT=SVR4
CMAKE_OPTIONS+= -DCMAKE_INSTALL_PREFIX=$(CONFIGURE_PREFIX)


$(BUILD_DIR)/%/.configured:     $(SOURCE_DIR)/.prep
	($(RM) -rf $(@D) ; $(MKDIR) $(@D))
	$(COMPONENT_PRE_CONFIGURE_ACTION)
	(cd $(@D) ; $(ENV) $(CONFIGURE_ENV) $(CMAKE) $(CMAKE_OPTIONS) $(@D)/build/cmake)
	$(COMPONENT_POST_CONFIGURE_ACTION)
	$(TOUCH) $@

build: $(BUILD_32)

install: $(INSTALL_32)
