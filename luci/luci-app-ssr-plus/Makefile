include $(TOPDIR)/rules.mk

PKG_NAME:=luci-app-ssr-plus
PKG_VERSION:=183
PKG_RELEASE:=6

PKG_CONFIG_DEPENDS:= \
	CONFIG_PACKAGE_$(PKG_NAME)_INCLUDE_Kcptun \
	CONFIG_PACKAGE_$(PKG_NAME)_INCLUDE_NaiveProxy \
	CONFIG_PACKAGE_$(PKG_NAME)_INCLUDE_Redsocks2 \
	CONFIG_PACKAGE_$(PKG_NAME)_INCLUDE_Shadowsocks \
	CONFIG_PACKAGE_$(PKG_NAME)_INCLUDE_ShadowsocksR \
	CONFIG_PACKAGE_$(PKG_NAME)_INCLUDE_ShadowsocksR_Server \
	CONFIG_PACKAGE_$(PKG_NAME)_INCLUDE_Simple_Obfs \
	CONFIG_PACKAGE_$(PKG_NAME)_INCLUDE_Trojan \
	CONFIG_PACKAGE_$(PKG_NAME)_INCLUDE_V2ray \
	CONFIG_PACKAGE_$(PKG_NAME)_INCLUDE_V2ray_Plugin \
	CONFIG_PACKAGE_$(PKG_NAME)_INCLUDE_Xray

LUCI_TITLE:=SS/SSR/V2Ray/Trojan/NaiveProxy/Socks5/Tun LuCI interface
LUCI_PKGARCH:=all
LUCI_DEPENDS:=+coreutils +coreutils-base64 +dns2socks +dnsmasq-full +ipset +ip-full \
	+iptables-mod-tproxy +lua +libuci-lua +microsocks +tcping \
	+resolveip +shadowsocksr-libev-ssr-check +wget-ssl \
	+PACKAGE_$(PKG_NAME)_INCLUDE_Kcptun:kcptun-client \
	+PACKAGE_$(PKG_NAME)_INCLUDE_NaiveProxy:naiveproxy \
	+PACKAGE_$(PKG_NAME)_INCLUDE_Redsocks2:redsocks2 \
	+PACKAGE_$(PKG_NAME)_INCLUDE_Shadowsocks:shadowsocks-libev-ss-local \
	+PACKAGE_$(PKG_NAME)_INCLUDE_Shadowsocks:shadowsocks-libev-ss-redir \
	+PACKAGE_$(PKG_NAME)_INCLUDE_ShadowsocksR:shadowsocksr-libev-ssr-local \
	+PACKAGE_$(PKG_NAME)_INCLUDE_ShadowsocksR:shadowsocksr-libev-ssr-redir \
	+PACKAGE_$(PKG_NAME)_INCLUDE_ShadowsocksR_Server:shadowsocksr-libev-ssr-server \
	+PACKAGE_$(PKG_NAME)_INCLUDE_Simple_Obfs:simple-obfs \
	+PACKAGE_$(PKG_NAME)_INCLUDE_Trojan:trojan \
	+PACKAGE_$(PKG_NAME)_INCLUDE_Trojan:ipt2socks \
	+PACKAGE_$(PKG_NAME)_INCLUDE_V2ray:v2ray \
	+PACKAGE_$(PKG_NAME)_INCLUDE_V2ray_Plugin:v2ray-plugin \
	+PACKAGE_$(PKG_NAME)_INCLUDE_Xray:xray-core

define Package/$(PKG_NAME)/config
config PACKAGE_$(PKG_NAME)_INCLUDE_Kcptun
	bool "Include Kcptun"
	default n

config PACKAGE_$(PKG_NAME)_INCLUDE_NaiveProxy
	bool "Include NaiveProxy"
	depends on !(arc||armeb||mips||mips64||powerpc)
	default y if i386||x86_64||arm||aarch64

config PACKAGE_$(PKG_NAME)_INCLUDE_Redsocks2
	bool "Include Redsocks2"
	default n

config PACKAGE_$(PKG_NAME)_INCLUDE_Shadowsocks
	bool "Include Shadowsocks-libev"
	default y

config PACKAGE_$(PKG_NAME)_INCLUDE_ShadowsocksR
	bool "Include ShadowsocksR-libev"
	default y

config PACKAGE_$(PKG_NAME)_INCLUDE_ShadowsocksR_Server
	bool "Include ShadowsocksR Server"
	default y if i386||x86_64||arm||aarch64

config PACKAGE_$(PKG_NAME)_INCLUDE_Simple_Obfs
	bool "Include Shadowsocks Simple Obfs Plugin"
	default y

config PACKAGE_$(PKG_NAME)_INCLUDE_Trojan
	bool "Include Trojan"
	default y if arm||mipsel

config PACKAGE_$(PKG_NAME)_INCLUDE_V2ray
	bool "Include V2ray"
	default n

config PACKAGE_$(PKG_NAME)_INCLUDE_V2ray_Plugin
	bool "Include Shadowsocks V2ray Plugin"
	default n

config PACKAGE_$(PKG_NAME)_INCLUDE_Xray
	bool "Include Xray"
	default y if i386||x86_64||arm||aarch64
endef

define Package/$(PKG_NAME)/conffiles
/etc/config/shadowsocksr
/etc/ssrplus/
endef

include $(TOPDIR)/feeds/luci/luci.mk

# call BuildPackage - OpenWrt buildroot signature
