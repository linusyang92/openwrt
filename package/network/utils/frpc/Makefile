#
# Copyright (c) 2016 Daniel Fu
# Copyright (c) 2017 EasyPi Software Foundation
#
# This is free software, licensed under the MIT License.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=frpc
PKG_VERSION:=0.17.0
PKG_RELEASE:=1

PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=LICENSE
PKG_MAINTAINER:=EasyPi Software Foundation

PKG_SOURCE:=frp_$(PKG_VERSION)_linux_mips.tar.gz
PKG_SOURCE_URL:=https://github.com/fatedier/frp/releases/download/v$(PKG_VERSION)
PKG_MD5SUM:=cc7cc78dbe75e3df74af708967b237e1
PKG_CAT:=zcat

include $(INCLUDE_DIR)/package.mk

define Package/frpc
	SECTION:=net
	CATEGORY:=Network
	TITLE:=A fast reverse proxy
	URL:=https://github.com/fatedier/frpc
endef

define Package/frpc/description
A fast reverse proxy to help you expose a local server behind a NAT or firewall to the internet.
endef

define Build/Compile
endef

define Package/frpc/postinst
endef

define Package/frpc/conffiles
/etc/config/frpc
endef

define Package/frpc/install
	$(INSTALL_DIR) $(1)/etc/config
	$(INSTALL_DATA) ./files/etc/config/frpc $(1)/etc/config/frpc
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) ./files/etc/init.d/frpc $(1)/etc/init.d/frpc
	$(INSTALL_DIR) $(1)/lib/upgrade/keep.d
	$(INSTALL_DATA) ./files/lib/upgrade/keep.d/frpc $(1)/lib/upgrade/keep.d/frpc
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(BUILD_DIR)/frp_$(PKG_VERSION)_linux_mips/frpc $(1)/usr/bin/frpc
endef

$(eval $(call BuildPackage,frpc))
