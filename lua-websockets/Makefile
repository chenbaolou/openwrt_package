#
# Copyright (C) 2009-2013 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=lua-websockets
PKG_VERSION:=1.0.0
PKG_RELEASE:=1
PKG_MAINTAINER:=Dirk Chang <dirk@kooiot.com>
PKG_LICENSE:=MIT

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/lipp/lua-websockets.git
PKG_SOURCE_PROTO:=git
PKG_SOURCE_VERSION:=f8dbe73d7fa642ad55c6257ccf086dd7800aca09
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/lua-websockets
  SUBMENU:=Lua
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=Lua-Websockets
  URL:=https://github.com/lipp/lua-websockets
  DEPENDS:=+lua
endef

define Package/lua-websockets/description
  Websockets for Lua.
endef

define Build/Configure
endef

define Build/Compile
	$(MAKE) -C $(PKG_BUILD_DIR) \
		T="$(BUILD_VARIANT)" \
		PREFIX="$(PKG_INSTALL_DIR)/usr" \
		install
endef

# add make variable overrides here
MAKE_FLAGS +=

define Package/lua-websockets/install
	$(INSTALL_DIR) $(1)/usr/lib/lua
	$(INSTALL_DIR) $(1)/usr/lib/lua/websocket
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/src/websocket.lua $(1)/usr/lib/lua/
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/src/websocket/bit.lua $(1)/usr/lib/lua/websocket
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/src/websocket/client.lua $(1)/usr/lib/lua/websocket
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/src/websocket/client_copas.lua $(1)/usr/lib/lua/websocket
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/src/websocket/client_ev.lua $(1)/usr/lib/lua/websocket
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/src/websocket/client_sync.lua $(1)/usr/lib/lua/websocket
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/src/websocket/ev_common.lua $(1)/usr/lib/lua/websocket
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/src/websocket/frame.lua $(1)/usr/lib/lua/websocket
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/src/websocket/handshake.lua $(1)/usr/lib/lua/websocket
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/src/websocket/server.lua $(1)/usr/lib/lua/websocket
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/src/websocket/server_copas.lua $(1)/usr/lib/lua/websocket
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/src/websocket/server_ev.lua $(1)/usr/lib/lua/websocket
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/src/websocket/sync.lua $(1)/usr/lib/lua/websocket
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/src/websocket/tools.lua $(1)/usr/lib/lua/websocket
endef

$(eval $(call BuildPackage,lua-websockets))
