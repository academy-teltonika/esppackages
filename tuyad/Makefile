include $(TOPDIR)/rules.mk

PKG_NAME:=tuyad
PKG_VERSION:=1.0
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/academy-teltonika/tuyad.git
PKG_SOURCE_VERSION:=a4f2d54c1c73fdb6528e6e15001503754af85e5f
 
include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk
CMAKE_BINARY_SUBDIR:=build

define Package/tuyad/description
	Tuya cloud communication daemon.
endef

PKG_BUILD_DEPENDS:=argp-standalone libtuya libubus libubox libblobmsg-json

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
	$(INSTALL_BIN) ./files/tuyad.config $(1)/etc/config/tuyad
endef

$(eval $(call BuildPackage,tuyad))
