#
# Copyright (C) 2012 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=websocket_test
PKG_RELEASE:=1

PKG_BUILD_DIR := $(BUILD_DIR)/$(PKG_NAME)

include $(INCLUDE_DIR)/package.mk

define Package/websocket_test
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=websocket_test
  DEPENDS:=+libwebsockets +zlib +libsqlite3 +libjson-c +libuuid +libpthread
endef

define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)
	$(CP) ./src/* $(PKG_BUILD_DIR)/
endef

define Build/Configure
endef
TARGET_LDFLAGS := -ljson-c -lwebsockets  -luuid -lsqlite3 -lpthread
define Build/Compile
	$(MAKE) -C $(PKG_BUILD_DIR) \
		CC="$(TARGET_CC)" \
		CFLAGS="$(TARGET_CFLAGS) -Wall" \
		LDFLAGS="$(TARGET_LDFLAGS)"
endef

define Package/websocket_test/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/websocket_test $(1)/usr/sbin/
endef

$(eval $(call BuildPackage,websocket_test))
