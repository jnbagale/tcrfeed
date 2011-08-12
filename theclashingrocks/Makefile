
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

PKG_NAME:=tcr
PKG_VERSION:=0.0.3

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://theclashingrocks.org/tarballs

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

PKG_INSTALL:=1


include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/nls.mk

TARGET_LDFLAGS+= \
	-Wl,-rpath-link=$(STAGING_DIR)/usr/lib \

define Package/tcr
	SECTION:=utils
	CATEGORY:=Utilities
	DEPENDS:=+glib2 +libgsl +libsdl +libsdl-gfx +libsdl-image +libuuid +libsdl-ttf +spread
	TITLE:=theclashingrocks
endef


define Build/Configure
	$(call Build/Configure/Default)
endef

define Build/Compile
	$(call Build/Compile/Default)
endef

define Package/tcr/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_DIR) $(1)/usr/share/tcr
	$(CP) $(PKG_INSTALL_DIR)/usr/bin/tcr $(1)/usr/bin/
	$(CP) $(PKG_INSTALL_DIR)/usr/share/tcr/* $(1)/usr/share/tcr/

endef

$(eval $(call BuildPackage,tcr))
