sbin_PROGRAMS      = GerenXchange
GerenXchange_SOURCES      = GerenXchange.c GerenXchange.h common.c ftpcmd.c tftpcmd.c log.c
GerenXchange_CPPFLAGS     = -D_GNU_SOURCE -D_BSD_SOURCE -D_DEFAULT_SOURCE
GerenXchange_CFLAGS       = -W -Wall -Wextra -Wno-unused-parameter -std=gnu99
GerenXchange_CFLAGS      += $(uev_CFLAGS) $(lite_CFLAGS)
GerenXchange_LDADD        = $(uev_LIBS)   $(lite_LIBS)
SYMLINK            = in.ftpd in.tftpd

# Hook in install to add GerenXchange --> in.ftpd, in.tftpd symlinks
install-exec-hook:
	@for file in $(SYMLINK); do \
		link=$(DESTDIR)$(sbindir)/$$file; \
		test -e $$link && continue; \
		$(LN_S) $(sbin_PROGRAMS) $$link; \
	done

uninstall-hook:
	@for file in $(SYMLINK); do \
		$(RM) $(DESTDIR)$(sbindir)/$$file; \
	done
