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

# see https://metacpan.org/source/ASPIERS/Stow-v2.1.2/configure.ac

dnl Check for perl on our system.
dnl Call to AC_SUBST(PERL) is implicit
AC_PATH_PROGS([PERL], [perl] [perl5], [false])
if test "x$PERL" = xfalse
then
  AC_MSG_ERROR([Perl not found; check your \$PATH.])
fi
 
# N.B. ${var#pattern} will not work with some shells, such as
# Solaris 10's /bin/sh :-(
#
#   http://www.gnu.org/software/autoconf/manual/autoconf.html#Portable-Shell
#
#   eval `$PERL -V:siteprefix -V:installsitelib`
#   pmdir_relative_path="${installsitelib#$siteprefix/}"
#
# This will work:
#
#   pmdir_relative_path=`echo "${installsitelib}" | sed -e "s!^$siteprefix/!!"`
#
# but this is cleaner:
pmdir_relative_path=`\
  $PERL -MConfig \
        -wle '($_ = $Config{installsitelib})
              =~ s!^\Q$Config{siteprefix}/!!; \
              print'`
 
AC_ARG_WITH(
    [pmdir],
    AS_HELP_STRING(
      [--with-pmdir=DIR],
      [Install Perl modules in DIR]),
    [PMDIR=${withval}],
    [PMDIR='${prefix}'/"$pmdir_relative_path"])
AC_CONFIG_COMMANDS_POST([[
  eval pmdir="$PMDIR"
  cat <<EOF
 
# Perl modules will be installed to $PMDIR
EOF
  if [ "$pmdir" != "$PMDIR" ]; then
    cat <<EOF
# which will expand to
#
#   $pmdir
#
# unless you override the value of prefix at make-time.
EOF
    echo
  fi
]])
AC_SUBST([PMDIR])




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

