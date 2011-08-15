# Copyright (C) [2011] [TheClashingRocks.org]
#
# Authors: Antonio Kheirkhahzadeh <antoniodariush@gmail.com> Jiva Bagale <jnbagale@gmail.com>
#
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
# 
include $(TOPDIR)/rules.mk

PKG_NAME:=spread-src
PKG_VERSION:=4.1.0

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://theclashingrocks.org/tarballs

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk


define Package/libspread
    TITLE:=libspread
    SECTION:=libs
    DEPENDS:=+librt
    CATEGORY:=Libraries
    URL:=http://www.spread.org/
endef

define Package/libspread/description
    this is libspread.
endef

define Build/Configure
	$(call Build/Configure/Default)
endef

define Build/Compile
	$(call Build/Compile/Default)
endef

define Build/InstallDev
	$(INSTALL_DIR) \
		$(1)/usr/lib 	\
		$(1)/usr/include 

	$(CP) \
		$(PKG_INSTALL_DIR)/usr/lib/* \
		$(1)/usr/lib/
	$(CP) \
		$(PKG_INSTALL_DIR)/usr/include/* \
		$(1)/usr/include/

endef

define Package/libspread/install
	$(INSTALL_DIR) \
		$(1)/usr/lib

	$(CP) \
		$(PKG_INSTALL_DIR)/usr/lib/* \
		$(1)/usr/lib/

endef

$(eval $(call BuildPackage,libspread))
