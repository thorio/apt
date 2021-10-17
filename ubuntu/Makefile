define deb
curl -o tmp/$(1).deb -L $(2)
reprepro includedeb generic tmp/$(1).deb
rm tmp/$(1).deb
endef

define appimage
mkdir -p build/$(1)/usr/share/$(1) build/$(1)/usr/bin
curl -o build/$(1)/usr/share/$(1)/$(1) -L $(2)
chmod +x build/$(1)/usr/share/$(1)/$(1)
ln -sf ../share/$(1)/$(1) build/$(1)/usr/bin/$(1)
dpkg-deb --build --root-owner-group build/$(1)
reprepro includedeb generic build/$(1).deb
rm build/$(1).deb build/$(1)/usr/share/$(1)/$(1) build/$(1)/usr/bin/$(1)
endef

.PHONY: alacritty
alacritty:
	$(call deb,alacritty,"https://launchpad.net/~aslatter/+archive/ubuntu/ppa/+files/alacritty_0.10.1+1-20220619T020303~jammy-92362428_amd64.deb")

.PHONY: blent
blent:
	$(call deb,blent,"https://github.com/thorio/blent/releases/download/0.4.1/blent.0.4.1.linux-x64.deb")

.PHONY: code
code:
	$(call deb,code,"https://code.visualstudio.com/sha/download?build=stable&os=linux-deb-x64")

.PHONY: discord
discord:
	$(call deb,discord,"https://discordapp.com/api/download?platform=linux&format=deb")

.PHONY: espanso
espanso:
	$(call deb,espanso,"https://github.com/federico-terzi/espanso/releases/download/v2.1.5-beta/espanso-debian-x11-amd64.deb")

.PHONY: foliate
foliate:
	$(call deb,foliate,"https://launchpad.net/~apandada1/+archive/ubuntu/foliate/+files/foliate_2.6.4-1~ubuntu22.04.1_all.deb")

.PHONY: chrome
chrome:
	$(call deb,google-chrome-stable,"https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb")

.PHONY: plexamp
plexamp:
	$(call appimage,plexamp,"https://plexamp.plex.tv/plexamp.plex.tv/desktop/Plexamp-4.2.2.AppImage")

.PHONY: clean
clean:
	$(RM) -rf tmp/*
