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


define Package/spread
    MAINTAINER:=team@theclashingrocks.org
    TITLE:=spread
    SECTION:=libs
    DEPENDS:=+librt +libspread
    CATEGORY:=Libraries
    URL:=http://www.spread.org/
endef

define Package/spread/description
    this is spread.
endef

CONFIGURE_ARGS+= --host=mipsel-openwrt-linux --cache-file=config.cache


define Build/Configure
	$(call Build/Configure/Default)
endef

define Build/Compile
	$(call Build/Compile/Default)
endef

define Build/InstallDev
	$(INSTALL_DIR) \
		$(1)/usr/lib 	 \
		$(1)/usr/include \
		$(1)/usr/bin \
		$(1)/usr/sbin \
		$(1)/etc

	$(CP) \
		$(PKG_INSTALL_DIR)/usr/lib/* \
		$(1)/usr/lib/
	$(CP) \
		$(PKG_INSTALL_DIR)/usr/include/* \
		$(1)/usr/include/
	$(CP) \
		$(PKG_INSTALL_DIR)/usr/bin/* \
		$(1)/usr/bin/
	$(CP) \
		$(PKG_INSTALL_DIR)/usr/sbin/* \
		$(1)/usr/sbin/
	$(CP) \
		$(PKG_INSTALL_DIR)/etc/* \
		$(1)/etc/

endef

define Package/spread/install
	$(INSTALL_DIR) \
		$(1)/usr/bin \
		$(1)/usr/sbin \
		$(1)/etc

	$(CP) \
		$(PKG_INSTALL_DIR)/usr/bin/* \
		$(1)/usr/bin/
	$(CP) \
		$(PKG_INSTALL_DIR)/usr/sbin/* \
		$(1)/usr/sbin/
	$(CP) \
		$(PKG_INSTALL_DIR)/etc/* \
		$(1)/etc/

endef

$(eval $(call BuildPackage,spread))
