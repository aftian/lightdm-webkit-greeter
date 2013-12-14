greeter_PROGRAMS = lightdm-webkit-greeter
greeterdir = $(bindir)

lightdm_webkit_greeter_SOURCES = \
	lightdm-webkit-greeter.c

lightdm_webkit_greeter_CFLAGS = \
	$(GREETER_CFLAGS) \
	$(WARN_CFLAGS) \
	-DVERSION=\"$(VERSION)\" \
	-DGETTEXT_PACKAGE=\"$(GETTEXT_PACKAGE)\" \
	-DLOCALE_DIR=\"$(localedir)\" \
	-DBINARY=\"lightdm-webkit-greeter\"

lightdm_webkit_greeter_LDADD = \
	$(GREETER_LIBS)

DISTCLEANFILES = \
	Makefile.in
