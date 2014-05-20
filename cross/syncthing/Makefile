PKG_NAME = syncthing
PKG_VERS = v0.8.7
PKG_EXT = tar.gz
PKG_DIST_NAME = $(PKG_NAME)-linux-$(SYNCTHING_ARCH)-$(PKG_VERS).$(PKG_EXT)
PKG_DIST_SITE = https://github.com/calmh/syncthing/releases/download/$(PKG_VERS)
PKG_DIR = $(PKG_NAME)-$(PKG_VERS)

DEPENDS = 

HOMEPAGE = http://www.syncthing.net/
COMMENT  = Syncthing replaces Dropbox and BitTorrent Sync with something open, trustworthy and decentralized. Your data is your data alone and you deserve to choose where it is stored, if it is shared with some third party and how ...
LICENSE  =

EXTRACT_PATH = $(WORK_DIR)/$(PKG_DIR)
CONFIGURE_TARGET = nop
COMPILE_TARGET = nop
INSTALL_TARGET = myInstall
GNU_CONFIGURE = 1
CONFIGURE_ARGS = 

# Define SYNCTHING_ARCH as per SyncThing standards
ifeq ($(findstring $(ARCH),88f5281 88f6281 armada370 armadaxp),$(ARCH))
SYNCTHING_ARCH = arm
endif
ifeq ($(findstring $(ARCH),powerpc ppc824x ppc853x),$(ARCH))
SYNCTHING_ARCH = powerpc
endif
ifeq ($(findstring $(ARCH),evansport),$(ARCH))
SYNCTHING_ARCH = 386
endif
ifeq ($(findstring $(ARCH),x86 cedarview bromolow),$(ARCH))
SYNCTHING_ARCH = amd64
endif
ifeq ($(findstring $(ARCH),qoriq),$(ARCH))
SYNCTHING_ARCH = ppc_quoriq
endif
ifeq ($(SYNCTHING_ARCH),)
$(error Unsupported ARCH $(ARCH))
endif

include ../../mk/spksrc.cross-cc.mk

