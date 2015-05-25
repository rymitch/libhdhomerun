ACLOCAL_AMFLAGS = -I m4

lib_LTLIBRARIES = libhdhomerun.la
libhdhomerun_la_SOURCES = \
	src/hdhomerun_channels.c \
	src/hdhomerun_channelscan.c \
	src/hdhomerun_control.c \
	src/hdhomerun_debug.c \
	src/hdhomerun_device.c \
	src/hdhomerun_device_selector.c \
	src/hdhomerun_discover.c \
	src/hdhomerun_pkt.c \
	src/hdhomerun_video.c
if POSIX
libhdhomerun_la_SOURCES += src/hdhomerun_os_posix.c
libhdhomerun_la_SOURCES += src/hdhomerun_sock_posix.c
endif
libhdhomerun_la_LDFLAGS = -version-info 1:0:0

bin_PROGRAMS = hdhomerun_config
hdhomerun_config_SOURCES = src/hdhomerun_config.c
hdhomerun_config_LDADD = libhdhomerun.la
