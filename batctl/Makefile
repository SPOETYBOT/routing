# SPDX-License-Identifier: GPL-2.0-only

include $(TOPDIR)/rules.mk



endif

define ConfigVars
$(subst $(space),,$(foreach opt,$(config-$(1)),CONFIG_$(opt)=$(1)
))
endef

define batctl_config
$(call ConfigVars,n)$(call ConfigVars,y)
endef
$(eval $(call shexport,batctl_config))

MAKE_FLAGS += $(call shvar,batctl_config)

define Package/batctl-tiny/install
	$(INSTALL_DIR) $(1)/usr/libexec
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/batctl

