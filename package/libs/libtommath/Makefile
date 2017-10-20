#
# Copyright (C) 2014 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=libtommath
PKG_VERSION:=1.0.1
PKG_RELEASE:=1

PKG_SOURCE:=ltm-$(PKG_VERSION).tar.xz
PKG_SOURCE_URL:=https://github.com/libtom/${PKG_NAME}/releases/download/v${PKG_VERSION}/
PKG_HASH:=47032fb39d698ce4cf9c9c462c198e6b08790ce8203ad1224086b9b978636c69

PKG_LICENSE:=WTFPL
PKG_LICENSE_FILES:=LICENSE

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/libtommath
  SECTION:=libs
  CATEGORY:=Libraries
  TITLE:=LibTom Math library
  URL:=http://www.libtom.net/LibTomMath
endef

TARGET_CFLAGS += $(FPIC)

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/lib
	$(INSTALL_DIR) $(1)/usr/include
	$(CP) $(PKG_INSTALL_DIR)/usr/local/include/*.h $(1)/usr/include
	$(CP) $(PKG_INSTALL_DIR)/usr/local/lib/libtommath.a $(1)/usr/lib
endef


define Package/libtommath/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/local/lib/libtommath.a $(1)/usr/lib/
endef

$(eval $(call BuildPackage,libtommath))
