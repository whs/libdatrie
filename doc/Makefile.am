EXTRA_DIST = meson.build

if ENABLE_DOXYGEN_DOC

all-local: doxygen.stamp

doxygen.stamp: $(top_srcdir)/datrie/*.h $(top_srcdir)/datrie/*.c
	$(DOXYGEN)
	touch doxygen.stamp

install-data-local: install-html

install-html:
	$(INSTALL) -d $(DESTDIR)$(htmldocdir)
	$(INSTALL_DATA) html/* $(DESTDIR)$(htmldocdir)

uninstall-local:
	rm -rf $(DESTDIR)$(htmldocdir)

clean-local:
	rm -rf html man
	rm -f doxygen.stamp
	rm -f doxygen_sqlite3.db

else

install-data-local:
uninstall-local:
clean-local:

endif

