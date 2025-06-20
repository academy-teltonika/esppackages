include $(TOPDIR)/rules.mk

PKG_NAME:=libsigroksp
PKG_VERSION:=1.0
PKG_RELEASE:=1
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=git://sigrok.org/libserialport
PKG_SOURCE_VERSION:=21b3dfe5f68c205be4086469335fd2fc2ce11ed2

PKG_FIXUP:=autoreconf
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/libsigroksp
	CATEGORY:=Libraries
	TITLE:=libsigroksp
endef

define Package/libsigroksp/description
	Sigrok serial port library.
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/lib
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/libserialport.so.0.1.1 $(1)/usr/lib
	$(LN) libserialport.so.0.1.1 $(1)/usr/lib/libserialport.so.0
	$(LN) libserialport.so.0.1.1 $(1)/usr/lib/libserialport.so
	$(INSTALL_DIR) $(1)/usr/include
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/include/libserialport.h $(1)/usr/include 
endef

define Package/libsigroksp/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/libserialport.so.0.1.1 $(1)/usr/lib
	$(LN) libserialport.so.0.1.1 $(1)/usr/lib/libserialport.so.0
	$(LN) libserialport.so.0.1.1 $(1)/usr/lib/libserialport.so
endef

$(eval $(call BuildPackage,libsigroksp))
