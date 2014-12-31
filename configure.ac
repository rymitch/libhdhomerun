AC_PREREQ(2.63)
AC_INIT([libhdhomerun],
        [0.1],
        [rymitch@gmail.com],
        [libhdhomerun],
        [http://github.com/rymitch/libhdhomerun/])
AM_INIT_AUTOMAKE([
        -Wall
        -Werror
        foreign
        subdir-objects
])

AM_PROG_AR
AC_PROG_CC
AC_PROG_LIBTOOL

case "$host_os" in
*darwin* | *rhapsody* | *macosx*)
        AC_DEFINE_UNQUOTED(DARWIN,1,[This is an Apple Darwin system])
        build_target="darwin"
        posix="yes"
        ;;
linux*)
        AC_DEFINE_UNQUOTED(LINUX,1,[This is a Linux kernel])
        AC_CHECK_LIB(pthread, pthread_create)
        AC_CHECK_LIB(rt, clock_gettime)
        build_target="linux"
        posix="yes"
        ;;
*cygwin*)
        AC_DEFINE_UNQUOTED(CYGWIN,1,[This is a Cygwin system])
        AC_DEFINE_UNQUOTED(WINDOWS,1,[This is a Windows system])
        build_target="cygwin"
        ;;
*mingw*)
        AC_DEFINE_UNQUOTED(MINGW,1,[This is a MinGW system])
        AC_DEFINE_UNQUOTED(WINDOWS,1,[This is a Windows system])
        AC_DEFINE_UNQUOTED(_WIN32,1,[This is a Windows system])
        build_target="mingw"
        ;;
*)
        AC_MSG_RESULT(Unrecognised OS $host_os)
        AC_DEFINE_UNQUOTED(OTHEROS,1,[Some strange OS])
;;
esac

AC_MSG_CHECKING([for build target])
AM_CONDITIONAL(DARWIN, test "$build_target" = "darwin")
AM_CONDITIONAL(CYGWIN, test "$build_target" = "cygwin")
AM_CONDITIONAL(MINGW, test "$build_target" = "mingw")
AM_CONDITIONAL(LINUX, test "$build_target" = "linux")
AM_CONDITIONAL(POSIX, test "$posix" = "yes")
AC_MSG_RESULT([$build_target])

AC_CONFIG_MACRO_DIR([m4])
AM_SILENT_RULES([yes])
LT_INIT([
        disable-static
        pic-only
])
AC_CONFIG_HEADERS(config.h)
AC_CONFIG_FILES([
        Makefile
])
AC_OUTPUT
