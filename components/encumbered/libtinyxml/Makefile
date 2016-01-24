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

COMPONENT_NAME= libtinyxml
COMPONENT_VERSION= 2.6.2
COMPONENT_FMRI = library/libtinyxml
COMPONENT_CLASSIFICATION = System/Libraries
COMPONENT_SUMMARY= TinyXML is a simple, small, minimal, C++ XML parser that can be easily integrating into other programs.
COMPONENT_SRC= tinyxml
COMPONENT_ARCHIVE= $(COMPONENT_SRC)-$(COMPONET_VERSION).tar.gz
COMPONENT_ARCHIVE_HASH= \
  sha256:15bdfdcec58a7da30adc87ac2b078e4417dbe5392f3afb719f9ba6d062645593
COMPONENT_ARCHIVE_URL= \
  http://downloads.sourceforge.net/project/tinyxml/tinyxml/2.6.2/tinyxml_2_6_2.tar.gz
COMPONENT_PROJECT_URL = http://sourceforge.net/projects/tinyxml/
COMPONENT_LICENSE = zlib/libpng License
COMPONENT_LICENSE_FILE = COPYING

include $(WS_TOP)/make-rules/encumbered.mk
include $(WS_TOP)/make-rules/prep.mk
include $(WS_TOP)/make-rules/configure.mk
include $(WS_TOP)/make-rules/ips.mk


COMPONENT_PRE_CONFIGURE_ACTION= \
            ( cd  $(COMPONENT_DIR)/$(COMPONENT_SRC) && \
		$(TOUCH)  INSTALL NEWS README AUTHORS ChangeLog && \
		libtoolize && aclocal && autoconf && automake --add-missing )
COMPONENT_POST_INSTALL_ACTION= \
	($(GSED) -e "s:%LIBDIR%:$(CONFIGURE_LIBDIR.$(BITS)):g" -e "s:%VERSION%:$(COMPONENT_VERSION):g" $(COMPONENT_DIR)/$(COMPONENT_SRC)/tinyxml.pc > $(BUILD_DIR)/tinyxml.pc.$(BITS)  )
build: $(BUILD_32_and_64)

install: $(INSTALL_32_and_64)

test: $(NO_TESTS)

