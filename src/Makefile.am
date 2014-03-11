dist_bin_SCRIPTS = liftoff
CLEANFILES = $(dist_bin_SCRIPTS)
EXTRA_DIST = liftoff.in

edit = sed \
	-e 's|@RUBY[@]|$(RUBY)|g' \
	-e 's|@rubydir[@]|$(rubydir)|g' \
	-e 's|@gemsetuppath[@]|$(gemsetuppath)|g'

liftoff: Makefile liftoff.in
	$(edit) $(srcdir)/$@.in > $@
	chmod +x $@
