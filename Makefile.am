# Makefile.am

ACLOCAL_AMFLAGS = -I config

LIBTOOL_DEPS = @LIBTOOL_DEPS@
SUBDIRS = libocispec config src templates doc hooks
DIST_SUBDIRS = libocispec config src templates doc hooks
EXTRA_DIST = \
	autogen.sh \
	lxc.spec \
	CONTRIBUTING \
	MAINTAINERS

RPMARGS =

pcdatadir = $(libdir)/pkgconfig
pcdata_DATA = lxc.pc

libtool: $(LIBTOOL_DEPS)
	$(SHELL) ./config.status libtool

install-data-local:
	$(MKDIR_P) $(DESTDIR)$(LXCPATH)
	$(MKDIR_P) $(DESTDIR)$(localstatedir)/cache/lxc

ChangeLog::
	@touch ChangeLog

rpm: dist
	rpmbuild --clean -ta ${distdir}.tar.gz $(RPMARGS)
