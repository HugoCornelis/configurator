dnl
dnl Neurospaces toolset configuration.
dnl

dnl Process this file with autoconf to produce a configure script.
# $Format: "AC_REVISION(${package}, ${label}, ${email})"$
AC_REVISION(configuration, nodist, hugo.cornelis@gmail.com)
dnl AC_REVISION($Id: configure.in 1.40 Wed, 10 Oct 2007 16:57:00 -0500 hugo $)
AC_INIT
AC_CONFIG_SRCDIR([configure.ac])

# $Format: "AM_INIT_AUTOMAKE(${package}, ${label})"$
AM_INIT_AUTOMAKE(configuration, nodist)

# find all configuration files

dnl this one does not work because of wrong configure or automake
dnl interpolation.  No time to figure it out.
dnl
dnl CONFIGURATION_FILES=`find etc -name "*[^~]" -type f -printf "%p "`

ETC_CONFIGURATION_FILES=`find etc/ -type f -printf "%p "`
AC_SUBST(ETC_CONFIGURATION_FILES)

# Checks for programs.

# Checks for libraries.

# Checks for header files.

# Checks for typedefs, structures, and compiler characteristics.

# Checks for library functions.

AC_CONFIG_FILES([Makefile
		])

AC_OUTPUT

