SPK_NAME = syncthing
SPK_VERS = v0.8.8
SPK_REV = 1
SPK_ICON = src/syncthing.png
DSM_UI_DIR = app

DEPENDS  = cross/busybox cross/$(SPK_NAME)

MAINTAINER = SynoCommunity
DESCRIPTION = Automatically sync files via secure, distributed technology.
DESCRIPTION_FRE = Synchronisation automatique de fichiers via une technologie sûre et distribuée. 
ADMIN_PORT = 7070
RELOAD_UI = yes
DISPLAY_NAME = Syncthing

HOMEPAGE   = http://www.syncthing.net/
LICENSE    =

WIZARDS_DIR = src/wizard/

INSTALLER_SCRIPT = src/installer.sh
SSS_SCRIPT       = src/dsm-control.sh

INSTALL_PREFIX = /usr/local/$(SPK_NAME)

POST_STRIP_TARGET = syncthing_extra_install

BUSYBOX_CONFIG = usrmng
ENV += BUSYBOX_CONFIG="$(BUSYBOX_CONFIG)"

include ../../mk/spksrc.spk.mk

.PHONY: syncthing_extra_install
btsync_extra_install:
	install -m 755 -d $(STAGING_DIR)/var
	install -m 600 src/sync.conf $(STAGING_DIR)/var/sync.conf
	install -m 755 -d $(STAGING_DIR)/app
	install -m 644 src/app/config $(STAGING_DIR)/app/config
	install -m 755 -d $(STAGING_DIR)/app/images
	for size in 16 24 32 48 72; do \
		convert $(SPK_ICON) -thumbnail $${size}x$${size} \
		        $(STAGING_DIR)/app/images/$(SPK_NAME)-$${size}.png ; \
	done
