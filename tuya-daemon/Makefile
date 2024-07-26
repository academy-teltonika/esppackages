include $(TOPDIR)/rules.mk

PKG_NAME:=tuya-daemon
PKG_VERSION:=1.0
PKG_RELEASE:=1

SOURCE_DIR:=/home/studentas/tasks/rutos/daemon-rut
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/Ugnius27/daemon-rut
PKG_SOURCE_VERSION:=9ea9f7f12930c82387d6f750665e584f505aadee
include $(INCLUDE_DIR)/package.mk

PKG_BUILD_DEPENDS:=argp-standalone
TARGET_LDFLAGS:=-largp

define Package/tuya-daemon
  DEPENDS:=+libtuya +libubus +libubox +libblobmsg-json
  CATEGORY:=Daemons
  TITLE:=tuya-daemon
endef

define Package/tuya-daemon/description
  TODO.
endef

define Package/tuya-daemon/install
		$(INSTALL_DIR) $(1)/usr/bin
		$(INSTALL_BIN) $(PKG_BUILD_DIR)/build/tuyad $(1)/usr/bin
		$(INSTALL_DIR) $(1)/etc/init.d
		$(INSTALL_BIN) ./files/tuyad.init $(1)/etc/init.d/tuyad
		$(INSTALL_DIR) $(1)/etc/config
		$(INSTALL_BIN) ./files/tuyad.config $(1)/etc/config/tuyad
endef

$(eval $(call BuildPackage,tuya-daemon))
