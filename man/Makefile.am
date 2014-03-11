dist_man_MANS = liftoff.1 liftoffrc.5

###### manpages as HTML
release_build_man_html:
	([ -d gh-pages ] || git clone --branch gh-pages --single-branch .. gh-pages) && \
	for i in $(dist_man_MANS); do \
	  mandoc -Thtml -Oman=%N.%S.html $$i > gh-pages/$$i.html ; \
	done && \
	cd gh-pages && \
	cp liftoff.1.html index.html && \
	git add -A && \
	git commit -m "HTML documentation for $(PACKAGE_VERSION)"

release_push_man_html:
	cd gh-pages && \
		git push -f $(ORIGIN_URL) gh-pages

release_clean_man_html:
	rm -rf gh-pages
