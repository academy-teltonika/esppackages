include $(TOPDIR)/rules.mk

PKG_NAME:=espcommd
PKG_VERSION:=1.0
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/academy-teltonika/espcommd.git
PKG_SOURCE_VERSION:=0089e7dd5ac7eb2b297312d10dc7ac3c2afac7a8
 
include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk
CMAKE_BINARY_SUBDIR:=build

define Package/espcommd/description
	Ubus esp communication server daemon.
endef

define Package/espcommd
	DEPENDS:=+libubus +libubox +libblobmsg-json +libsigroksp
	CATEGORY:=Daemons
	TITLE:=espcommd
endef

define Package/espcommd/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/espcommd $(1)/usr/bin
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_DATA) ./files/espcommd.init $(1)/etc/init.d/espcommd
	$(INSTALL_DIR) $(1)/etc/config
	$(INSTALL_DATA) ./files/espcommd.config $(1)/etc/config/espcommd
endef

$(eval $(call BuildPackage,espcommd))
