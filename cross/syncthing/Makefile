PKG_NAME = syncthing
PKG_VERS = v0.8.8
PKG_EXT = tar.gz
PKG_DIST_NAME = $(PKG_NAME)-linux-$(SYNCTHING_ARCH)-$(PKG_VERS).$(PKG_EXT)
PKG_DIST_SITE = https://github.com/calmh/syncthing/releases/download/$(PKG_VERS)
PKG_DIR = $(PKG_NAME)-linux-$(SYNCTHING_ARCH)-$(PKG_VERS)

DEPENDS = 

HOMEPAGE = http://www.syncthing.net/
COMMENT  = Syncthing replaces Dropbox and BitTorrent Sync with something open, trustworthy and decentralized. Your data is your data alone and you deserve to choose where it is stored, if it is shared with some third party and how ...
LICENSE  =

CONFIGURE_TARGET = nop
COMPILE_TARGET = nop
INSTALL_TARGET = myInstall
GNU_CONFIGURE = 1
CONFIGURE_ARGS = 

# Define SYNCTHING_ARCH as per SyncThing standards
ifeq ($(findstring $(ARCH),88f6281 88f6282),$(ARCH))
SYNCTHING_ARCH = armv5
endif
ifeq ($(findstring $(ARCH),qoriq ppc853x ppc854x ppc824x),$(ARCH))
$(error Unsupported ARCH $(ARCH))
endif
ifeq ($(findstring $(ARCH),evansport),$(ARCH))
SYNCTHING_ARCH = 386
endif
ifeq ($(findstring $(ARCH),x86 cedarview bromolow),$(ARCH))
SYNCTHING_ARCH = amd64
endif
ifeq ($(SYNCTHING_ARCH),)
$(error Unsupported ARCH $(ARCH))
endif

include ../../mk/spksrc.cross-cc.mk

myInstall:
    mkdir -p $(STAGING_INSTALL_PREFIX)/bin
    install -m 755 $(WORK_DIR)/$(PKG_DIR)/syncthing $(STAGING_INSTALL_PREFIX)/bin/
