AM_LIBADD = \
	$(PULSEAUDIO_LIBS) \
	$(HYBRIS_LIBS) \
	$(EXPAT_LIBS)
AM_CFLAGS = \
	$(DROID_DEVICE_CFLAGS) \
	$(PULSEAUDIO_CFLAGS) \
	$(DROIDHEADERS_CFLAGS) \
	$(HYBRIS_CFLAGS) \
	$(EXPAT_CFLAGS) \
	-DPULSEAUDIO_VERSION=@PA_MAJOR@ \
	-I$(top_srcdir)/src/common \
	-I$(top_srcdir)/src/common/include


modlibexec_LTLIBRARIES = libdroid-util$(DROID_MODULE_SUFFIX).la
includedir = @includedir@/pulsecore/modules/droid@DROID_MODULE_SUFFIX@
include_HEADERS = include/droid/version.h           \
                  include/droid/conversion.h        \
                  include/droid/droid-config.h      \
                  include/droid/droid-util.h        \
                  include/droid/sllist.h            \
                  include/droid/utils.h

pkgconfigdir = $(libdir)/pkgconfig
pkgconfig_DATA = libdroid-util$(DROID_MODULE_SUFFIX).pc

libdroid_util__DROID_MODULE_SUFFIX__la_SOURCES = droid-util.c             \
                           droid-config.c           \
                           conversion.c             \
                           config-parser-xml.c      \
                           config-parser-xml.h      \
                           sllist.c                 \
                           utils.c                  \
                           droid-util-audio.h
libdroid_util__DROID_MODULE_SUFFIX__la_LDFLAGS = -avoid-version -Wl,-z,noexecstack -lhybris-common $(SBJ_DEVICE_LDFLAGS)
libdroid_util__DROID_MODULE_SUFFIX__la_LIBADD = $(AM_LIBADD)
libdroid_util__DROID_MODULE_SUFFIX__la_CFLAGS = $(AM_CFLAGS)
