dist_man8_MANS     = GerenXchange.8
SYMLINK            = in.ftpd in.tftpd

# Hook in install to add GerenXchange.8 --> in.ftpd.8, in.tftpd.8 symlinks
install-data-hook:
	@for file in $(SYMLINK); do \
		link=$(DESTDIR)$(man8dir)/$$file.8; \
		test -e $$link && continue; \
		$(LN_S) $(dist_man8_MANS) $$link; \
	done

uninstall-hook:
	@for file in $(SYMLINK); do \
		$(RM) $(DESTDIR)$(man8dir)/$$file.8; \
	done

