dnl Process this file with autoconf to produce a configure script

AC_INIT(bitlib, 26, rrt@sc3d.org)
AM_INIT_AUTOMAKE

dnl Check for programs
AC_PROG_CC
AC_PROG_LIBTOOL
AC_SUBST(LIBTOOL_DEPS)

dnl Extra CFLAGS if we have gcc
if test "$GCC" = yes; then
    CFLAGS="$CFLAGS -Wall -W -Wmissing-prototypes -Wstrict-prototypes -pedantic"
fi

dnl Check for header files
AC_HEADER_STDC

dnl Whether to use builtin float to int cast (OK e.g. on i386)
AC_SUBST(BUILTIN_CAST)
AC_ARG_WITH([builtin-cast],
            [AS_HELP_STRING([--with-builtin-cast],
                            [Use Lua's built-in cast from float to integer])])
if test "$with_builtin_cast" = yes; then
   AC_DEFINE(BUILTIN_CAST, 1, [Define to 1 to use Lua's built-in float to integer cast.])
fi

dnl Lua
AX_WITH_LUA
if test -z "$LUA"; then
  AC_MSG_FAILURE([Lua not found])
fi
AX_LUA_VERSION(501, 502)
AX_LUA_HEADERS
AX_LUA_LIBS
AX_LUA_LIB_VERSION(501, 502)
AC_SUBST(LUA)
AC_SUBST(LUA_INCLUDE)
AC_SUBST(LUA_LIB)

dnl Lua libraries
dnl FIXME: Parametrize on version
lualibdir='${libdir}/lua/5.1'
AC_SUBST(lualibdir)

dnl Generate output files
AC_CONFIG_MACRO_DIR(m4)
AC_CONFIG_FILES(Makefile)
AC_OUTPUT
