#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PECL_NAME:=redis
PECL_LONGNAME:=Redis - an API for communicating with the Redis key-value store

PKG_NAME:=php7-pecl-$(PECL_NAME)
PKG_VERSION=2017-09-27-$(PKG_SOURCE_VERSION)
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/phpredis/phpredis.git
PKG_SOURCE_VERSION:=24e78592547c31e4cd4ab778020437c575364cf4
PKG_SOURCE_SUBDIR:=$(PECL_NAME)-$(PKG_SOURCE_VERSION)
PKG_SOURCE:=$(PECL_NAME)-$(PKG_SOURCE_VERSION).tar.gz

PKG_MAINTAINER:=Michael Grunder <michael.grunder@gmail.com>

PKG_LICENSE:=PHPv3.01
PKG_LICENSE_FILES:=

PKG_BUILD_DIR:=$(BUILD_DIR)/pecl-php7/$(PECL_NAME)-$(PKG_SOURCE_VERSION)
PKG_BUILD_PARALLEL:=1

PKG_FIXUP:=autoreconf

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/nls.mk
include ../php7/pecl.mk

CONFIGURE_ARGS+= --with-redis=shared,"$(STAGING_DIR)/usr"

$(eval $(call PECLPackage,$(PECL_NAME),$(PECL_LONGNAME),+php7-mod-sockets,25))
$(eval $(call BuildPackage,$(PKG_NAME)))
