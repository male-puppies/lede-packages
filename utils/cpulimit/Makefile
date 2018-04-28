#
# Copyright (C) 2014 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=cpulimit
PKG_RELEASE:=1

PKG_MAINTAINER:=Jay <870337742@qq.com>
PKG_LICENSE:=GPL-2.0+

include $(INCLUDE_DIR)/package.mk

define Package/cpulimit
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=OpenWrt cpulimit
endef

define Package/cpulimit/description
	Cpulimit is a tool which limits the CPU usage of a process (expressed in percentage, not in CPU time).
	 It is useful to control batch jobs, when you don't want them to eat too many CPU cycles.
endef

TARGET_CFLAGS += -I$(STAGING_DIR)/usr/include

ifneq ($(CONFIG_USE_GLIBC),)
  TARGET_CFLAGS += -D_DEFAULT_SOURCE
endif

define Package/cpulimit/conffiles
endef

define Build/Prepare
        mkdir -p $(PKG_BUILD_DIR)
        $(CP) ./src/* $(PKG_BUILD_DIR)/
endef

define Package/cpulimit/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/cpulimit $(1)/usr/sbin/
endef

$(eval $(call BuildPackage,cpulimit))
