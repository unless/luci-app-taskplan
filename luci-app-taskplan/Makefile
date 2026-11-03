#
# Copyright 2019-2026 sirpdboy
#
# This is free software, licensed under the Apache License, Version 2.0 .
#

include $(TOPDIR)/rules.mk

PKG_NAME:=luci-app-taskplan
PKG_VERSION:=3.0.1
PKG_RELEASE:=20260303

PKG_LICENSE:=GPL-2.0
PKG_MAINTAINER:=sirpdboy

LUCI_PKGARCH:=all

define Package/luci-app-taskplan
  SECTION:=luci
  CATEGORY:=LuCI
  SUBMENU:=3. Applications
  TITLE:=LuCI Support for Task Plan
  PKGARCH:=all
  DEPENDS:=+rpcd +luci-base +bash
endef

define Package/luci-app-taskplan/description
  Scheduled tasks and startup tasks management.
  Includes restart, shutdown, network restart, memory release,
  system cleaning, and custom scripts.
endef

define Build/Compile
endef

define Package/$(PKG_NAME)/conffiles
/etc/config/taskplan
endef

include $(TOPDIR)/feeds/luci/luci.mk

# call BuildPackage - OpenWrt buildroot signature

define Build/Prepare/$(LUCI_NAME)
	chmod 0755 \
		$(PKG_BUILD_DIR)/root/usr/libexec/rpcd/luci.taskplan \
		$(PKG_BUILD_DIR)/root/etc/init.d/taskplan \
		$(PKG_BUILD_DIR)/root/usr/bin/taskplanhandler \
		$(PKG_BUILD_DIR)/root/etc/taskplan/taskplanrun
endef
