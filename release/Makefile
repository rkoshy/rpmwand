VERSION=0.9.3
RELEASE=1
RPMFILE=RPMS/noarch/rpmwand-$(VERSION)-1.noarch.rpm

$(RPMFILE): rpmwand.spec.in rpmwand-files.txt
	mkdir -p rpmwand-skel/usr/bin/ || exit 1
	cp -p ../rpmwand rpmwand-skel/usr/bin/rpmwand || exit 1
	../rpmwand build rpmwand $(VERSION) $(RELEASE) || exit 1
	-rm -rf rpmwand-$(VERSION).tar.gz rpmwand.spec rpmwand-$(VERSION) faked-root.* || exit 1
