PKG_NAME = perkeep
PKG_VERS = 0.10
PKG_ORG = perkeep
PKG_IMPORT_PATH = github.com/$(PKG_ORG)/$(PKG_NAME)
PKG_EXT = tar.gz
PKG_DIST_NAME = $(PKG_VERS).$(PKG_EXT)
PKG_DIST_SITE = https://$(PKG_IMPORT_PATH)/archive
PKG_DIST_FILE = $(PKG_NAME)-$(PKG_VERS).$(PKG_EXT)
EXTRACT_PATH = $(WORK_DIR)/src/github.com/$(PKG_ORG)
PKG_DIR = $(PKG_NAME)
# DEPENDS = cross/zlib cross/openssl cross/curl cross/libevent
DEPENDS = native/go cross/sqlite

HOMEPAGE = https://perkeep.org
COMMENT  = Perkeep lets you permanently keep your stuff, for life. See https://perkeep.org/doc/synology
LICENSE  = Apache-2.0

POST_EXTRACT_TARGET = perkeep_post_extract

GO_SRC_DIR = $(EXTRACT_PATH)/$(PKG_NAME)
GO_BIN_DIR = $(GO_SRC_DIR)/$(PKG_NAME)
GO_LDFLAGS = -s -w
# Perkeep: does it have a version field?
# GO_LDFLAGS = -s -w -X github.com/perkeep/perkeep/config.Version=$(PKG_VERS)
# use GOPATH within workdir
GOPATH=$(WORK_DIR)

include ../../mk/spksrc.cross-go.mk

.PHONY: perkeep_post_extract
perkeep_post_extract:
	cd $(EXTRACT_PATH) && mv $(PKG_NAME)-$(PKG_VERS) $(PKG_NAME)
