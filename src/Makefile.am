moddir=${AP_LIBEXECDIR}
mod_LTLIBRARIES = mod_depends.la 

mod_depends_la_SOURCES = mod_depends.c
mod_depends_la_CFLAGS  = -Wall -I${top_srcdir}/include ${MODULE_CFLAGS}
mod_depends_la_LDFLAGS = -rpath ${AP_LIBEXECDIR} -module -avoid-version

plugindir=${AP_LIBEXECDIR}/mod_depends
plugin_LTLIBRARIES = http.la

install: install-am
	rm -f $(DESTDIR)${moddir}/mod_depends.a
	rm -f $(DESTDIR)${moddir}/mod_depends.la
	mkdir -p $(DESTDIR)${AP_INCLUDEDIR}
	cp -p $(top_srcdir)/include/mod_depends.h $(DESTDIR)${AP_INCLUDEDIR}
