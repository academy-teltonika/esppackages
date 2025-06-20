include $(TOPDIR)/rules.mk

PKG_NAME:=tuyad
PKG_VERSION:=1.0
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/academy-teltonika/tuyad.git
PKG_SOURCE_VERSION:=f9b6dc10edd52bcadfa13e36d93146338e403e69
 
include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk
CMAKE_BINARY_SUBDIR:=build

define Package/tuyad/description
	Tuya cloud communication daemon.
endef

PKG_BUILD_DEPENDS:=argp-standalone

define Package/tuyad
	DEPENDS:=+libtuya +libubus +libubox +libblobmsg-json +espcommd
	CATEGORY:=Daemons
	TITLE:=tuyad
endef

define Package/tuyad/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/tuyad $(1)/usr/bin
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) ./files/tuyad.init $(1)/etc/init.d/tuyad
	$(INSTALL_DIR) $(1)/etc/config
	$(INSTALL_DATA) ./files/tuyad.config $(1)/etc/config/tuyad
endef

$(eval $(call BuildPackage,tuyad))
