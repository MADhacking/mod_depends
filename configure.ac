dnl Process this file with autoconf to produce a configure script.

dnl Ensure a recent version of Autoconf.
AC_PREREQ(2.59)

dnl Initialise the Autoconf system.
AC_INIT(mod_depends, 0.7.1)

dnl Determine system type
AC_CANONICAL_TARGET

dnl Configure m4 macro directory.
AC_CONFIG_MACRO_DIR([m4])

dnl Initialize automake.
AM_INIT_AUTOMAKE([])

dnl Locate suitable C compiler
AC_PROG_CXX
AC_PROG_AWK
AC_PROG_CC
AC_PROG_CPP
AC_PROG_INSTALL
AC_PROG_LN_S
AC_PROG_MAKE_SET
AC_PROG_RANLIB
AC_PROG_MKDIR_P
AM_PROG_CC_C_O 

dnl Initialize Libtool.
LT_INIT

dnl Check if Libtool is present.
AC_PROG_LIBTOOL

dnl Set locations of headers and makefiles.
AM_CONFIG_HEADER([include/mod_depends_config.h:config.in])
AC_CONFIG_FILES([Makefile src/Makefile])

dnl Check for correct source directory.
AC_CONFIG_SRCDIR([src/mod_depends.c])

dnl Check that we have version 2.0.40+ of Apache and get useful vars.
AP_VERSION=2.0.40
CHECK_APACHE(,$AP_VERSION,
    :,:,
    AC_MSG_ERROR([*** Apache version $AP_VERSION not found!])
)

MODULE_CFLAGS="${APXS_CFLAGS} ${AP_INCLUDES} ${APR_INCLUDES} ${APU_INCLUDES}"

AC_SUBST(MODULE_CFLAGS)

AC_OUTPUT

echo "---"
echo "Configuration summary for mod_depends"
echo ""
echo "   * Apache Modules Directory:    $AP_LIBEXECDIR"
echo ""
echo "---"
