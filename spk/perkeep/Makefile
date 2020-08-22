SPK_NAME = perkeep
SPK_VERS = 0.10
SPK_REV = 1
SPK_ICON = src/keepy-small.png

DEPENDS = cross/busybox cross/$(SPK_NAME)

MAINTAINER = SynoCommunity
DESCRIPTION  = Perkeep lets you permanently keep your stuff, for life.
# DESCRIPTION_FRE = 
# DESCRIPTION_SPN = 
RELOAD_UI = yes
STARTABLE = yes
DISPLAY_NAME = Perkeep
CHANGELOG = "1. Initial release; perkeep "

HOMEPAGE = https://perkeep.org
LICENSE  = Apache-2.0

WIZARDS_DIR = src/wizard/

SERVICE_USER = auto
SERVICE_WIZARD_SHARE = wizard_download_dir
SERVICE_SETUP = src/service-setup.sh
SERVICE_PORT = 9091
SERVICE_PORT_TITLE = $(DISPLAY_NAME)

# Admin link for in DSM UI
ADMIN_PORT = $(SERVICE_PORT)

POST_STRIP_TARGET = perkeep_extra_install

BUSYBOX_CONFIG = usrmng
ENV += BUSYBOX_CONFIG="$(BUSYBOX_CONFIG)"


include ../../mk/spksrc.spk.mk


.PHONY: perkeep_extra_install
perkeep_extra_install:
	install -m 755 -d $(STAGING_DIR)/var
	install -m 644 src/settings.json $(STAGING_DIR)/var/settings.json
