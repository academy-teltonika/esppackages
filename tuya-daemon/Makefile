include $(TOPDIR)/rules.mk

PKG_NAME:=tuya-daemon
PKG_VERSION:=1.0
PKG_RELEASE:=1

SOURCE_DIR:=/home/studentas/tasks/rutos/daemon-rut
#PKG_SOURCE_PROTO:=git
#PKG_SOURCE_URL:=http://84.15.161.187/ugnsta/daemon-rut
#PKG_SOURCE_VERSION:=90b0c87a7450bc0dfef28434710159eceae5efc3
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

define Build/Prepare
		mkdir -p $(PKG_BUILD_DIR)
		cp -r $(SOURCE_DIR)/* $(PKG_BUILD_DIR)
		$(Build/Patch)
endef

define Package/tuya-daemon/install
		$(INSTALL_DIR) $(1)/usr/bin
		$(INSTALL_BIN) $(PKG_BUILD_DIR)/build/tuyad $(1)/usr/bin
endef

$(eval $(call BuildPackage,tuya-daemon))
