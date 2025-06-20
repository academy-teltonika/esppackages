include $(TOPDIR)/rules.mk

PKG_NAME:=libtuya
PKG_VERSION:=1.0
PKG_RELEASE:=1
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/tuya/tuya-iot-core-sdk
PKG_SOURCE_VERSION:=0208badefb2003d30e70b5b875395e3187c850d9

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk
CMAKE_BINARY_SUBDIR := build

define Package/libtuya
	CATEGORY:=Libraries
	TITLE:=libtuya
endef

define Package/libtuya/description
	Tuya cloud communiction library.
endef

# We need this empty definition, because everything crashes and burns withuot it :)
# (the build system tries to call a non existent make target "install" in the tuya library)
define Build/Install 
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/lib
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/build/lib/liblink_core.so $(1)/usr/lib
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/build/lib/libmiddleware_implementation.so $(1)/usr/lib
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/build/lib/libplatform_port.so $(1)/usr/lib
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/build/lib/libutils_modules.so $(1)/usr/lib

	$(INSTALL_DIR) $(1)/usr/include
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/interface/*.h $(1)/usr/include
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/utils/*.h $(1)/usr/include
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/libraries/mbedtls/include/mbedtls/*.h $(1)/usr/include
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/libraries/coreHTTP/source/dependency/3rdparty/http_parser/*.h $(1)/usr/include
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/libraries/coreMQTT/source/include/*.h $(1)/usr/include
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/include/*.h $(1)/usr/include
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/middleware/*.h $(1)/usr/include
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/examples/subdevice_basic_demo/tuya_cacert.h $(1)/usr/include
endef

define Package/libtuya/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/build/lib/liblink_core.so $(1)/usr/lib
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/build/lib/libmiddleware_implementation.so $(1)/usr/lib
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/build/lib/libplatform_port.so $(1)/usr/lib
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/build/lib/libutils_modules.so $(1)/usr/lib
endef

$(eval $(call BuildPackage,libtuya))
