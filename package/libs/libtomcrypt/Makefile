#
# Copyright (C) 2014 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=libtomcrypt
PKG_VERSION:=1.18.0
PKG_RELEASE:=1

PKG_SOURCE:=crypt-$(PKG_VERSION).tar.xz
PKG_SOURCE_URL:=https://github.com/libtom/${PKG_NAME}/releases/download/v${PKG_VERSION}/
PKG_HASH:=da9df56a314afaab71963aa71bb6a075ea6bdee3d4db4af045f6bfe23e88b87a

PKG_LICENSE:=WTFPL
PKG_LICENSE_FILES:=LICENSE

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/libtomcrypt
  SECTION:=libs
  CATEGORY:=Libraries
  TITLE:=LibTom Crypto library
  URL:=http://www.libtom.net/LibTomCrypt
  DEPENDS:=+libtommath
endef

TARGET_CFLAGS += $(FPIC) -DUSE_LTM -DLTM_DESC

define Build/Install
	$(call Build/Install/Default,NODOCS=1 USER=$(shell id -u) GROUP=$(shell id -g) install)
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/lib
	$(INSTALL_DIR) $(1)/usr/include
	$(CP) $(PKG_INSTALL_DIR)/usr/local/include/*.h $(1)/usr/include
	$(CP) $(PKG_INSTALL_DIR)/usr/local/lib/libtomcrypt.a $(1)/usr/lib
endef


define Package/libtomcrypt/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/local/lib/libtomcrypt.a $(1)/usr/lib/
endef

$(eval $(call BuildPackage,libtomcrypt))
