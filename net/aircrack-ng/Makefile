#
# Copyright (C) 2006-2015 OpenWrt.org
# Copyright (C) 2018 adde88@gmail.com
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=aircrack-ng
PKG_VERSION:=1.2-rc5
PKG_RELEASE:=8
PKG_LICENSE:=GPLv2

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/aircrack-ng/aircrack-ng.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=03911733590c42c943e1e1c3258c9a6630035a92
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.gz

PKG_FIXUP:=autoreconf

PKG_BUILD_PARALLEL:=1
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/aircrack-ng
  SECTION:=net
  CATEGORY:=Network
  DEPENDS:=+libpcap +libpthread +libopenssl +libnl +wireless-tools +ethtool +libstdcpp +libpcre +libsqlite3
  TITLE:=WLAN tools for breaking 802.11 WEP/WPA keys
  URL:=https://www.aircrack-ng.org/
  MAINTAINER:=Andreas Nilsen <adde88@gmail.com>
  SUBMENU:=wireless
endef

define Package/aircrack-ng/description
  WLAN tools for breaking 802.11 WEP/WPA keys
endef

CONFIGURE_ARGS+=  --with-ext-scripts \
		  --with-experimental

MAKE_FLAGS+=	pkglibexecdir=/usr/bin \
		prefix=/usr \
		OSNAME=Linux

CFLAGS="$(TARGET_CFLAGS) -Wall -Iinclude/ $(TARGET_CPPFLAGS) -D_REVISION=0" -msse -msse2 -msse3 \

define Package/aircrack-ng/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/* $(1)/usr/bin/
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/sbin/* $(1)/usr/sbin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/src/aircrack-ng--generic $(1)/usr/bin
endef

$(eval $(call BuildPackage,aircrack-ng))
