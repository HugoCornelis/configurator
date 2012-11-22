##
## Neurospaces toolset configuration.
##

#SUBDIRS = perl tests

nobase_dist_etc_DATA = \
	@ETC_CONFIGURATION_FILES@

#! the file paths have the /etc prefix already, so here we must not specify it.

etcdir = $(prefix)

dist-hook:
	cp $(srcdir)/license.txt $(distdir)
#	cp -R $(srcdir)/docs $(distdir)
#	cp -R $(srcdir)/perl $(distdir)
#	test -d $(distdir)/tests || mkdir $(distdir)/tests
#	test -d $(distdir)/tests/specifications || mkdir $(distdir)/tests/specifications
#	cp -R $(srcdir)/tests/run $(distdir)/tests/run
#	cp -R $(srcdir)/tests/tests_2_html $(distdir)/tests/tests_2_html
#	cp -R $(srcdir)/tests/specifications $(distdir)/tests
#	cp -R $(srcdir)/tests/code/tests.config $(distdir)/tests/code/tests.config
#	cp -R $(srcdir)/tests/tests.config $(distdir)/tests/tests.config
#	cp -R $(srcdir)/tests.config $(distdir)
#	cp -R $(srcdir)/tests/perl $(distdir)/tests

#check_SCRIPTS = $(srcdir)/tests/run

#TESTS = $(srcdir)/tests/run

#perl_HEADERS = studio_test.pm

#TESTS = studio_test.pm

test: check

html-upload-prepare:
	rm -fr html/htdocs/neurospaces_project/reconstruct/
	mkdir --parents html/htdocs/neurospaces_project/reconstruct
	mkdir --parents html/htdocs/neurospaces_project/reconstruct/html_source
	tar cfh - tests/html | ( cd html/htdocs/neurospaces_project/reconstruct && tar vxf - )

html-upload: html-upload-prepare
	scp -pr html/htdocs/* hcornelis,neurospaces@web.sourceforge.net:/home/groups/n/ne/neurospaces/htdocs/

#perldir = @PMDIR@

#nobase_perl_DATA = \
#	reconstruct_test.pm \
#	@PERL_EMBED_DATA@

#nobase_perl_DATA = @PERL_EMBED_DATA@

