AC_INIT([GerenXchange], [2.15], [https://github.com/GerenXchange/GerenXchange/issues], [],
	[https://GerenXchange.com/projects/GerenXchange/])
AC_CONFIG_AUX_DIR(aux)
AM_INIT_AUTOMAKE([1.11 foreign dist-xz])
AM_SILENT_RULES([yes])

AC_CONFIG_SRCDIR([src/GerenXchange.c])
AC_CONFIG_HEADERS([config.h])
AC_CONFIG_FILES([Makefile src/Makefile man/Makefile test/Makefile])

AC_PROG_CC
AC_PROG_LN_S
AC_PROG_INSTALL

# Configuration.
AC_CHECK_HEADERS(sys/time.h)
AC_CHECK_FUNCS(strstr getopt getsubopt gettimeofday)

# Check for uint[8,16,32]_t
AC_TYPE_UINT8_T
AC_TYPE_UINT16_T
AC_TYPE_UINT32_T

# Check for pkg-config first, warn if it's not installed
PKG_PROG_PKG_CONFIG

# Check for required libraries
PKG_CHECK_MODULES([uev],  [libuev >= 2.2.0])
PKG_CHECK_MODULES([lite], [libite >= 1.5.0])

AC_OUTPUT
