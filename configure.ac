dnl Process this file with autoconf to produce a configure script.

AC_INIT(lightdm-webkit-greeter, 0.1.0)
AC_CONFIG_MACRO_DIR(m4)
AC_CONFIG_HEADER(config.h)
AM_INIT_AUTOMAKE
AM_PROG_CC_C_O
AM_MAINTAINER_MODE
m4_ifdef([AM_SILENT_RULES], [AM_SILENT_RULES(yes)])

GNOME_COMPILE_WARNINGS(maximum)

dnl ###########################################################################
dnl Dependencies
dnl ###########################################################################

PKG_CHECK_MODULES(GREETER, [
    liblightdm-gobject-0
    gtk+-2.0
    webkit-1.0
    dbus-glib-1
])

dnl ###########################################################################
dnl Configurable values
dnl ###########################################################################
THEME_DIR=`$PKG_CONFIG --define-variable=prefix=$prefix --variable=themedir liblightdm-gobject-0`
AC_SUBST(THEME_DIR)

GREETER_DIR=`$PKG_CONFIG --define-variable=prefix=$prefix --variable=greeterdir liblightdm-gobject-0`
AC_SUBST(GREETER_DIR)

dnl ###########################################################################
dnl Internationalization
dnl ###########################################################################

IT_PROG_INTLTOOL(0.35.0)
GETTEXT_PACKAGE=lightdm-webkit-greeter
AC_DEFINE_UNQUOTED(GETTEXT_PACKAGE, "$GETTEXT_PACKAGE", Gettext package)

dnl ###########################################################################
dnl Files to generate
dnl ###########################################################################

AC_OUTPUT([
Makefile
src/Makefile
po/Makefile.in
themes/Makefile
themes/webkit/Makefile
])

dnl ###########################################################################
dnl Summary
dnl ###########################################################################

echo "
                    Light Display Manager WebKit Greeter $VERSION
                    ==========================================

        prefix:                   $prefix
        Theme directory:          $THEME_DIR
        Greeter directory:        $GREETER_DIR
"
