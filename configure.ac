AC_INIT([servicehisilicon], [0.1], [])
AM_INIT_AUTOMAKE([subdir-objects foreign dist-bzip2 no-define tar-pax])
AC_CONFIG_MACRO_DIR([m4])
LT_INIT

AC_PROG_CC
AC_PROG_CXX
AM_PATH_PYTHON
AX_PYTHON_DEVEL
AC_LANG(C++)

PKG_CHECK_MODULES(ENIGMA2, enigma2)

AC_ARG_WITH(boxtype,
	AS_HELP_STRING([--with-boxtype],[build for BOXTYPE, $withval]),
	[BOXTYPE="$withval"],[BOXTYPE=""])
AC_SUBST(BOXTYPE)
AC_DEFINE_UNQUOTED(BOXTYPE,"$BOXTYPE",[box type])

AC_ARG_WITH(brandname,
	AS_HELP_STRING([--with-brandname],[build for MACHINE_BRAND, $withval]),
	[MACHINE_BRAND="$withval"],[MACHINE_BRAND=""])
AC_SUBST(MACHINE_BRAND)
AC_DEFINE_UNQUOTED(MACHINE_BRAND,"$MACHINE_BRAND",[brand name])

AC_ARG_WITH(platform,
	AS_HELP_STRING([--with-platform],[build for PLATFORM, $withval]),
	[PLATFORM="$withval"],[PLATFORM=""])
AC_SUBST(PLATFORM)
AC_DEFINE_UNQUOTED(PLATFORM,"$PLATFORM",[platform])

AX_CXX_COMPILE_STDCXX_17([ext],[mandatory])

AC_DEFINE([DEBUG])

AC_ARG_WITH(binarycompatibledebug,
	AC_HELP_STRING([--with-binarycompatibledebug], [use e2 independent debug output]),
	[[with_binarycompatibledebug=$withval]],
	[[with_binarycompatibledebug=no]]
)

if test x"$with_binarycompatibledebug" = xyes ; then
	AC_DEFINE([BINARY_COMPATIBLE_DEBUGLOG])
fi

AC_PATH_PROG(MSGFMT, msgfmt, AC_MSG_ERROR(Could not find msgfmt))

AC_CONFIG_FILES([
Makefile
servicehisilicon/Makefile
plugin/Makefile
locale/Makefile
])
AC_OUTPUT
